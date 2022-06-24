### EX NO : 09
### DATE  : 26.05.2022
# <p align="center">Thresholding</p>
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
<br/>
<br/>

## PROGRAM:
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image=cv2.imread("hinata.jpg",1)
image=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray=cv2.imread("hinata.jpg",0)
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
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
![1](https://user-images.githubusercontent.com/75235488/169489939-95bbf87a-d180-4907-af8e-56579e8c2c58.png)

### Global Thresholding

![2](https://user-images.githubusercontent.com/75235488/169490144-49a0d81d-8f35-4bfb-8d3a-27fbec344ef7.png)
![3](https://user-images.githubusercontent.com/75235488/169490172-aa90832a-0d81-4f03-975b-c9f780fb68dd.png)
![4](https://user-images.githubusercontent.com/75235488/169490269-3fd03cec-ce27-46fb-b35b-829c89358bd8.png)
![5](https://user-images.githubusercontent.com/75235488/169490290-e9556294-a0d6-4715-b832-060380be3c1c.png)
![6](https://user-images.githubusercontent.com/75235488/169490308-80744e5a-46c6-4d8a-89ff-fb22dd06fd0c.png)

<br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/>

### Adaptive Thresholding

![7](https://user-images.githubusercontent.com/75235488/169489987-85cfb06d-38fe-421a-bfbe-87f535270454.png)
![8](https://user-images.githubusercontent.com/75235488/169490001-9fdc9a27-a74a-479e-994d-30573249dfd9.png)


### Optimum Global Thesholding using Otsu's Method

![9](https://user-images.githubusercontent.com/75235488/169489969-d55d4643-1c7d-45dc-95fe-5c5a9db52b08.png)



## RESULT:
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
