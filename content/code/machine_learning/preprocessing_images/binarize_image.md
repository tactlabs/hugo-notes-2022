---
title: "Binarize Images"
author: "Chris Albon"
date: 2017-12-20T11:53:49-07:00
description: "How to binarize images using OpenCV in Python."
type: technical_note
draft: false
aliases: [/machine_learning/preprocessing_images/binarize_image/]
---
## Preliminaries


```python
# Load image
import cv2
import numpy as np
from matplotlib import pyplot as plt
```

## Load Image As Greyscale


```python
# Load image as greyscale
image_grey = cv2.imread('images/plane_256x256.jpg', cv2.IMREAD_GRAYSCALE)
```

## Apply Adaptive Thresholding


```python
# Apply adaptive thresholding
max_output_value = 255
neighorhood_size = 99
subtract_from_mean = 10
image_binarized = cv2.adaptiveThreshold(image_grey, 
                                        max_output_value, 
                                        cv2.ADAPTIVE_THRESH_GAUSSIAN_C, 
                                        cv2.THRESH_BINARY, 
                                        neighorhood_size, 
                                        subtract_from_mean)
```

## View Image


```python
# Show image
plt.imshow(image_binarized, cmap='gray'), plt.axis("off")
plt.show()
```


![png](binarize_image_8_0.png)

