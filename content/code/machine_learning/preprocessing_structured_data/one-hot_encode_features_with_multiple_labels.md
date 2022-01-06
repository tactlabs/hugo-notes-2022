---
title: "One-Hot Encode Features With Multiple Labels"
author: "Chris Albon"
date: 2017-12-20T11:53:49-07:00
description: "How to one-hot encode nominal categorical features with multiple labels per observation for machine learning in Python."
type: technical_note
draft: false
aliases: [/machine_learning/preprocessing_structured_data/one-hot_encode_features_with_multiple_labels/]
---
## Preliminaries


```python
# Load libraries
from sklearn.preprocessing import MultiLabelBinarizer
import numpy as np
```

## Create Data


```python
# Create NumPy array
y = [('Texas', 'Florida'), 
    ('California', 'Alabama'), 
    ('Texas', 'Florida'), 
    ('Delware', 'Florida'), 
    ('Texas', 'Alabama')]
```

## One-hot Encode Data


```python
# Create MultiLabelBinarizer object
one_hot = MultiLabelBinarizer()

# One-hot encode data
one_hot.fit_transform(y)
```




    array([[0, 0, 0, 1, 1],
           [1, 1, 0, 0, 0],
           [0, 0, 0, 1, 1],
           [0, 0, 1, 1, 0],
           [1, 0, 0, 0, 1]])



## View Column Headers


```python
# View classes
one_hot.classes_
```




    array(['Alabama', 'California', 'Delware', 'Florida', 'Texas'], dtype=object)


