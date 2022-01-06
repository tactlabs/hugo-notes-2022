---
title: "Imputing Missing Class Labels"
author: "Chris Albon"
date: 2017-12-20T11:53:49-07:00
description: "How to impute missing class labels for machine learning in Python."
type: technical_note
draft: false
aliases: [/machine_learning/preprocessing_structured_data/imputing_missing_class_labels/]
---
## Preliminaries


```python
# Load libraries
import numpy as np
from sklearn.preprocessing import Imputer
```

## Create Feature Matrix With Missing Values


```python
# Create feature matrix with categorical feature
X = np.array([[0, 2.10, 1.45], 
              [1, 1.18, 1.33], 
              [0, 1.22, 1.27],
              [0, -0.21, -1.19],
              [np.nan, 0.87, 1.31],
              [np.nan, -0.67, -0.22]])
```

## Fill Missing Values' Class With Most Frequent Class


```python
# Create Imputer object
imputer = Imputer(strategy='most_frequent', axis=0)

# Fill missing values with most frequent class
imputer.fit_transform(X)
```




    array([[ 0.  ,  2.1 ,  1.45],
           [ 1.  ,  1.18,  1.33],
           [ 0.  ,  1.22,  1.27],
           [ 0.  , -0.21, -1.19],
           [ 0.  ,  0.87,  1.31],
           [ 0.  , -0.67, -0.22]])


