---
title: "Arithmetic Basics"
author: "Chris Albon"
date: 2017-12-20T11:53:49-07:00
description: "Arithmetic basics"
type: technical_note
draft: false
aliases: [/python/basics/arithmetic_basics/]
---
## Create some simulated variables


```python
x = 6
y = 9
```

## x plus y


```python
x + y
```




    15



## x minus y


```python
x - y
```




    -3



## x times y


```python
x * y
```




    54



## the remainder of x divided by y


```python
x % y
```




    6



## x divided by y


```python
x / y
```




    0.6666666666666666



## x divided by y (floor) (i.e. the quotient)


```python
x // y
```




    0



## x raised to the y power


```python
x ** y
```




    10077696



## x plus y, then divide by x


```python
(x + y) / x
```




    2.5



## Classics vs. floor division. This varies between 2.x and 3.x.

### Classic divison of 3 by 5


```python
3 / 5
```




    0.6



### Floor divison of 3 by 5. This means it truncates any remainder down the its "floor"


```python
3 // 5
```




    0


