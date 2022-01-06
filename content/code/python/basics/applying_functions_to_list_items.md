---
title: "Applying Functions To List Items"
author: "Chris Albon"
date: 2017-12-20T11:53:49-07:00
description: "Applying Functions To List Items"
type: technical_note
draft: false
aliases: [/python/basics/applying_functions_to_list_items/]
---
### Create a list of regiment names


```python
regimentNames = ['Night Riflemen', 'Jungle Scouts', 'The Dragoons', 'Midnight Revengence', 'Wily Warriors']
```

## Using A For Loop

### Create a for loop goes through the list and capitalizes each


```python
# create a variable for the for loop results
regimentNamesCapitalized_f = []

# for every item in regimentNames
for i in regimentNames:
    # capitalize the item and add it to regimentNamesCapitalized_f
    regimentNamesCapitalized_f.append(i.upper())
    
# View the outcome
regimentNamesCapitalized_f
```




    ['NIGHT RIFLEMEN',
     'JUNGLE SCOUTS',
     'THE DRAGOONS',
     'MIDNIGHT REVENGENCE',
     'WILY WARRIORS']



## Using Map()

### Create a lambda function that capitalizes x


```python
capitalizer = lambda x: x.upper()
```

### Map the capitalizer function to regimentNames, convert the map into a list, and view the variable


```python
regimentNamesCapitalized_m = list(map(capitalizer, regimentNames)); regimentNamesCapitalized_m
```




    ['NIGHT RIFLEMEN',
     'JUNGLE SCOUTS',
     'THE DRAGOONS',
     'MIDNIGHT REVENGENCE',
     'WILY WARRIORS']



## Using List Comprehension

### Apply the expression x.upper to each item in the list called regiment names. Then view the output


```python
regimentNamesCapitalized_l = [x.upper() for x in regimentNames]; regimentNamesCapitalized_l
```




    ['NIGHT RIFLEMEN',
     'JUNGLE SCOUTS',
     'THE DRAGOONS',
     'MIDNIGHT REVENGENCE',
     'WILY WARRIORS']


