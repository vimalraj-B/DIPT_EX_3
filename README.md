# Experiment 3 : Histogram Processing

### Developed By : VIMALRAJ B
### Register Number : 212224230304

### Aim :
To study and implement histogram equalization for grayscale and color images using Python, OpenCV, NumPy, and Matplotlib to improve image contrast.

### Requirements :

* Jupyter Notebook / Anaconda Navigator
* Computer or laptop
* Sufficient storage space for Python libraries and image files
* Input image file: eagle.jpg

### Procedure
1. Import the required Python libraries: OpenCV (cv2), NumPy, and Matplotlib (pyplot).
2. Read the input image (eagle.jpg) in grayscale mode using OpenCV.
3. Display the original grayscale image using Matplotlib.
4. Calculate and plot the histogram of the original grayscale image using plt.hist().
5. Apply histogram equalization to the grayscale image using cv2.equalizeHist().
6. Display the equalized grayscale image and plot its histogram.
7. Read the input image again in color mode.
8. Convert the color image from BGR to HSV color space using cv2.cvtColor().
9. Apply histogram equalization to the Value (brightness) channel of the HSV image.
10. Convert the equalized HSV image back to BGR color space.
11. Display the original and equalized color images for comparison.
12. Plot the original and equalized image histograms to observe the changes in intensity distribution.

### Program : 

### Step1 : Histogram Equalization for Grayscale Images

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('eagle.jpg', cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()
```
```python
plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()
```
```python
img_eq = cv2.equalizeHist(img)

plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')
```

```python
plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()
```

### Step2 : Histogram Equalization for Color Images

```python
img = cv2.imread('eagle.jpg', cv2.IMREAD_COLOR)

img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)

img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])

img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)

plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()
```
```python
plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()
```
```python
plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.show()
```
```python
plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```

### Output : 

### Step1 : Histogram Equalization for Grayscale Images

<img width="248" height="290" alt="image" src="https://github.com/user-attachments/assets/f1f20661-8cdc-4eac-a191-90aa3f22eef3" />

<img width="403" height="295" alt="image" src="https://github.com/user-attachments/assets/55e6b508-ecb9-44a4-aa04-f9e538963c09" />

<img width="406" height="293" alt="image" src="https://github.com/user-attachments/assets/126653c6-d2e9-4063-a63b-50d48a71e573" />

<img width="249" height="299" alt="image" src="https://github.com/user-attachments/assets/db57a2ac-a653-41ce-910c-ba99e08bb3a5" />




### Step2 : Histogram Equalization for Color Images

<img width="254" height="293" alt="image" src="https://github.com/user-attachments/assets/2f619121-787f-4545-8897-01e6e110b57b" />

<img width="413" height="289" alt="image" src="https://github.com/user-attachments/assets/360fdb71-c785-4d69-9077-323a53cb0089" />

<img width="454" height="162" alt="image" src="https://github.com/user-attachments/assets/5a25990b-c49b-48cf-9288-4b847a8b3434" />

<img width="440" height="131" alt="image" src="https://github.com/user-attachments/assets/f77eede7-ca20-48c5-a684-c6b94f2b5ee4" />

















### Result :

Thus , the Histogram equalization was successfully performed, improving the contrast of grayscale and color images.












            
