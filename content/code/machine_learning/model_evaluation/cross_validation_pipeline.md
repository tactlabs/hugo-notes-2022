---
title: "Cross Validation Pipeline"
author: "Chris Albon"
date: 2017-12-20T11:53:49-07:00
description: "Cross validaton pipeline with scikit."
type: technical_note
draft: false
aliases: [/machine_learning/model_evaluation/cross_validation_pipeline/]
---
The code below does a lot in only a few lines. To help explain things, here are the steps that code is doing:

1. Split the raw data into three folds. Select one for testing and two for training.
2. Preprocess the data by scaling the training features.
3. Train a support vector classifier on the training data.
4. Apply the classifier to the test data.
5. Record the accuracy score.
6. Repeat steps 1-5 two more times, once for each fold.
7. Calculate the mean score for all the folds.

## Preliminaries


```python
from sklearn.datasets import load_iris
from sklearn.pipeline import make_pipeline
from sklearn import preprocessing
from sklearn import cross_validation
from sklearn import svm
```

## Load Data

For this tutorial we will use the famous [iris dataset](https://en.wikipedia.org/wiki/Iris_flower_data_set). The iris data contains four measurements of 150 iris flowers and their species. We will use a support vector classifier to predict the species of the iris flowers.


```python
# Load the iris test data
iris = load_iris()
```


```python
# View the iris data features for the first three rows
iris.data[0:3]
```




    array([[ 5.1,  3.5,  1.4,  0.2],
           [ 4.9,  3. ,  1.4,  0.2],
           [ 4.7,  3.2,  1.3,  0.2]])




```python
# View the iris data target for first three rows. '0' means it flower is of the setosa species.
iris.target[0:3]
```




    array([0, 0, 0])



## Create Classifier Pipeline

Now we create a pipeline for the data. First, the pipeline preprocesses the data by scaling the feature variable's values to mean zero and unit variance. Second, the pipeline trains a support classifier on the data with `C=1`. `C` is the cost function for the margins. The higher the C, the less tolerant the model is for observations being on the wrong side of the hyperplane.


```python
# Create a pipeline that scales the data then trains a support vector classifier
classifier_pipeline = make_pipeline(preprocessing.StandardScaler(), svm.SVC(C=1))
```

## Cross Validation 

Scikit provides a great helper function to make it easy to do cross validation. Specifically, the code below splits the data into three folds, then executes the classifier pipeline on the iris data.

Important note from the [scikit docs](http://scikit-learn.org/stable/modules/generated/sklearn.cross_validation.cross_val_score.html#sklearn.cross_validation.cross_val_score): _For integer/None inputs, if y is binary or multiclass, StratifiedKFold used. If the estimator is a classifier or if y is neither binary nor multiclass, KFold is used._


```python
# KFold/StratifiedKFold cross validation with 3 folds (the default)
# applying the classifier pipeline to the feature and target data
scores = cross_validation.cross_val_score(classifier_pipeline, iris.data, iris.target, cv=3)
```

## Evaluate Model

Here is the output of our 3 KFold cross validation. Each value is the accuracy score of the support vector classifier when leaving out a different fold. There are three values because there are three folds. A higher accuracy score, the better.


```python
scores
```




    array([ 0.98039216,  0.90196078,  0.97916667])



To get an good measure of the model's accuracy, we calculate the mean of the three scores. This is our measure of model accuracy.


```python
scores.mean()
```




    0.95383986928104569


