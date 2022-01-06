---
title: "Dimensionality Reduction On Sparse Feature Matrix"
author: "Chris Albon"
date: 2017-12-20T11:53:49-07:00
description: "How to conduct dimensionality reduction when the feature matrix is sparse using Python."
type: technical_note
draft: false
aliases: [/machine_learning/feature_engineering/dimensionality_reduction_on_sparse_feature_matrix/]
---
## Preliminaries


```python
# Load libraries
from sklearn.preprocessing import StandardScaler
from sklearn.decomposition import TruncatedSVD
from scipy.sparse import csr_matrix
from sklearn import datasets
import numpy as np
```

## Load Digits Data And Make Sparse


```python
# Load the data
digits = datasets.load_digits()

# Standardize the feature matrix
X = StandardScaler().fit_transform(digits.data)

# Make sparse matrix
X_sparse = csr_matrix(X)
```

## Create Truncated Singular Value Decomposition


```python
# Create a TSVD
tsvd = TruncatedSVD(n_components=10)
```

## Run Truncated Singular Value Decomposition


```python
# Conduct TSVD on sparse matrix
X_sparse_tsvd = tsvd.fit(X_sparse).transform(X_sparse)
```

## View Results


```python
# Show results
print('Original number of features:', X_sparse.shape[1])
print('Reduced number of features:', X_sparse_tsvd.shape[1])
```

    Original number of features: 64
    Reduced number of features: 10


## View Percent Of Variance Explained By New Features


```python
# Sum of first three components' explained variance ratios
tsvd.explained_variance_ratio_[0:3].sum()
```




    0.30039385372588506


