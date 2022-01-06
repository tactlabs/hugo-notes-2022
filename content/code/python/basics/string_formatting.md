---
title: "String Formatting"
author: "Chris Albon"
date: 2017-12-20T11:53:49-07:00
description: "String formatting using Python."
type: technical_note
draft: false
aliases: [/python/basics/string_formatting/]
---
### Import the sys module


```python
import sys
```

### Print a string with 1 digit and one string.


```python
'This is %d %s bird!' % (1, 'dead')
```




    'This is 1 dead bird!'



### Print a dictionary based string


```python
'%(number)d more %(food)s' % {'number' : 1, 'food' : 'burger'}
```




    '1 more burger'



### Print a string about my laptop.


```python
'My {1[kind]} runs {0.platform}'.format(sys, {'kind': 'laptop'})
```




    'My laptop runs darwin'



## String Formatting Codes
- %s string
- %r repr string
- %c character (integer or string)
- %d decimal
- %i integer
- %x hex integer
- %X same as X but with uppercase
- %e floating point lowercase
- %E floating point uppercase
- %f floating point decimal lowercase
- %F floating point decimal uppercase
- %g floating point e or f
- %G floating point E or F
- %% literal %
