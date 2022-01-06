---
title: "Remove Stop Words"
author: "Chris Albon"
date: 2017-12-20T11:53:49-07:00
description: "How to remove stop words from unstructured text data for machine learning in Python."
type: technical_note
draft: false
aliases: [/machine_learning/preprocessing_text/remove_stop_words/]
---
## Preliminaries


```python
# Load library
from nltk.corpus import stopwords

# You will have to download the set of stop words the first time
import nltk
nltk.download('stopwords')
```

    [nltk_data] Downloading package stopwords to
    [nltk_data]     /Users/chrisalbon/nltk_data...
    [nltk_data]   Package stopwords is already up-to-date!





    True



## Create Word Tokens


```python
# Create word tokens
tokenized_words = ['i', 'am', 'going', 'to', 'go', 'to', 'the', 'store', 'and', 'park']
```

## Load Stop Words


```python
# Load stop words
stop_words = stopwords.words('english')

# Show stop words
stop_words[:5]
```




    ['i', 'me', 'my', 'myself', 'we']



## Remove Stop Words


```python
# Remove stop words
[word for word in tokenized_words if word not in stop_words]
```




    ['going', 'go', 'store', 'park']


