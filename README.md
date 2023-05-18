# Thresholding of Images
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
```
Developed by: Parshwanath M
Register Number: 212221230073
```

```
# Load the necessary packages
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale
image = cv2.imread("picture (1).jpg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("picture (1).jpg",0)

# Use Global thresholding to segment the image
ret,thresh_img1 = cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)

# Use Adaptive thresholding to segment the image
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

# Use Otsu's method to segment the image 
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Display the results
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
for i in range(0,9):
    plt.figure(figsize=(5,5))
    plt.subplot(1,2,1)
    plt.title("Original Image")    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()
```

## Output

### Original Image
![9 1](https://github.com/parsh2004/Thresholding/assets/95388047/951b13af-9509-44ea-8948-b40e8a2b05f8)
### Global Thresholding
![9 2](https://github.com/parsh2004/Thresholding/assets/95388047/7758e224-482f-4f00-b439-7419e6d510be)

![9 3](https://github.com/parsh2004/Thresholding/assets/95388047/5ce2b19b-e394-4051-aaeb-e0bc0e155e86)

![9 4](https://github.com/parsh2004/Thresholding/assets/95388047/b9c122d3-11c5-4d26-a313-ae4562c67bac)

![9 5](https://github.com/parsh2004/Thresholding/assets/95388047/7f07c101-5795-451b-bc7e-d2fa530cc2cc)

![9 6](https://github.com/parsh2004/Thresholding/assets/95388047/7e02d3a8-b70b-4fe0-9a80-ce78b928686a)

### Adaptive Thresholding
![9 7](https://github.com/parsh2004/Thresholding/assets/95388047/af47902f-9578-4b77-9ca4-bef7db442b7d)

![9 8](https://github.com/parsh2004/Thresholding/assets/95388047/d6191a56-cb2b-4e5b-bb4c-f5d1bcbfdcf8)

### Optimum Global Thesholding using Otsu's Method
![9 9](https://github.com/parsh2004/Thresholding/assets/95388047/82087ab0-8bfd-4836-bc9e-506e05b1e63c)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
