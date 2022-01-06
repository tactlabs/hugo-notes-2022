---
title: "Generating Random Numbers With NumPy"
author: "Chris Albon"
date: 2017-12-20T11:53:49-07:00
description: "Generating random numbers with NumPy."
type: technical_note
draft: false
aliases: [/python/basics/generating_random_numbers_with_numpy/]
---
### Import Numpy


```python
import numpy as np
```

### Generate A Random Number From The Normal Distribution


```python
np.random.normal()
```




    0.5661104974399703



### Generate Four Random Numbers From The Normal Distribution


```python
np.random.normal(size=4)
```




    array([-1.03175853,  1.2867365 , -0.23560103, -1.05225393])



### Generate Four Random Numbers From The Uniform Distribution


```python
np.random.uniform(size=4)
```




    array([ 0.00193123,  0.51932356,  0.87656884,  0.33684494])



### Generate Four Random Integers Between 1 and 100


```python
np.random.randint(low=1, high=100, size=4)
```




    array([96, 25, 94, 77])


