---
title: "repr vs. str"
author: "Chris Albon"
date: 2017-12-20T11:53:49-07:00
description: "repr vs. str in Python."
type: technical_note
draft: false
aliases: [/python/basics/repr_vs_str/]
---
## Preliminaries


```python
import datetime
```

## Create A Simple Object


```python
class Regiment(object):

    def __init__(self, date=datetime.datetime.now()):
        self.date = date

    def __repr__(self):
        return date

    def __str__(self):
        return str(date)
```

`__repr__` is for the developer. It is string representation of the object and the code needed to reproduce the object. 

`__str__` is the output for the end user. It prints what the user wants to see.
