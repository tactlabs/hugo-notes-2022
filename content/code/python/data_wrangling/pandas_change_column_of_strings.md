---
title: "Quickly Change A Column Of Strings In Pandas"
author: "Chris Albon"
date: 2017-12-20T11:53:49-07:00
description: "Quickly Change A Column Of Strings In Pandas."
type: technical_note
draft: false
aliases: [/python/data_wrangling/pandas_change_column_of_strings/]
---
Often I need or want to change the case of all items in a column of strings (e.g. BRAZIL to Brazil, etc.). There are many ways to accomplish this but I have settled on this one as the easiest and quickest.


```python
# Import pandas
import pandas as pd

# Create a list of first names
first_names = pd.Series(['Steve Murrey', 'Jane Fonda', 'Sara McGully', 'Mary Jane'])
```


```python
# print the column
first_names
```




    0    Steve Murrey
    1      Jane Fonda
    2    Sara McGully
    3       Mary Jane
    dtype: object




```python
# print the column with lower case
first_names.str.lower()
```




    0    steve murrey
    1      jane fonda
    2    sara mcgully
    3       mary jane
    dtype: object




```python
# print the column with upper case
first_names.str.upper()
```




    0    STEVE MURREY
    1      JANE FONDA
    2    SARA MCGULLY
    3       MARY JANE
    dtype: object




```python
# print the column with title case
first_names.str.title()
```




    0    Steve Murrey
    1      Jane Fonda
    2    Sara Mcgully
    3       Mary Jane
    dtype: object




```python
# print the column split across spaces
first_names.str.split(" ")
```




    0    [Steve, Murrey]
    1      [Jane, Fonda]
    2    [Sara, McGully]
    3       [Mary, Jane]
    dtype: object




```python
# print the column with capitalized case
first_names.str.capitalize()
```




    0    Steve murrey
    1      Jane fonda
    2    Sara mcgully
    3       Mary jane
    dtype: object



You get the idea. Many more string methods are [avaliable here](https://docs.python.org/3.5/library/stdtypes.html#string-methods)
