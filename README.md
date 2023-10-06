# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the necessary packages.

### Step2:
Read the Image and convert to grayscale.

### Step3:
Use Global thresholding to segment the image.

### Step4:
Use Adaptive thresholding to segment the image.

### Step5:
Use Otsu's method to segment the image.

### Step5:
Display the results.

## Program

```
Developed by: Dharini PV
Register No: 212222240024
```
# Load the necessary packages
```python
import numpy as np
import matplotlib.pyplot as plt
import cv2
```
# Read the Image and convert to grayscale
```python
image = cv2.imread("cutes.jpeg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("cutes.jpeg",0)
```

# Use Global thresholding to segment the image
```python
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```

# Use Adaptive thresholding to segment the image
```python
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```

# Use Otsu's method to segment the image 
```python
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```

# Display the results
```python
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
for i in range(0,9):
    plt.figure(figsize=(10,10))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()
```
## Output

### Original Image
![Screenshot from 2023-10-07 00-36-17](https://github.com/DHARINIPV/THRESHOLDING/assets/119400845/7c0256f1-16bd-4ec1-8392-d86e55a027ad)

### Global Thresholding
![Screenshot from 2023-10-07 00-37-05](https://github.com/DHARINIPV/THRESHOLDING/assets/119400845/4bd21a62-eb1e-44b5-a16d-9b43ef8fe43f)
![Screenshot from 2023-10-07 00-37-30](https://github.com/DHARINIPV/THRESHOLDING/assets/119400845/520a9b33-09e7-44c0-a7eb-697794160786)
![Screenshot from 2023-10-07 00-37-49](https://github.com/DHARINIPV/THRESHOLDING/assets/119400845/9c1087fa-2bd3-4cd3-bf3b-88cec99b8190)
![Screenshot from 2023-10-07 00-38-09](https://github.com/DHARINIPV/THRESHOLDING/assets/119400845/a72b90d0-b3c7-4f3d-9975-d1fc99f667d6)
![Screenshot from 2023-10-07 00-38-29](https://github.com/DHARINIPV/THRESHOLDING/assets/119400845/bd0abb96-309e-4877-a778-c89e78971534)

### Adaptive Thresholding
![Screenshot from 2023-10-07 00-39-24](https://github.com/DHARINIPV/THRESHOLDING/assets/119400845/d6419e7b-4dc2-49b7-8c9c-95732232c659)
![Screenshot from 2023-10-07 00-39-47](https://github.com/DHARINIPV/THRESHOLDING/assets/119400845/4abc2aac-197c-4c65-b47d-7534fe5ffe3c)

### Optimum Global Thesholding using Otsu's Method
![Screenshot from 2023-10-07 00-38-59](https://github.com/DHARINIPV/THRESHOLDING/assets/119400845/178dd974-f4ba-44a2-b384-71a0f5d91938)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

