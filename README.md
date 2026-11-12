<img width="332" height="434" alt="download" src="https://github.com/user-attachments/assets/baf4e879-ac0e-4990-8c49-232a26163be8" /># EXP-3-Record-Histogram-processing

---

## Aim

To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

The program performs the following operations:

- Read and display a grayscale image  
- Plot histogram of the grayscale image  
- Apply histogram equalization on grayscale image  
- Read and display a color image  
- Plot histogram of B, G, R channels  
- Convert image to HSV color space  
- Apply histogram equalization on the Value (V) channel  
- Convert the enhanced image back to BGR format  
- Display original and enhanced images with histograms  

---

## Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib  

---

## Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the image `parrot.jpg` in grayscale format.

### Step 3:
Display the grayscale image and plot its histogram.

### Step 4:
Apply histogram equalization using `cv2.equalizeHist()` to enhance contrast.

### Step 5:
Display original grayscale image, its histogram, enhanced image, and its histogram using a 2 × 2 grid.

### Step 6:
Read the same image in color format.

### Step 7:
Split the image into B, G, R channels and plot their histograms.

### Step 8:
Convert the image from BGR to HSV color space.

### Step 9:
Apply histogram equalization on the V (Value) channel.

### Step 10:
Merge the channels and convert the image back to BGR format.

### Step 11:
Display original color image, histogram, enhanced image, and enhanced histogram using a 2 × 2 grid.

---

## Program
```
### Name: N V Chetan Satwik
### Reg. No: 212224240100

## Import Python necessary libraries
import cv2
import numpy as np
import matplotlib.pyplot as plt
## Histogram Equalization for Grayscale Images
img = cv2.imread('1sample.png', cv2.IMREAD_GRAYSCALE)
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
## Histogram Equalization for Color Images
img = cv2.imread('1sample.png', cv2.IMREAD_COLOR)
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
---

##  Output

<img width="332" height="434" alt="download" src="https://github.com/user-attachments/assets/0e7e50e4-6b93-40be-a840-ed6ea43fff39" />

<img width="579" height="434" alt="download" src="https://github.com/user-attachments/assets/34269163-493e-4265-a36e-d7ba5308e6c1" />

<img width="579" height="434" alt="download" src="https://github.com/user-attachments/assets/88382ea5-e1b4-4909-9315-4927ba318699" />


<img width="332" height="434" alt="download" src="https://github.com/user-attachments/assets/16efcd3d-d51b-4f35-8453-8beb39cf677d" />

<img width="332" height="434" alt="download" src="https://github.com/user-attachments/assets/a6d9da6b-2057-4b9f-a107-f181a14aa4de" />

<img width="579" height="434" alt="download" src="https://github.com/user-attachments/assets/fa373a7b-79e5-4a45-81d6-a9cf0dd97c5f" />


<img width="1163" height="414" alt="download" src="https://github.com/user-attachments/assets/0a863436-a79a-4014-96a7-b7f20b835738" />



<img width="1246" height="372" alt="download" src="https://github.com/user-attachments/assets/5641d3d2-7238-4210-99ef-290b4eabe6a5" />






### Grayscale Histogram Equalization

- Original grayscale image is displayed  
- Histogram of original grayscale image is plotted  
- Enhanced image after histogram equalization is displayed  
- Histogram of enhanced grayscale image shows improved contrast  

### Color Image Histogram Equalization

- Original color image is displayed  
- Histogram of B, G, R channels is plotted  
- Enhanced image after HSV-based equalization is displayed  
- Histogram of enhanced image shows better intensity distribution  

---

## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
