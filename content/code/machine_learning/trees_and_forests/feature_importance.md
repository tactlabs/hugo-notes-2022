---
title: "Feature Importance"
author: "Chris Albon"
date: 2017-12-20T11:53:49-07:00
description: "How to identify important features in random forest in scikit-learn."
type: technical_note
draft: false
aliases: [/machine_learning/trees_and_forests/feature_importance/]
images:
 - /images/machine_learning_flashcards/Feature_Importance_print.png
---
<a alt="Feature Importance" href="https://machinelearningflashcards.com">
    <img src="/images/machine_learning_flashcards/Feature_Importance_print.png" class="flashcard center-block">
</a>

## Preliminaries


```python
# Load libraries
from sklearn.ensemble import RandomForestClassifier
from sklearn import datasets
import numpy as np
import matplotlib.pyplot as plt
```

## Load Iris Flower Dataset


```python
# Load data
iris = datasets.load_iris()
X = iris.data
y = iris.target
```

## Train A Decision Tree Model


```python
# Create decision tree classifer object
clf = RandomForestClassifier(random_state=0, n_jobs=-1)

# Train model
model = clf.fit(X, y)
```

## View Feature Importance


```python
# Calculate feature importances
importances = model.feature_importances_
```

## Visualize Feature Importance


```python
# Sort feature importances in descending order
indices = np.argsort(importances)[::-1]

# Rearrange feature names so they match the sorted feature importances
names = [iris.feature_names[i] for i in indices]

# Create plot
plt.figure()

# Create plot title
plt.title("Feature Importance")

# Add bars
plt.bar(range(X.shape[1]), importances[indices])

# Add feature names as x-axis labels
plt.xticks(range(X.shape[1]), names, rotation=90)

# Show plot
plt.show()
```


![png](feature_importance_11_0.png)

