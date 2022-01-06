---
title: "Making A Matplotlib Scatterplot From A Pandas Dataframe"
author: "Chris Albon"
date: 2017-12-20T11:53:49-07:00
description: "Making a Matplotlib scatterplot from a pandas dataframe."
type: technical_note
draft: false
aliases: [/python/data_visualization/matplotlib_scatterplot_from_pandas/]
---
### import modules


```python
%matplotlib inline
import pandas as pd
import matplotlib.pyplot as plt
import numpy as np
```

### Create dataframe


```python
raw_data = {'first_name': ['Jason', 'Molly', 'Tina', 'Jake', 'Amy'], 
        'last_name': ['Miller', 'Jacobson', 'Ali', 'Milner', 'Cooze'], 
        'female': [0, 1, 1, 0, 1],
        'age': [42, 52, 36, 24, 73], 
        'preTestScore': [4, 24, 31, 2, 3],
        'postTestScore': [25, 94, 57, 62, 70]}
df = pd.DataFrame(raw_data, columns = ['first_name', 'last_name', 'age', 'female', 'preTestScore', 'postTestScore'])
df
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>first_name</th>
      <th>last_name</th>
      <th>age</th>
      <th>female</th>
      <th>preTestScore</th>
      <th>postTestScore</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Jason</td>
      <td>Miller</td>
      <td>42</td>
      <td>0</td>
      <td>4</td>
      <td>25</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Molly</td>
      <td>Jacobson</td>
      <td>52</td>
      <td>1</td>
      <td>24</td>
      <td>94</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Tina</td>
      <td>Ali</td>
      <td>36</td>
      <td>1</td>
      <td>31</td>
      <td>57</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Jake</td>
      <td>Milner</td>
      <td>24</td>
      <td>0</td>
      <td>2</td>
      <td>62</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Amy</td>
      <td>Cooze</td>
      <td>73</td>
      <td>1</td>
      <td>3</td>
      <td>70</td>
    </tr>
  </tbody>
</table>
</div>



### Scatterplot of preTestScore and postTestScore, with the size of each point determined by age


```python
plt.scatter(df.preTestScore, df.postTestScore
, s=df.age)
```




    <matplotlib.collections.PathCollection at 0x10ca42b00>




![png](matplotlib_scatterplot_from_pandas_6_1.png)


### Scatterplot of preTestScore and postTestScore with the size = 300 and the color determined by sex


```python
plt.scatter(df.preTestScore, df.postTestScore, s=300, c=df.female)
```




    <matplotlib.collections.PathCollection at 0x10cb90a90>




![png](matplotlib_scatterplot_from_pandas_8_1.png)

