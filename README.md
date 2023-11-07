# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding, and Otsu's thresholding using Python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Import necessary packages

### Step2:
Read the image

### Step3:
If the read image is a color image, convert it into a grayscale image

### Step4:
perform the threshold operation you want to do(global thresholding or adaptive thresholding or otsu's 
thresholding)

### Step5:
Display the Results


## Program
```
Developed By: Jeeva Abishake
Register No: 212221240018
```
```python
# Load the necessary packages

import cv2



# Read the Image and convert it to grayscale

img = cv2.imread('cat.jpeg',-1)
cv2.imshow('original_image',img)
cv2.waitKey(0)
cv2.destroyAllWindows
gray =cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
cv2.imshow('gray_image',gray)
cv2.waitKey(0)
cv2.destroyAllWindows


# Use Global thresholding to segment the image

ret,thresh_img1=cv2.threshold(gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(gray,100,255,cv2.THRESH_TRUNC)


# Use Adaptive thresholding to segment the image

thresh_img6=cv2.adaptiveThreshold(gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img7=cv2.adaptiveThreshold(gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)


# Use Otsu's method to segment the image 

ret,thresh_img8=cv2.threshold(gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)



# Display the results

image =[thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
for i in range(0,8):
    cv2.imshow('threshold_image',image[i])
    cv2.waitKey(0)
    cv2.destroyAllWindows



```
## Output

### Original Image
![cat](https://github.com/JEEVAABI/THRESHOLDING/assets/93427098/d44da6eb-514b-4e70-9d92-0b7d2afd6440)


### Global Thresholding
![gray](https://github.com/JEEVAABI/THRESHOLDING/assets/93427098/db29fe08-9984-41a6-8607-cbee9c62e658)
![th](https://github.com/JEEVAABI/THRESHOLDING/assets/93427098/c90055a5-652f-48b2-a508-3c21de9d3200)
![th2](https://github.com/JEEVAABI/THRESHOLDING/assets/93427098/50bc9f0d-7e92-4594-98b7-2774346ff021)

![thres](https://github.com/JEEVAABI/THRESHOLDING/assets/93427098/6e305238-b148-40b4-b598-720d50d25217)
![th4](https://github.com/JEEVAABI/THRESHOLDING/assets/93427098/9b4e480a-c6be-4fe0-a81a-b8b5012095fd)

![th5](https://github.com/JEEVAABI/THRESHOLDING/assets/93427098/00ff5bef-3ad3-4a50-8835-583623641bb0)



### Adaptive Thresholding
![th6](https://github.com/JEEVAABI/THRESHOLDING/assets/93427098/799611cc-5ef7-455b-ae3e-88cbdc9201b8)
![th7](https://github.com/JEEVAABI/THRESHOLDING/assets/93427098/65b7171a-c86d-45a3-8903-8f5b707cc91b)




### Optimum Global Thresholding using Otsu's Method
![th8](https://github.com/JEEVAABI/THRESHOLDING/assets/93427098/93bb0472-6357-4dba-a60d-a82c7ea4d60b)



## Result
Thus the images are segmented using global thresholding, adaptive thresholding, and optimum global thresholding using Python and OpenCV.

