---
title: "DBSCAN Clustering"
author: "Chris Albon"
date: 2017-12-20T11:53:49-07:00
description: "How to conduct DBSCAN clustering in scikit-learn."
type: technical_note
draft: false
aliases: [/machine_learning/clustering/dbscan_clustering/]
images:
 - /images/machine_learning_flashcards/DBSCAN_print.png
---
<a alt="DBSCAN Clustering" href="https://machinelearningflashcards.com">
    <img src="/images/machine_learning_flashcards/DBSCAN_print.png" class="flashcard center-block">
</a>

## Preliminaries


```python
# Load libraries
from sklearn import datasets
from sklearn.preprocessing import StandardScaler
from sklearn.cluster import DBSCAN
```

## Load Iris Flower Dataset


```python
# Load data
iris = datasets.load_iris()
X = iris.data
```

## Standardize Features


```python
# Standarize features
scaler = StandardScaler()
X_std = scaler.fit_transform(X)
```

## Conduct DBSCAN Clustering

`DBSCAN` has three main parameters to set:

- `eps`: The maximum distance from an observation for another observation to be considered its neighbor.
- `min_samples`: The minimum number of observation less than `eps` distance from an observation for to be considered a core observation.
- `metric`: The distance metric used by `eps`. For example, `minkowski`, `euclidean`, etc. (note that if Minkowski distance is used, the parameter `p` can be used to set the power of the Minkowski metric)

If we look at the clusters in our training data we can see two clusters have been identified, `0` and `1`, while outlier observations are labeled `-1`.


```python
# Create meanshift object
clt = DBSCAN(n_jobs=-1)

# Train model
model = clt.fit(X_std)
```
