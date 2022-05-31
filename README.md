# Thresholding
## AIM:
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## SOFTWARE REQUIRED:
1. Anaconda - Python 3.7
2. OpenCV

## ALGORITHM:

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

## PROGRAM:
```python
# Developed By   : GRAHAM STANES A
# Register Number: 212220230020
# Load the necessary packages
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale
image=cv2.imread("hinata.jpg",1)
image=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray=cv2.imread("hinata.jpg",0)

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
    plt.figure(figsize=(5,5))
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
## OUTPUT:

### Original Image and Grayscale Image
![image](https://user-images.githubusercontent.com/75235150/171138766-ce661a62-20fe-4906-a589-4f7b637e960a.png)

### Global Thresholding
![image](https://user-images.githubusercontent.com/75235150/171138826-2196f011-dd5f-409b-822f-7cce2f0153a8.png)
![image](https://user-images.githubusercontent.com/75235150/171138865-359b72b7-3708-4f01-83d4-f72786fa7038.png)
![image](https://user-images.githubusercontent.com/75235150/171138892-164a6fb5-062c-4ef6-9337-7a263ef63db0.png)
![image](https://user-images.githubusercontent.com/75235150/171138921-05ddb82c-c068-45c5-a4dd-81df1534ef0f.png)
![image](https://user-images.githubusercontent.com/75235150/171138949-28cca553-603e-42ac-b3a2-965ce7c8743b.png)

### Adaptive Thresholding
![image](https://user-images.githubusercontent.com/75235150/171138980-124f20b0-0cc1-432b-aed4-2248dab5f734.png)
![image](https://user-images.githubusercontent.com/75235150/171139017-a4f74201-f00d-412b-a267-e7f60c4be1ca.png)

### Optimum Global Thesholding using Otsu's Method
![image](https://user-images.githubusercontent.com/75235150/171139075-336f961c-ddb9-4829-824e-8880a1362e23.png)

## RESULT:
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
