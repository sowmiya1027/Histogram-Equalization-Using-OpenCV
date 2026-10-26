# Experiment - 3: Histogram-of-an-images
# Name: Sowmiya R
# Register Number: 212225040420


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


import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('sv.jpeg', cv2.IMREAD_GRAYSCALE)

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


## Output

### Input Grayscale Image
<img width="758" height="551" alt="image" src="https://github.com/user-attachments/assets/fa67d2c8-f374-4875-b601-4717c0059db7" />


### Input Grayscale Image Range
<img width="397" height="545" alt="image" src="https://github.com/user-attachments/assets/e319c2d1-c5a6-4289-83b1-a8f32c8ce40f" />


### Input Grayscale Image Equalized Histogram
<img width="746" height="555" alt="image" src="https://github.com/user-attachments/assets/dd523554-6b75-4872-a0a4-bc1cf677a3f1" />



### Original Image
<img width="418" height="537" alt="image" src="https://github.com/user-attachments/assets/17d122d3-939d-4802-8e03-d8ddf3f65e20" />



### Equalized Image

<img width="416" height="541" alt="image" src="https://github.com/user-attachments/assets/30a0ecf1-f1ed-46b6-ba24-cc08bb679de6" />

### Equalized Histogram
<img width="797" height="552" alt="image" src="https://github.com/user-attachments/assets/7e4050d6-0c17-4086-a440-8028409baa51" />


### Final Output of Original Image and Equalized 
<img width="1367" height="463" alt="image" src="https://github.com/user-attachments/assets/978c605d-9b0c-449c-8207-d680f78f7c63" />


### Final Output of Original Image and its Histogram Equalized

<img width="1392" height="516" alt="image" src="https://github.com/user-attachments/assets/cb0a40c8-3385-48d5-ad05-b9f121361cdb" />

## Result

Thus, the histogram showing the frequency of pixel intensities ranging from 0 to 255 was obtained for the grayscale image and the color image using OpenCV.
