---
title: "Multinomial Logistic Regression"
author: "Chris Albon"
date: 2017-12-20T11:53:49-07:00
description: "How to train a multinomial logistic regression in scikit-learn."
type: technical_note
draft: false
aliases: [/machine_learning/naive_bayes/multinomial_logistic_regression/]
---
In multinomial logistic regression (MLR) the logistic function we saw in Recipe 15.1 is replaced with a softmax function:

$$P(y\_i=k \mid X)={\frac {e^{\beta\_{k}x\_{i}}}{{\sum\_{j=1}^{K}}e^{\beta\_{j}x\_{i}}}}$$

where $P(y\_i=k \mid X)$ is the probability the $i$th observation's target value, $y\_i$, is class $k$, and $K$ is the total number of classes. One practical advantage of the MLR is that its predicted probabilities using the `predict_proba` method are more reliable (i.e. better calibrated).

## Preliminaries


```python
# Load libraries
from sklearn.linear_model import LogisticRegression
from sklearn import datasets
from sklearn.preprocessing import StandardScaler
```

## Load Iris Flower Data


```python
# Load data
iris = datasets.load_iris()
X = iris.data
y = iris.target
```

## Standardize Features


```python
# Standarize features
scaler = StandardScaler()
X_std = scaler.fit_transform(X)
```

## Create Multinomial Logistic Regression


```python
# Create one-vs-rest logistic regression object
clf = LogisticRegression(random_state=0, multi_class='multinomial', solver='newton-cg')
```

## Train Multinomial Logistic Regression


```python
# Train model
model = clf.fit(X_std, y)
```

## Create Previously Unseen Observation


```python
# Create new observation
new_observation = [[.5, .5, .5, .5]]
```

## Predict Observation's Class


```python
# Predict class
model.predict(new_observation)
```




    array([1])



## View Probability Observation Is Each Class


```python
# View predicted probabilities
model.predict_proba(new_observation)
```




    array([[ 0.01944996,  0.74469584,  0.2358542 ]])


