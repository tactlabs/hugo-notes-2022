---
title: "Indexing And Slicing NumPy Arrays"
author: "Chris Albon"
date: 2017-12-20T11:53:49-07:00
description: "Indexing and slicing NumPy arrays."
type: technical_note
draft: false
aliases: [/python/basics/numpy_indexing_and_slicing/]
---

```python
# Import modules
import numpy as np
```


```python
# Create a 2x2 array
battle_deaths = [[344, 2345], [253, 4345]]
deaths = np.array(battle_deaths)
deaths
```




    array([[ 344, 2345],
           [ 253, 4345]])




```python
# Select the top row, second item
deaths[0, 1]
```




    2345




```python
# Select the second column
deaths[:, 1]
```




    array([2345, 4345])




```python
# Select the second row
deaths[1, :]
```




    array([ 253, 4345])




```python
# Create an array of civilian deaths
civilian_deaths = np.array([4352, 233, 3245, 256, 2394])
civilian_deaths
```




    array([4352,  233, 3245,  256, 2394])




```python
# Find the index of battles with less than 500 deaths
few_civ_deaths = np.where(civilian_deaths < 500)
few_civ_deaths
```




    (array([1, 3]),)




```python
# Find the number of civilian deaths in battles with less than 500 deaths
civ_deaths = civilian_deaths[few_civ_deaths]
civ_deaths
```




    array([233, 256])


