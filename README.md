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

### Step 6:
Display the results.

## Program

```
#Developed by: Sithi Hajara I
#Register no: 21221230102
```

# Load the necessary packages
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

# Read the Image and convert to grayscale
```
in_img=cv2.imread('suzume.PNG')
in_img2=cv2.imread('suzume2.PNG')

in_img= cv2.resize(in_img, (461,250))
in_img2= cv2.resize(in_img2, (463,284))

gray_img = cv2.cvtColor(in_img,cv2.COLOR_BGR2GRAY)
gray_img2 = cv2.cvtColor(in_img2,cv2.COLOR_BGR2GRAY)
```
# Use Global thresholding to segment the image
```
# cv2.threshold(image, threshold_value, max_val, thresholding_technique)
ret,thresh_img1=cv2.threshold(gray_img,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(gray_img,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(gray_img,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(gray_img,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(gray_img,100,255,cv2.THRESH_TRUNC)
```

# Use Adaptive thresholding to segment the image
```
# cv2.adaptiveThreshold(source, max_val, adaptive_method, threshold_type, blocksize, constant)
thresh_img6=cv2.adaptiveThreshold(gray_img2,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img7=cv2.adaptiveThreshold(gray_img2,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```

# Use Otsu's method to segment the image 
```
# cv2.threshold(img,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
ret,thresh_img8=cv2.threshold(gray_img2,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
# Display the results

```
cv2.imshow('original image',in_img)
cv2.imshow('original image(second)',in_img2)

cv2.imshow('original image(gray)',gray_img)
cv2.imshow('original image(gray)(second)',gray_img2)

cv2.imshow('binary threshold',thresh_img1)
cv2.imshow('binary-inverse threshold',thresh_img2)
cv2.imshow('to-zero threshold',thresh_img3)
cv2.imshow('to-zero-inverse threshold',thresh_img4)
cv2.imshow('truncate threshold',thresh_img5)

cv2.imshow('mean adaptive threshold',thresh_img6)
cv2.imshow('gaussian adaptive threshold',thresh_img7)

cv2.imshow('otsu\'s threshold',thresh_img8)

cv2.waitKey(0)
cv2.destroyAllWindows()

```
## Output

### Original Image
![Screenshot 2023-04-29 114836](https://user-images.githubusercontent.com/94219582/236668709-4afc9bff-ff73-4b2e-9f61-1909b5879ab5.png)

### Global Thresholding
![Screenshot 2023-04-29 115038](https://user-images.githubusercontent.com/94219582/236669049-61ea7539-3006-48b8-ab4e-43d21c7fc253.png)
![Screenshot 2023-05-07 145511](https://user-images.githubusercontent.com/94219582/236669641-3ffdfca6-5f53-4607-a945-62fe191586b9.png)

### Adaptive Thresholding
![Screenshot 2023-05-07 150424](https://user-images.githubusercontent.com/94219582/236669825-da6f39f5-fa3b-4b8f-9241-7fcdf9fe790c.png)

![Screenshot 2023-05-07 150516](https://user-images.githubusercontent.com/94219582/236669836-bf13d75c-627f-4863-9278-2d71d527ce65.png)

### Optimum Global Thesholding using Otsu's Method
![image](https://user-images.githubusercontent.com/94219582/236668932-278308e0-ba68-4b77-a98d-a5aea30b8c2e.png)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

