---
title: "Agglomerative Clustering"
author: "Chris Albon"
date: 2017-12-20T11:53:49-07:00
description: "How to conduct agglomerative clustering in scikit-learn. "
type: technical_note
draft: false
aliases: [/machine_learning/clustering/agglomerative_clustering/]
images:
 - /images/machine_learning_flashcards/Aggomerative_Clustering_print.png
---
<a alt="Agglomerative Clustering" href="https://machinelearningflashcards.com">
    <img src="/images/machine_learning_flashcards/Aggomerative_Clustering_print.png" class="flashcard center-block">
</a>

## Preliminaries


```python
# Load libraries
from sklearn import datasets
from sklearn.preprocessing import StandardScaler
from sklearn.cluster import AgglomerativeClustering
```

## Load Iris Flower Data


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

## Conduct Agglomerative Clustering

In scikit-learn, `AgglomerativeClustering` uses the `linkage` parameter to determine the merging strategy to minimize the 1) variance of merged clusters (`ward`), 2) average of distance between observations from pairs of clusters (`average`), or 3) maximum distance between observations from pairs of clusters (`complete`). 

Two other parameters are useful to know. First, the `affinity` parameter determines the distance metric used for `linkage` (`minkowski`, `euclidean`, etc.). Second, `n_clusters` sets the number of clusters the clustering algorithm will attempt to find. That is, clusters are successively merged until there are only `n_clusters` remaining.


```python
# Create meanshift object
clt = AgglomerativeClustering(linkage='complete', 
                              affinity='euclidean', 
                              n_clusters=3)

# Train model
model = clt.fit(X_std)
```

## Show Cluster Membership


```python
# Show cluster membership
model.labels_
```




    array([1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1,
           1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 2, 1, 1, 1, 1,
           1, 1, 1, 1, 0, 0, 0, 2, 0, 2, 0, 2, 0, 2, 2, 0, 2, 0, 0, 0, 0, 2, 2,
           2, 0, 0, 0, 0, 0, 0, 0, 0, 0, 2, 2, 2, 2, 0, 0, 0, 0, 2, 0, 2, 2, 0,
           2, 2, 2, 0, 0, 0, 2, 2, 0, 0, 0, 0, 0, 0, 2, 0, 0, 0, 0, 0, 0, 0, 0,
           0, 0, 0, 0, 2, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0,
           0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0])


