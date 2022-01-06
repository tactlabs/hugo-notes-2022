---
title: "One-Hot Encode Nominal Categorical Features"
author: "Chris Albon"
date: 2017-12-20T11:53:49-07:00
description: "How to one-hot encode nominal categorical features for machine learning in Python."
type: technical_note
draft: false
aliases: [/machine_learning/preprocessing_structured_data/one-hot_encode_nominal_categorical_features/]
---
<a alt="One-hot encoding" href="https://machinelearningflashcards.com">
    <img src="/images/machine_learning_flashcards/One-Hot_Encoding_print.png" class="flashcard center-block">
</a>

## Preliminaries


```python
# Load libraries
import numpy as np
import pandas as pd
from sklearn.preprocessing import OneHotEncoder
```

## Create Data With One Class Label


```python
# Create NumPy array
x = np.array([['Texas'], 
              ['California'], 
              ['Texas'], 
              ['Delaware'], 
              ['Texas']])
```

## One-hot Encode Data (Method 1)


```python
# Create LabelBinzarizer object
one_hot = OneHotEncoder()

# One-hot encode data
one_hot.fit_transform(x)
```




    <5x3 sparse matrix of type '<class 'numpy.float64'>'
    	with 5 stored elements in Compressed Sparse Row format>



## View Column Headers


```python
# View classes
one_hot.categories_
```




    [array(['California', 'Delaware', 'Texas'], dtype='<U10')]



## One-hot Encode Data (Method 2)


```python
# Dummy feature
pd.get_dummies(x[:,0])
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>California</th>
      <th>Delaware</th>
      <th>Texas</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>0</td>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>0</td>
      <td>0</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>


