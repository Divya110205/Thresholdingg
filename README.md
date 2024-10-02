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
Use Otsu's method to segment the image and display the results.

## Program
### Developed By :DIVYA.A
### Register Number : 212222230034
```python
# Load the necessary packages
import numpy as np
import matplotlib.pyplot as plt
import cv2

# Read the Image and convert to grayscale
image = cv2.imread('love.jpg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('love.jpg',0)

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
![Screenshot 2024-10-02 182117](https://github.com/user-attachments/assets/53ee486c-797d-4da4-8a6d-de46a153d822)


### Global Thresholding
![Screenshot 2024-10-02 182145](https://github.com/user-attachments/assets/eba839e0-074a-4e5a-8110-6a27224fd1a9)
![Screenshot 2024-10-02 182154](https://github.com/user-attachments/assets/8494d605-63f2-406f-8e04-4cd5058dfeba)
![Screenshot 2024-10-02 182202](https://github.com/user-attachments/assets/2d90240b-07a3-4e55-932f-de9115f49a80)
![Screenshot 2024-10-02 182211](https://github.com/user-attachments/assets/34d39b45-3118-442e-8ab0-d76cc98ccd11)
![Screenshot 2024-10-02 182217](https://github.com/user-attachments/assets/07d351c5-3a7f-48d3-b447-9b4ea30abfbd)

### Adaptive Thresholding
![Screenshot 2024-10-02 182226](https://github.com/user-attachments/assets/3213c5e7-a41c-4c9a-a6db-d6ad89a4463d)
![Screenshot 2024-10-02 182235](https://github.com/user-attachments/assets/f23ca339-965e-4524-81a0-a8ecfcc9b9a0)


### Optimum Global Thesholding using Otsu's Method
![Screenshot 2024-10-02 182246](https://github.com/user-attachments/assets/7b4abc39-b761-4357-a0df-68952579009f)



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
