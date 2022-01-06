---
title: "Load An Excel File Into Pandas"
author: "Chris Albon"
date: 2017-12-20T11:53:49-07:00
description: "How to quickly load an Excel file into pandas."
type: technical_note
draft: false
aliases: [/python/data_wrangling/load_excel_file_into_pandas/]
---
## Preliminaries


```python
# Load library
import pandas as pd
```

## Load Excel File


```python
# Create URL to Excel file (alternatively this can be a filepath)
url = 'https://raw.githubusercontent.com/chrisalbon/simulated_datasets/master/data.xlsx'

# Load the first sheet of the Excel file into a data frame
df = pd.read_excel(url, sheetname=0, header=1)

# View the first ten rows
df.head(10)
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
      <th>5</th>
      <th>2015-01-01 00:00:00</th>
      <th>0</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>5</td>
      <td>2015-01-01 00:00:01</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>9</td>
      <td>2015-01-01 00:00:02</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>6</td>
      <td>2015-01-01 00:00:03</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>6</td>
      <td>2015-01-01 00:00:04</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>9</td>
      <td>2015-01-01 00:00:05</td>
      <td>0</td>
    </tr>
    <tr>
      <th>5</th>
      <td>7</td>
      <td>2015-01-01 00:00:06</td>
      <td>0</td>
    </tr>
    <tr>
      <th>6</th>
      <td>1</td>
      <td>2015-01-01 00:00:07</td>
      <td>0</td>
    </tr>
    <tr>
      <th>7</th>
      <td>6</td>
      <td>2015-01-01 00:00:08</td>
      <td>0</td>
    </tr>
    <tr>
      <th>8</th>
      <td>9</td>
      <td>2015-01-01 00:00:09</td>
      <td>0</td>
    </tr>
    <tr>
      <th>9</th>
      <td>5</td>
      <td>2015-01-01 00:00:10</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
</div>


