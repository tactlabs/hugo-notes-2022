---
title: "Hard Wrapping Text"
author: "Chris Albon"
date: 2017-12-20T11:53:49-07:00
description: "Hard wrapping text using pandas."
type: technical_note
draft: false
aliases: [/python/basics/hard_wrapping_text/]
---
## Preliminaries


```python
import textwrap
```

## Create Text


```python
# Create some text
excerpt = 'Then there was the bad weather. It would come in one day when the fall was over. We would have to shut the windows in the night against the rain and the cold wind would strip the leaves from the trees in the Place Contrescarpe. The leaves lay sodden in the rain and the wind drove the rain against the big green autobus at the terminal and the Café des Amateurs was crowded and the windows misted over from the heat and the smoke inside.'
```

## Hard Wrap Text


```python
# Hard wrap the excerpt at 50 characters
print(textwrap.fill(excerpt, 50))
```

    Then there was the bad weather. It would come in
    one day when the fall was over. We would have to
    shut the windows in the night against the rain and
    the cold wind would strip the leaves from the
    trees in the Place Contrescarpe. The leaves lay
    sodden in the rain and the wind drove the rain
    against the big green autobus at the terminal and
    the Café des Amateurs was crowded and the windows
    misted over from the heat and the smoke inside.

