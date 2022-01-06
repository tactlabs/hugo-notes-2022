---
title: "Queues And Stacks"
author: "Chris Albon"
date: 2017-12-20T11:53:49-07:00
description: "Queues and stacks in Python."
type: technical_note
draft: false
aliases: [/python/basics/queues_and_stacks/]
---
## Preliminaries


```python
from collections import deque
```

## Make A Queue


```python
# Option 1: Make a queue
queue = deque(range(10))

# Option 2: Make a queue that, if full, discards any item at the 
# opposite end to where you added an item.
queue = deque(range(10), maxlen=10)
```

## Manipulate Queue


```python
# Append an item to the right

queue.append('A')

# View queue
queue
```




    deque([1, 2, 3, 4, 5, 6, 7, 8, 9, 'A'])




```python
# Append an item to the left

queue.appendleft('A')

# View queue
queue
```




    deque(['A', 1, 2, 3, 4, 5, 6, 7, 8, 9])




```python
# Count occurances of item
queue.count('A')

# View queue
queue
```




    deque(['A', 1, 2, 3, 4, 5, 6, 7, 8, 9])




```python
# Remove and return right-most item
queue.pop()

# View queue
queue
```




    deque(['A', 1, 2, 3, 4, 5, 6, 7, 8])




```python
# Remove and return left-most item
queue.popleft()


# View queue
queue
```




    deque([1, 2, 3, 4, 5, 6, 7, 8])




```python
# Insert item to the right of an item
queue.insert(2, 'A')

# View queue
queue
```




    deque([1, 2, 'A', 3, 4, 5, 6, 7, 8])




```python
# Reverse the queue
queue.reverse()

# View queue
queue
```




    deque([8, 7, 6, 5, 4, 3, 'A', 2, 1])




```python
# Delete all items
queue.clear()

# View queue
queue
```




    deque([])


