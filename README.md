# Ex. No: 03 Histogram-of-an-Images
## Histogram of an Images
## Name: Rithesh S
## Reg. No: 212225220084

## Aim

To obtain a histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255. Also, write a Python program using OpenCV to perform histogram equalization.

## Software Required

- Anaconda - Python 3.7
- OpenCV
- NumPy
- Matplotlib

## Algorithm

### Step 1
Read the grayscale and color images using the `cv2.imread()` function.

### Step 2
Display the grayscale and color images using the `imshow()` function.

### Step 3
Use the `cv2.calcHist()` function to calculate the frequency of pixel intensities in the grayscale image.

### Step 4
Use the `cv2.calcHist()` function to calculate the histograms of the Blue, Green, and Red channels of the color image.

### Step 5
Plot and display the histograms of the grayscale image and color image.

## Program

**Developed By:** Rithesh S

**Register Number:** 212225220084

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('Rithesh.jpeg', cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()

plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()

img_eq = cv2.equalizeHist(img)

plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')

plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()

img = cv2.imread('sv.jpeg', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()

plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()

plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.show()

plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```

## Output

### Input Grayscale Image
<img width="362" height="531" alt="image" src="https://github.com/user-attachments/assets/ae2ecbad-87a9-4eb9-a309-9e695c770350" />


### Input Grayscale Image Range
<img width="787" height="522" alt="image" src="https://github.com/user-attachments/assets/3990a52b-bd27-4f74-a85c-2359ef3ea7a6" />


### Input Grayscale Image Equalized Histogram
<img width="848" height="547" alt="image" src="https://github.com/user-attachments/assets/b85d6376-7048-4d7c-8e34-3ef335df1bf0" />


### Histogram of Grayscale Image and Color Image Channels

### Original Image

<img width="407" height="540" alt="image" src="https://github.com/user-attachments/assets/e8ee29ef-e90d-4703-bf8c-1ba0fa47eabb" />

### Equalized Image

<img width="422" height="542" alt="image" src="https://github.com/user-attachments/assets/79a27ff4-6e44-4b88-8917-6ef4a9721b34" />

### Equalized Histogram
<img width="773" height="542" alt="image" src="https://github.com/user-attachments/assets/5eeb9fdc-0a95-4c3e-80d1-eeffcb49d1b7" />

### Final Output of Original Image and Equalized 
<img width="1357" height="487" alt="image" src="https://github.com/user-attachments/assets/a63e074b-67a3-4da5-8bcf-fbe9c8fa89cf" />


### Final Output of Original Image and its Histogram Equalized
<img width="1347" height="378" alt="image" src="https://github.com/user-attachments/assets/ff199b11-c755-4115-bec5-c4ed74fdf019" />


## Result

Thus, the histogram showing the frequency of pixel intensities ranging from 0 to 255 was obtained for the grayscale image and the color image using OpenCV.
