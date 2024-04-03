# Implementation-of-Erosion-and-Dilation
## Aim
To implement Erosion and Dilation using Python and OpenCV.
## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
### Step1:
Import the image

### Step2:
Read the colour image and convert it into grayscale

### Step3:
Perform edge detection using canny

### Step4:
Define the kernel size for erosion and dilation

### Step5:
Display all images

## Program:

```
import cv2
import numpy as np
from matplotlib import pyplot as plt

#Read the color image

input_image_path = 'prema.jpg'
color_image = cv2.imread(input_image_path)

#Convert the color image to grayscale

gray_image=cv2.cvtColor(color_image, cv2.COLOR_BGR2GRAY)

#Perform edge detection using Canny

edges = cv2.Canny(gray_image, 100, 200) # you can adjust the thresholds as needed

#Define the kernel size for erosion and dilation

kernel_size = 5
kernel = np.ones((kernel_size, kernel_size), np. uint8)

#Perform erosion

erosion = cv2.erode(edges, kernel, iterations=1)

#Perform diiation

dilation = cv2.dilate(edges, kernel, iterations=1)

#Display all images

plt.figure(figsize=(15, 10))
plt.subplot(2, 3, 1)
plt.imshow(cv2.cvtColor(color_image, cv2.COLOR_BGR2RGB))
plt.title('Original Color Image')
plt.axis('on')
plt.subplot(2, 3, 2)
plt.imshow(gray_image, cmap="gray")
plt.title('Black and white Image')
plt.axis('on')
plt.subplot(2, 3, 3)
plt.imshow(edges, cmap='gray')
plt.title('Edge Segmentation')
plt.axis('on')
plt.subplot(2, 3, 4)
plt.imshow(erosion, cmap = 'gray')
plt.title('Erosion')
plt.axis('on')
plt.subplot(2, 3, 5)
plt.imshow(dilation, cmap='gray')
plt.title('Dilation')
plt.axis('on')
plt.show()

```
## Output:

![Screenshot 2024-04-02 112234](https://github.com/premalatha-sureshbabu/erosion-dilation/assets/120620842/dcd3495d-eac8-4e92-a4a5-9ab0efded1c3)


## Result
Thus the generated text image is eroded and dilated using python and OpenCV.
