## THRESHOLDING
### Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

### Software Required
1. Anaconda - Python 3.7
2. OpenCV

### Algorithm

#### Step1:
Load the necessary packages.
#### Step2:
Read the Image and convert to grayscale.
#### Step3:
Use Global thresholding to segment the image.
#### Step4:
Use Adaptive thresholding to segment the image.
#### Step5:
Use Otsu's method to segment the image and display the results.

### Program
```python
DEVELOPED BY: HARISH G
REGISTER NO: 212222243001
```
#### Load the necessary packages
```python
import numpy as np
import matplotlib.pyplot as plt
import cv2
```
#### Read the Image and convert to grayscale
```python
image = cv2.imread("dogncat.jpg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("dogncat.jpg",0)
```
#### Use Global thresholding to segment the image
```python
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
#### Use Adaptive thresholding to segment the image
```python
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
#### Use Otsu's method to segment the image 
```python
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
#### Display the results
```
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
### Output
#### Original Image
![Screenshot 2024-04-27 133547](https://github.com/Harish2404lll/Thresholdingg/assets/141472096/d3dea63e-3112-4e39-9c81-c16616f16943)

#### Global Thresholding
![Screenshot 2024-04-27 133558](https://github.com/Harish2404lll/Thresholdingg/assets/141472096/cd5ee0ed-1d3e-4c97-a97f-6f1589e7591f)
![Screenshot 2024-04-27 133609](https://github.com/Harish2404lll/Thresholdingg/assets/141472096/d0a59b33-7de4-4654-9d23-7cc0e7fa0541)
![Screenshot 2024-04-27 133623](https://github.com/Harish2404lll/Thresholdingg/assets/141472096/880b565d-6263-42bc-b997-9fbecc5a36c5)
![Screenshot 2024-04-27 133633](https://github.com/Harish2404lll/Thresholdingg/assets/141472096/da480887-d0ad-4370-b03c-fd280dc33aec)
![Screenshot 2024-04-27 133641](https://github.com/Harish2404lll/Thresholdingg/assets/141472096/104221de-8243-4bd5-8afe-ea0052d498cd)


#### Adaptive Thresholding
![Screenshot 2024-04-27 133706](https://github.com/Harish2404lll/Thresholdingg/assets/141472096/0e3925f9-1694-44a6-8402-07a1af084a10)
![Screenshot 2024-04-27 133701](https://github.com/Harish2404lll/Thresholdingg/assets/141472096/e7252428-b234-45eb-8f0d-f62ceb0f4a37)

#### Optimum Global Thesholding using Otsu's Method

![Screenshot 2024-04-27 133655](https://github.com/Harish2404lll/Thresholdingg/assets/141472096/da69f5c1-9910-45e9-9b62-63fabdebbba1)
### Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
