# EX.NO : 09
# DATE :

# <p align="center">Thresholding of Images</p>
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step 1:
Load the necessary packages.

### Step 2:
Read the Image and convert to grayscale.

### Step 3:
Use Global thresholding to segment the image.

### Step 4:
Use Adaptive thresholding to segment the image.

### Step 5:
Use Otsu's method to segment the image.

### Step 6:
Display the results.

## Program

```python
# Load the necessary packages

import cv2
import matplotlib.pyplot as plt
import numpy as np

# Read the Image and convert to grayscale

image=cv2.imread("new.jpg")
image1=cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)

# Use Global thresholding to segment the image

ret, thresh1 = cv2.threshold(image1,100,200,cv2.THRESH_BINARY)
ret, thresh2 = cv2.threshold(image1,100,200,cv2.THRESH_BINARY_INV)
ret, thresh3 = cv2.threshold(image1,100,200,cv2.THRESH_TRUNC)
ret, thresh4 = cv2.threshold(image1,100,200,cv2.THRESH_TOZERO)
ret, thresh5 = cv2.threshold(image1,100,200,cv2.THRESH_TOZERO_INV)


# Use Adaptive thresholding to segment the image

th1=cv2.adaptiveThreshold(image1,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
th2=cv2.adaptiveThreshold(image1,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

# Use Otsu's method to segment the image 

ret2,th3 = cv2.threshold(image1,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Display the results

titles=["Gray Image","THRESH_BINARY","THRESH_BINARY_INV","THRESH_TRUNC"
       ,"THRESH_TOZERO","THRESH_TOZERO_INV","ADAPTIVE_THRESH_MEAN_C","ADAPTIVE_THRESH_GAUSSIAN_C","OTSU"]
images=[image1,thresh1,thresh2,thresh3,thresh4,thresh5,th1,th2,th3]
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

### Original Image and Grayscale Image

<img width="465" alt="image" src="https://user-images.githubusercontent.com/75235554/169636388-25b3e8f1-3500-405c-9b58-b83b39b02704.png">

### Global Thresholding

<img width="469" alt="image" src="https://user-images.githubusercontent.com/75235554/169636399-e09729e3-d522-453d-bc48-747cdd0dde1a.png">

<img width="476" alt="image" src="https://user-images.githubusercontent.com/75235554/169636412-b0e6b58f-e339-4516-b6f1-be9f91056ce6.png">

<img width="488" alt="image" src="https://user-images.githubusercontent.com/75235554/169636418-c9644e6c-e139-4475-a0f7-3dbd1a69cc37.png">

### Adaptive Thresholding

<img width="467" alt="image" src="https://user-images.githubusercontent.com/75235554/169636424-c1c82417-6063-4dd4-b603-ab44366878f9.png">

### Optimum Global Thesholding using Otsu's Method

<img width="446" alt="image" src="https://user-images.githubusercontent.com/75235554/169636438-2712a17f-23ba-4b37-9412-3822d6fbfeed.png">

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

