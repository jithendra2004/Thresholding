# Thresholding of Images
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

### step 6:

## Program

~~~

Developed by : V.A.Jithendra
Register Number : 212221230043
~~~~
```python
# Load the necessary packages

import cv2
import numpy as np
import matplotlib.pyplot as plt



# Read the Image and convert to grayscale
image=cv2.imread("image.jpg",1)
image=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray=cv2.imread("image.jpg",0)



# Use Global thresholding to segment the image

ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
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
![1](https://user-images.githubusercontent.com/94226297/170170536-8edc137b-bb84-4a04-8be5-e0d7bcb4dd75.png)

### Global Thresholding

![2](https://user-images.githubusercontent.com/94226297/170170543-c7621dfe-323b-46cf-8ec0-a67a13a3f60b.png)
![3](https://user-images.githubusercontent.com/94226297/170170558-066bc197-3872-4421-95c0-d50a4aa614bb.png)


![4](https://user-images.githubusercontent.com/94226297/170170576-f83db0ba-9ae1-4171-9b32-9acd47245041.png)
![5](https://user-images.githubusercontent.com/94226297/170170617-40146bfc-cfed-42da-97b5-4e44242f9823.png)

![6](https://user-images.githubusercontent.com/94226297/170170754-3c39aa6e-e4da-4b83-9767-9a6e5fa994ba.png)


### Adaptive Thresholding

![8](https://user-images.githubusercontent.com/94226297/170170822-becbd2c0-875e-42a3-a691-18bd550a9d6e.png)

![9](https://user-images.githubusercontent.com/94226297/170170830-a7e73967-c9c7-421b-9ff7-6f3e38226481.png)



### Optimum Global Thesholding using Otsu's Method

![7](https://user-images.githubusercontent.com/94226297/170170845-e5d0d914-f3c7-4406-a223-a4ce1f52064b.png)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

