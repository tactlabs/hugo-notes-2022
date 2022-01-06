---
title: "Meanshift Clustering"
author: "Chris Albon"
date: 2017-12-20T11:53:49-07:00
description: "How to conduct meanshift clustering in scikit-learn."
type: technical_note
draft: false
aliases: [/machine_learning/clustering/meanshift_clustering/]
---
<a alt="Meanshift Clustering" href="https://machinelearningflashcards.com">
    <img src="/images/machine_learning_flashcards/Meanshift_Clustering_By_Analogy_print.png" class="flashcard center-block">
</a>

## Preliminaries


```python
# Load libraries
from sklearn import datasets
from sklearn.preprocessing import StandardScaler
from sklearn.cluster import MeanShift
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

## Conduct Meanshift Clustering

`MeanShift` has two important parameters we should be aware of. First, `bandwidth` sets radius of the area (i.e. kernel) an observation uses to determine the direction to shift. In our analogy, bandwidth was how far a person could see through the fog. We can set this parameter manually, however by default a reasonable bandwidth is estimated automatically (with a significant increase in computational cost). Second, sometimes in meanshift there are no other observations within an observation's kernel. That is, a person on our football cannot see a single other person. By default, `MeanShift` assigns all these "orphan" observations to the kernel of the nearest observation. However, if we want to leave out these orphans, we can set `cluster_all=False` wherein orphan observations the label of `-1`.


```python
# Create meanshift object
clt = MeanShift(n_jobs=-1)

# Train model
model = clt.fit(X_std)
```
