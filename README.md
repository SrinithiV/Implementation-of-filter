# Implementation-of-filter
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
</br>Import necessary libraries (cv2, NumPy, Matplotlib) for image loading, filtering, and visualization.
</br> 
### Step2
</br>Load the image using cv2.imread() and convert it to RGB format using cv2.cvtColor() for proper display in Matplotlib.
</br> 

### Step3
</br>Apply different filters:
1. Averaging Filter: Define an averaging kernel using np.ones() and apply it to the image using cv2.filter2D().
2. Weighted Averaging Filter: Define a weighted kernel (e.g., 3x3 Gaussian-like) and apply it with cv2.filter2D().
3. Gaussian Filter: Use cv2.GaussianBlur() to apply Gaussian blur.
4. Median Filter: Use cv2.medianBlur() to reduce noise.
5. Laplacian Operator: Use cv2.Laplacian() to apply edge detection.
</br> 

### Step4
</br>Display each filtered image using plt.subplot() and plt.imshow() for side-by-side comparison of the original and processed images.
</br> 

### Step5
</br>Save or show the images using plt.show() after applying each filter to visualize the effects of smoothing and sharpening.
</br> 

## Program:
### Developed By   : SRINITHI V
### Register Number: 212222110046

```Python
import cv2
import matplotlib.pyplot as plt
import numpy as np

image1 = cv2.imread("harry.jpg")
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

plt.figure(figsize=(7, 3))
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
```
### OUTPUT:
![Screenshot 2024-10-26 104202](https://github.com/user-attachments/assets/28c6c559-d082-49db-a9a5-9cacb3ef0541)

### 1. Smoothing Filters

i) Using Averaging Filter
```Python
kernel = np.ones((11, 11), np.float32) / 121
averaging_image = cv2.filter2D(image2, -1, kernel)

plt.figure(figsize=(7, 3))
plt.imshow(averaging_image)
plt.title("Averaging Filter Image")
plt.axis("off")
plt.show()
```
### OUTPUT:
![Screenshot 2024-10-26 104212](https://github.com/user-attachments/assets/d99145e5-c926-4f91-93fc-e48816ca3cb1)

ii) Using Weighted Averaging Filter
```Python
kernel1 = np.array([[1, 2, 1],
                    [2, 4, 2],
                    [1, 2, 1]]) / 16

weighted_average_image = cv2.filter2D(image2, -1, kernel1)
plt.figure(figsize=(7, 3))
plt.imshow(weighted_average_image)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()
```
### OUTPUT:
![Screenshot 2024-10-26 104238](https://github.com/user-attachments/assets/06db5955-3865-4675-a28a-55d8ffe2fe7c)

iii) Using Gaussian Filter
```Python
gaussian_blur = cv2.GaussianBlur(image2, (11, 11), 0)

plt.figure(figsize=(7, 3))
plt.imshow(gaussian_blur)
plt.title("Gaussian Filter")
plt.axis("off")
plt.show()
```
### OUTPUT:
![Screenshot 2024-10-26 104606](https://github.com/user-attachments/assets/aaed1d44-bd68-4ace-9ab7-f3122feddfb9)

iv)Using Median Filter
```Python
median_blur = cv2.medianBlur(image2, 11)

plt.figure(figsize=(7, 3))
plt.imshow(median_blur)
plt.title("Median Filter")
plt.axis("off")
plt.show()
```
### OUTPUT:
![Screenshot 2024-10-26 104621](https://github.com/user-attachments/assets/32c9d047-5d7a-4981-92a7-542e4e1b8e71)

### 2. Sharpening Filters
i) Using Laplacian Linear Kernal
```Python
sharpened_image = cv2.filter2D(image2, -1, kernel1)

plt.figure(figsize=(7, 3))
plt.imshow(sharpened_image)
plt.title("Sharpened Image (Laplacian Kernel)")
plt.axis("off")
plt.show()
```
### OUTPUT:
![Screenshot 2024-10-26 104636](https://github.com/user-attachments/assets/116da93c-ffc2-4667-8c52-b50a64a2b00d)

ii) Using Laplacian Operator
```Python
laplacian = cv2.Laplacian(image2, cv2.CV_64F)

plt.figure(figsize=(7, 3))
plt.imshow(laplacian, cmap='gray')
plt.title("Laplacian Operator Image")
plt.axis("off")
plt.show()
```
### OUTPUT:
![Screenshot 2024-10-26 104650](https://github.com/user-attachments/assets/e38aae90-1270-4f18-ad70-86867ec000ca)

## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
