# DIPT-EXP-3
# EXPERIMENT - 3 - Histogram Equalization Using OpenCV (Grayscale & Color Images)
# Aim:
To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

The program performs the following operations:

Read and display a grayscale image

Plot histogram of the grayscale image

Apply histogram equalization on grayscale image

Read and display a color image

Plot histogram of B, G, R channels

Convert image to HSV color space

Apply histogram equalization on the Value (V) channel

Convert the enhanced image back to BGR format

Display original and enhanced images with histograms

Software Used
Anaconda – Python 3.7

Jupyter Notebook / VS Code

OpenCV (cv2)

NumPy

Matplotlib

# Algorithm:
Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

Step 2:
Read the image parrot.jpg in grayscale format.

Step 3:
Display the grayscale image and plot its histogram.

Step 4:
Apply histogram equalization using cv2.equalizeHist() to enhance contrast.

Step 5:
Display original grayscale image, its histogram, enhanced image, and its histogram using a 2 × 2 grid.

Step 6:
Read the same image in color format.

Step 7:
Split the image into B, G, R channels and plot their histograms.

Step 8:
Convert the image from BGR to HSV color space.

Step 9:
Apply histogram equalization on the V (Value) channel.

Step 10:
Merge the channels and convert the image back to BGR format.

Step 11:
Display original color image, histogram, enhanced image, and enhanced histogram using a 2 × 2 grid.


# Program:
Developed By: Abhinav Guru R
Register No: 212225040009
1. Import the required libraries and read the grayscale image.
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('game.jpg', cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('Original GrayScale Image')
plt.show()
```
2. Plot the histogram of the grayscale image
```
plt.hist(img.ravel(), 256, range=[0,256])
plt.title('Original GrayScale Image Histogram')
plt.show()
```
3. Apply histogram equalization.
```
img_eq = cv2.equalizeHist(img)
```
4. Display the histogram of the equalized image.
```
plt.hist(img_eq.ravel(), 256, range=[0,256])
plt.title('Equalized Histogram')
plt.show()
```
5. Display the equalized grayscale image.
```
plt.imshow(img_eq, cmap='gray')
plt.title('Equalized Image')
plt.show()
```
6. Read the image in color mode and convert to HSV.
```
img = cv2.imread('game.jpg', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
```
7. Apply histogram equalization to the V channel.
```
img_hsv[:, :, 2] = cv2.equalizeHist(img_hsv[:, :, 2])
```
8. Convert the enhanced HSV image back to BGR.
```
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
```
9. Display the original and equalized color images.
```
plt.subplot(121)
plt.imshow(img[:, :, ::-1])
plt.title('Original Color Image')

plt.subplot(122)
plt.imshow(img_eq[:, ::-1])
plt.title('Equalized Image')

plt.show()
```
10. Display the original and equalized images along with their histograms.
```
plt.figure(figsize=[12,10])

plt.subplot(221)
plt.imshow(img[:, :, ::-1])
plt.title('Original Color Image')

plt.subplot(222)
plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Image')

plt.subplot(223)
plt.hist(img.ravel(), 256, range=[0,256])
plt.title('Original Histogram')

plt.subplot(224)
plt.hist(img_eq.ravel(), 256, range=[0,256])
plt.title('Histogram Equalized')

plt.show()
```

# OUTPUT:
<Figure size 640x480 with 1 Axes><img width="314" height="434" alt="image" src="https://github.com/user-attachments/assets/a6a1cbc7-f001-4da3-b510-6f86cd995416" />
<BR>
<Figure size 640x480 with 1 Axes><img width="579" height="434" alt="image" src="https://github.com/user-attachments/assets/509b15ef-072e-407c-93da-964c1518bd05" />
<br>
<Figure size 640x480 with 1 Axes><img width="579" height="434" alt="image" src="https://github.com/user-attachments/assets/c88cc2f9-fb37-4a14-a731-e0719add5c94" />
<br>
<Figure size 640x480 with 1 Axes><img width="314" height="434" alt="image" src="https://github.com/user-attachments/assets/0de69ad8-2039-46b7-bbf8-149b5e42dc3b" />
<br>
<Figure size 2000x1000 with 2 Axes><img width="1148" height="414" alt="image" src="https://github.com/user-attachments/assets/ecfe9dfe-861d-4ac3-8f2d-d333b017aaae" />
<br>
<Figure size 1500x400 with 2 Axes><img width="1223" height="372" alt="image" src="https://github.com/user-attachments/assets/ca6d47cf-b843-44aa-9fda-c51f8395d8e6" />







# RESULT:
Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
