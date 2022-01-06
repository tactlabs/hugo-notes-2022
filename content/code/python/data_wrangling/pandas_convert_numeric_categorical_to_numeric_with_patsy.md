---
title: "Convert A Categorical Variable Into Dummy Variables"
author: "Chris Albon"
date: 2017-12-20T11:53:49-07:00
description: "Convert A Categorical Variable Into Dummy Variables."
type: technical_note
draft: false
aliases: [/python/data_wrangling/pandas_convert_numeric_categorical_to_numeric_with_patsy/]
---

```python
# import modules
import pandas as pd
import patsy
```


```python
# Create dataframe
raw_data = {'countrycode': [1, 2, 3, 2, 1]} 
df = pd.DataFrame(raw_data, columns = ['countrycode'])
df
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>countrycode</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Convert the countrycode variable into three binary variables
patsy.dmatrix('C(countrycode)-1', df, return_type='dataframe')
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>C(countrycode)[1]</th>
      <th>C(countrycode)[2]</th>
      <th>C(countrycode)[3]</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>0.0</td>
      <td>1.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>0.0</td>
      <td>0.0</td>
      <td>1.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0.0</td>
      <td>1.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
  </tbody>
</table>
</div>


