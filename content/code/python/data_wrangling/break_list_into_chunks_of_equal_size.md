---
title: "Break A List Into N-Sized Chunks"
author: "Chris Albon"
date: 2017-12-20T11:53:49-07:00
description: "Break a list into n-sized chunks."
type: technical_note
draft: false
aliases: [/python/data_wrangling/break_list_into_chunks_of_equal_size/]
aliases:
    - /python/break_list_into_chunks_of_equal_size.html
---
In this snippet we take a list and break it up into n-size chunks. This is a very common practice when dealing with APIs that have a maximum request size.

Credit for this nifty function goes to Ned Batchelder who [posted it on StackOverflow](http://stackoverflow.com/questions/312443/how-do-you-split-a-list-into-evenly-sized-chunks-in-python).


```python
# Create a list of first names
first_names = ['Steve', 'Jane', 'Sara', 'Mary','Jack','Bob', 'Bily', 'Boni', 'Chris','Sori', 'Will', 'Won','Li']
```


```python
# Create a function called "chunks" with two arguments, l and n:
def chunks(l, n):
    # For item i in a range that is a length of l,
    for i in range(0, len(l), n):
        # Create an index range for l of n items:
        yield l[i:i+n]
```


```python
# Create a list that from the results of the function chunks:
list(chunks(first_names, 5))
```




    [['Steve', 'Jane', 'Sara', 'Mary', 'Jack'],
     ['Bob', 'Bily', 'Boni', 'Chris', 'Sori'],
     ['Will', 'Won', 'Li']]


