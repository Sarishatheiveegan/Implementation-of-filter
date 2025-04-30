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


### 1. Smoothing Filters

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('DOREMON.png', cv2.IMREAD_GRAYSCALE)
plt.imshow(image, cmap='gray')
plt.title("Original Image")
plt.axis('off')
plt.show()
```
i) Using Averaging Filter
```python
kernel = np.ones((4, 4), np.float32) / 9
averaged_image = cv2.filter2D(image, -1, kernel)
plt.imshow(averaged_image, cmap='gray')
plt.title("Averaging Filter")
plt.axis('off')
plt.show()
```
ii) Using Weighted Averaging Filter
```python
weighted_kernel = np.array([[1, 2, 1], [2, 4, 2], [1, 2, 1]], np.float32)
weighted_kernel = weighted_kernel / weighted_kernel.sum()
weighted_image = cv2.filter2D(image, -1, weighted_kernel)
plt.imshow(weighted_image, cmap='gray')
plt.title("Weighted Averaging Filter")
plt.axis('off')
plt.show()
```
iii) Using Gaussian Filter
```python
gaussian_image = cv2.GaussianBlur(image, (3, 3), 1)
plt.imshow(gaussian_image, cmap='gray')
plt.title("Gaussian Filter")
plt.axis('off')
plt.show()
```

iv)Using Median Filter
```python
median_image = cv2.medianBlur(image, 3) 
plt.imshow(median_image, cmap='gray')
plt.title("Median Filter")
plt.axis('off')
plt.show()
```
### 2. Sharpening Filters
i) Using Laplacian Linear Kernal
```python
laplacian_kernel = np.array([[0, 1, 0], [1, -4, 1], [0, 1, 0]], np.float32)
laplacian_image = cv2.filter2D(image, -1, laplacian_kernel)
sharpened_laplacian_image = cv2.add(image, laplacian_image)
plt.imshow(sharpened_laplacian_image, cmap='gray')
plt.title("Laplacian Kernel")
plt.axis('off')
plt.show()
```
ii) Using Laplacian Operator
```python
laplacian_operator_image = cv2.Laplacian(image, cv2.CV_64F) 
laplacian_operator_image = cv2.convertScaleAbs(laplacian_operator_image) 
sharpened_operator_image = cv2.add(image, laplacian_operator_image)
plt.imshow(sharpened_operator_image, cmap='gray')
plt.title("Laplacian Operator")
plt.axis('off')
plt.show()
```
## OUTPUT:
### 1. Smoothing Filters
</br>
Original Image

![Screenshot 2025-04-30 153824](https://github.com/user-attachments/assets/e02838a9-8510-400a-8d24-96affe46bea7)



i) Using Averaging Filter
<br>
![Screenshot 2025-04-30 154545](https://github.com/user-attachments/assets/49915ff2-95c2-4568-acc5-a2638c18ae5f)


ii)Using Weighted Averaging Filter

![Screenshot 2025-04-30 153904](https://github.com/user-attachments/assets/55d8036b-6076-4441-b7ee-35074b116f9c)


iii)Using Gaussian Filter

![Screenshot 2025-04-30 153920](https://github.com/user-attachments/assets/2983dd94-6662-4dd0-8e83-c62500f6380a)


iv) Using Median Filter

![Screenshot 2025-04-30 153928](https://github.com/user-attachments/assets/1933283a-ba02-4613-a90e-15b7bf53f99e)



### 2. Sharpening Filters


i) Using Laplacian Kernal

![Screenshot 2025-04-30 153937](https://github.com/user-attachments/assets/e1613c69-820a-4d46-90f8-4fdf6f30436c)



ii) Using Laplacian Operator


![Screenshot 2025-04-30 153945](https://github.com/user-attachments/assets/37cd5d4d-7f43-4f39-981d-d5cfee7cae30)



## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
