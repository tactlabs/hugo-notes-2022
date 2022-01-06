---
title: "Assign A New Column To A Pandas DataFrame"
author: "Chris Albon"
date: 2017-12-20T11:53:49-07:00
description: "Assign A New Column To A Pandas DataFrame."
type: technical_note
draft: false
aliases: [/python/data_wrangling/pandas_assign_new_column_dataframe/]
---
## Preliminaries


```python
import pandas as pd
```

## Create Dataframe


```python
# Create empty dataframe
df = pd.DataFrame()

# Create a column
df['name'] = ['John', 'Steve', 'Sarah']

# View dataframe
df
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>John</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Steve</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Sarah</td>
    </tr>
  </tbody>
</table>
</div>



## Assign New Column To Dataframe


```python
# Assign a new column to df called 'age' with a list of ages
df.assign(age = [31, 32, 19])
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>age</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>John</td>
      <td>31</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Steve</td>
      <td>32</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Sarah</td>
      <td>19</td>
    </tr>
  </tbody>
</table>
</div>


