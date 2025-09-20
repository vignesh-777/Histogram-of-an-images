# Histogram-of-an-images
## Aim
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.
## NAME:vignesh R
## REG NO:212223240177
## Date No:
## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Read the gray and color image using imread()

### Step2:
Print the image using imshow().



### Step3:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### step4:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### Step5:
The Histogram of gray scale image and color image is shown.


## Program:
```python
# Developed By: vignesh  R
# Register Number: 212223240177
```
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the image in grayscale format.
img = cv2.imread('parrot.jpg', cv2.IMREAD_GRAYSCALE)

# Display the images.
plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()

# Display the images
plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()

# Equalize histogram
img_eq = cv2.equalizeHist(img)

# Display the images.
plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')

# Display the images.
plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()

# Read the color image.
img = cv2.imread('parrot.jpg', cv2.IMREAD_COLOR)
# Convert to HSV.
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)

# Perform histogram equalization only on the V channel, for value intensity.
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])

# Convert back to BGR format.
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()
plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()

# Display the images.
#plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.subplot(223); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(224); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()
# Display the histograms.
plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')

```
## Output:
### Input Grayscale Image and Color Image
<img width="552" height="396" alt="image" src="https://github.com/user-attachments/assets/df12d701-dd30-4c5f-ae41-d120210b46f5" />

<img width="552" height="396" alt="image" src="https://github.com/user-attachments/assets/3f254592-dcdf-4bbb-ae30-d84d62e9ef9c" />

### Histogram of Grayscale Image and any channel of Color Image

<img width="578" height="426" alt="image" src="https://github.com/user-attachments/assets/ca076139-00b7-4253-87a5-711c1643c01d" />


### Histogram Equalization of Grayscale Image.
<img width="1244" height="374" alt="image" src="https://github.com/user-attachments/assets/4914e3ab-175f-4699-a74f-1950cb38f8e1" />


## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
