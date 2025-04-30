# Implementation-of-filter
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
## Step1
Import the required libraries.

## Step2
Convert the image from BGR to RGB.

## Step3
Apply the required filters for the image separately.

## Step4
Plot the original and filtered image by using matplotlib.pyplot.

## Step5
End the program.

## Program:
### Developed By   : MARINO SARISHA T
### Register Number: 212223240084
</br>

### 1. Smoothing Filters


import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('taj.webp', cv2.IMREAD_GRAYSCALE)
plt.imshow(image, cmap='gray')
plt.title("Original Image")
plt.axis('off')

i) Using Averaging Filter

kernel = np.ones((4, 4), np.float32) / 9
averaged_image = cv2.filter2D(image, -1, kernel)
plt.imshow(averaged_image, cmap='gray')
plt.title("Averaging Filter")
plt.axis('off')

ii) Using Weighted Averaging Filter

weighted_kernel = np.array([[1, 2, 1], [2, 4, 2], [1, 2, 1]], np.float32)
weighted_kernel = weighted_kernel / weighted_kernel.sum()
weighted_image = cv2.filter2D(image, -1, weighted_kernel)
plt.imshow(weighted_image, cmap='gray')
plt.title("Weighted Averaging Filter")
plt.axis('off')

iii) Using Gaussian Filter

gaussian_image = cv2.GaussianBlur(image, (3, 3), 1)
plt.imshow(gaussian_image, cmap='gray')
plt.title("Gaussian Filter")
plt.axis('off')



iv)Using Median Filter

median_image = cv2.medianBlur(image, 3) 
plt.imshow(median_image, cmap='gray')
plt.title("Median Filter")
plt.axis('off')




### 2. Sharpening Filters
i) Using Laplacian Linear Kernal

laplacian_kernel = np.array([[0, 1, 0], [1, -4, 1], [0, 1, 0]], np.float32)
laplacian_image = cv2.filter2D(image, -1, laplacian_kernel)
sharpened_laplacian_image = cv2.add(image, laplacian_image)
plt.imshow(sharpened_laplacian_image, cmap='gray')
plt.title("Laplacian Kernel")
plt.axis('off')


ii) Using Laplacian Operator

laplacian_operator_image = cv2.Laplacian(image, cv2.CV_64F) 
laplacian_operator_image = cv2.convertScaleAbs(laplacian_operator_image) 
sharpened_operator_image = cv2.add(image, laplacian_operator_image)
plt.imshow(sharpened_operator_image, cmap='gray')
plt.title("Laplacian Operator")
plt.axis('off')


## OUTPUT:
### 1. Smoothing Filters
</br>
Original Image

![Screenshot 2025-04-26 221055](https://github.com/user-attachments/assets/30423354-1e47-400a-ab37-049368ac0c30)


i) Using Averaging Filter
<br>
![image](https://github.com/user-attachments/assets/7d468330-b813-43d5-99c8-ee2705b76181)

ii)Using Weighted Averaging Filter
<br>
![image](https://github.com/user-attachments/assets/17ad219a-44fe-4681-a165-42ae07e926ca)


iii)Using Gaussian Filter
<br>
![image](https://github.com/user-attachments/assets/5efff4e0-1c1f-4f7f-bf11-e1ff85f90ad2)


iv) Using Median Filter
<br>

![image](https://github.com/user-attachments/assets/e9bf7412-b85e-4f54-bf1f-0581a98385ef)


### 2. Sharpening Filters


i) Using Laplacian Kernal

<br>

![image](https://github.com/user-attachments/assets/aeeea623-cf8a-43c4-9124-74bf5ba34b0f)


ii) Using Laplacian Operator

<br>

![image](https://github.com/user-attachments/assets/e8cc7c7e-5bd8-4dd1-a8d2-2816e8d6b18c)


## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
