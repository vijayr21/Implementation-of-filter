# Implementation-of-filter
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
</br>
Import necessary libraries (cv2, NumPy, Matplotlib) for image loading, filtering, and visualization.
</br> 

### Step2
</br>
Load the image using cv2.imread() and convert it to RGB format using cv2.cvtColor() for proper display in Matplotlib.
</br> 

### Step3
</br>
Apply different filters:
    <br>1.Averaging Filter: Define an averaging kernel using np.ones() and apply it to the image using cv2.filter2D().
    <br>2.Weighted Averaging Filter: Define a weighted kernel (e.g., 3x3 Gaussian-like) and apply it with cv2.filter2D().
    <br>3.Gaussian Filter: Use cv2.GaussianBlur() to apply Gaussian blur.
    <br>4.Median Filter: Use cv2.medianBlur() to reduce noise.
    <br>5.Laplacian Operator: Use cv2.Laplacian() to apply edge detection.
</br> 

### Step4
</br>
Display each filtered image using plt.subplot() and plt.imshow() for side-by-side comparison of the original and processed images.
</br> 

### Step5
</br>
Save or show the images using plt.show() after applying each filter to visualize the effects of smoothing and sharpening.
</br> 

## Program:
### Developed By: VIJAY R
### Register Number: 212223240178

### 1. Smoothing Filters

i) Using Averaging Filter
```Python

import cv2
import matplotlib.pyplot as plt
import numpy as np
image1 = cv2.imread("cat.jpg")
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)
plt.figure(figsize=(10, 8))
plt.subplot(1, 2, 1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
```
ii) Using Weighted Averaging Filter
```Python
kernel = np.ones((11, 11), np.float32) / 121
averaging_image = cv2.filter2D(image2, -1, kernel)
plt.figure(figsize=(10, 8))
plt.subplot(1, 2, 2)
plt.imshow(averaging_image)
plt.title("Averaging Filter Image")
plt.axis("off")
plt.show()
```
iii) Using Gaussian Filter
```Python
kernel1 = np.array([[1, 2, 1],
                    [2, 4, 2],
                    [1, 2, 1]]) / 16

weighted_average_image = cv2.filter2D(image2, -1, kernel1)
plt.figure(figsize=(10, 8))
plt.subplot(1, 2, 2)
plt.imshow(weighted_average_image)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()
```
iv)Using Median Filter
```Python
gaussian_blur = cv2.GaussianBlur(image2, (11, 11), 0)
plt.figure(figsize=(10, 8))
plt.subplot(1, 2, 2)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()
```

### 2. Sharpening Filters
i) Using Laplacian Linear Kernal
```Python
sharpened_image = cv2.filter2D(gaussian_blur, -1, kernel1)
plt.figure(figsize=(10, 8))
plt.subplot(1, 2, 2)
plt.imshow(sharpened_image)
plt.title("Sharpened Image (Laplacian Kernel)")
plt.axis("off")
plt.show()
```
ii) Using Laplacian Operator
```Python
laplacian = cv2.Laplacian(image2, cv2.CV_64F)
plt.figure(figsize=(10, 8))
plt.subplot(1, 2, 2)
plt.imshow(laplacian, cmap='gray')
plt.title("Laplacian Operator Image")
plt.axis("off")
plt.show()
```

## OUTPUT:
### 1. Smoothing Filters
#### i) Using Averaging Filter
![image](https://github.com/user-attachments/assets/060d1ace-5ee5-4e56-9feb-e1bfda7289ad)


#### ii)Using Weighted Averaging Filter
![image](https://github.com/user-attachments/assets/e64f440c-b14d-46ef-b03f-2a63e0215531)


#### iii)Using Gaussian Filter
![image](https://github.com/user-attachments/assets/db45c764-b3f8-4393-9a3d-1a6beb90f6f0)


#### iv) Using Median Filter
![image](https://github.com/user-attachments/assets/f20ac856-715c-4170-8280-00e60343e68b)


### 2. Sharpening Filters
#### i) Using Laplacian Kernal
![image](https://github.com/user-attachments/assets/8a3efc58-fc55-48c7-9bf3-5eda383f0d40)


#### ii) Using Laplacian Operator
![image](https://github.com/user-attachments/assets/9b1cec65-f9e7-4d11-9d24-04e3cf5a610a)


## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
