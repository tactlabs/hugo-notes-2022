---
title: "Decision Tree Regression"
author: "Chris Albon"
date: 2017-12-20T11:53:49-07:00
description: "Training a decision tree regression in scikit-learn."
type: technical_note
draft: false
aliases: [/machine_learning/trees_and_forests/decision_tree_regression/]
images:
 - /images/machine_learning_flashcards/Decision_Tree_Regression_print.png
---
<a alt="Decision Tree Regression" href="https://machinelearningflashcards.com">
    <img src="/images/machine_learning_flashcards/Decision_Tree_Regression_print.png" class="flashcard center-block">
</a>

## Preliminaries


```python
# Load libraries
from sklearn.tree import DecisionTreeRegressor
from sklearn import datasets
```

## Load Boston Housing Dataset


```python
# Load data with only two features
boston = datasets.load_boston()
X = boston.data[:,0:2]
y = boston.target
```

## Create Decision Tree

Decision tree regression works similar to decision tree classification, however instead of reducing Gini impurity or entropy, potential splits are measured on how much they reduce the mean squared error (MSE):

$$\text{MSE} = \frac{1}{n} \sum_{i=1}^{n} (y_i - \hat{y}_i)^2$$

where $y_i$ is the true value of the target and $\hat{y}_i$ is the predicted value.


```python
# Create decision tree classifer object
regr = DecisionTreeRegressor(random_state=0)
```

## Train Model


```python
# Train model
model = regr.fit(X, y)
```

## Create Observation To Predict


```python
# Make new observation
observation = [[0.02, 16]]
              
# Predict observation's value  
model.predict(observation)
```




    array([ 33.])


