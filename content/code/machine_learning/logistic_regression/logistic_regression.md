---
title: "Logistic Regression"
author: "Chris Albon"
date: 2017-12-20T11:53:49-07:00
description: "How to train a logistic regression in scikit-learn."
type: technical_note
draft: false
---
Despite having "regression" in its name, a logistic regression is actually a widely used binary classifier (i.e. the target vector can only take two values). In a logistic regression, a linear model (e.g. $\beta\_{0}+\beta\_{1}x$) is included in a logistic (also called sigmoid) function, ${\frac{1}{1+e^{-z}}}$, such that:

$$P(y\_i=1 \mid X)={\frac{1}{1+e^{-(\beta\_{0}+\beta\_{1}x)}}}$$

where $P(y\_i=1 \mid X)$ is the probability of the $i$th observation's target value, $y\_i$, being class 1, $X$ is the training data, $\beta\_0$ and $\beta\_1$ are the parameters to be learned, and $e$ is Euler's number.

## Preliminaries


```python
# Load libraries
from sklearn.linear_model import LogisticRegression
from sklearn import datasets
from sklearn.preprocessing import StandardScaler
```

## Load Iris Flower Dataset


```python
# Load data with only two classes
iris = datasets.load_iris()
X = iris.data[:100,:]
y = iris.target[:100]
```

## Standardize Features


```python
# Standarize features
scaler = StandardScaler()
X_std = scaler.fit_transform(X)
```

## Create Logistic Regression


```python
# Create logistic regression object
clf = LogisticRegression(random_state=0)
```

## Train Logistic Regression


```python
# Train model
model = clf.fit(X_std, y)
```

## Create Previously Unseen Observation


```python
# Create new observation
new_observation = [[.5, .5, .5, .5]]
```

## Predict Class Of Observation


```python
# Predict class
model.predict(new_observation)
```




    array([1])



## View Predicted Probabilities


```python
# View predicted probabilities
model.predict_proba(new_observation)
```




    array([[ 0.18823041,  0.81176959]])


