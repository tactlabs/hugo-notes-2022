---
title: "Brute Force D20 Roll Simulator"
author: "Chris Albon"
date: 2017-12-20T11:53:49-07:00
description: "Brute force D20 roll simulator."
type: technical_note
draft: false
aliases: [/python/basics/brute_force_d20_simulator/]
---
This snippet is a completely inefficient simulator of a 20 sided dice. To create a "successful roll" the snippet has to generate  dozens of random numbers.

## Import random module


```python
import random
```

## Create a variable with a TRUE value


```python
rolling = True
```

## Create a while loop that rolls until the first digit is 2 or less and the second digit is 10 or less


```python
# while rolling is true
while rolling:
    # create x, a random number between 0 and 99
    x = random.randint(0, 99)
    # create y, a random number between 0 and 99
    y = random.randint(0, 99)
    # if x is less than 2 and y is between 0 and 10
    if x < 2 and 0 < y < 10:
        # Print the outcome
        print('You rolled a {0}{1}.'.format(x, y))
        # And set roll of False
        rolling = False
    # Otherwise
    else:
        # Try again
        print('Trying again.')
```

    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    Trying again.
    You rolled a 16.

