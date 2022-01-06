---
title: "Recursive Functions"
author: "Chris Albon"
date: 2017-12-20T11:53:49-07:00
description: "Recursive functions in Python."
type: technical_note
draft: false
aliases: [/python/basics/recursive_functions/]
---
## Simple factorial


```python
print(5*4*3*2*1)
```

    120


## Recursive function

The tell-tale sign of a recursive function is a function that calls itself


```python
# Create a function inputing n, that,
def factorial(n):
    # if n is less than or equal to 1,
    if n <= 1:
        # return n,
        return n

    # if not, return n multiplied by the output
    # of the factorial function of one less than n
    return n*factorial(n-1)

# run the function
factorial(5)
```




    120


