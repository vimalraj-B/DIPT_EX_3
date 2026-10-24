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


<img width="384" height="234" alt="1" src="https://github.com/user-attachments/assets/2d3a94ac-87c3-4d82-bed0-eac247c8d96f" /><br>


<img width="397" height="290" alt="image" src="https://github.com/user-attachments/assets/134ce2ea-4b12-407d-a993-1596ef721511" /><br>


<img width="398" height="289" alt="image" src="https://github.com/user-attachments/assets/3549e3a2-74a4-4c33-aa4e-2359f7c43aa3" /><br>


<img width="405" height="236" alt="image" src="https://github.com/user-attachments/assets/8137f9db-daf1-4908-855e-fa7809ca3ce6" /><br>



### Step2 : Histogram Equalization for Color Images



<img width="395" height="232" alt="image" src="https://github.com/user-attachments/assets/e17ffc96-fdd0-4b29-a352-2546b8c4a787" /><br>


<img width="404" height="293" alt="image" src="https://github.com/user-attachments/assets/df6de317-de0e-41b1-a81c-716830f78c29" /><br>


<img width="745" height="200" alt="image" src="https://github.com/user-attachments/assets/623f7f6f-20ca-4fd2-a99a-9b5f39cbb5c8" /><br>


<img width="739" height="216" alt="image" src="https://github.com/user-attachments/assets/33b632c7-a630-4b63-b895-63df0366ff9a" /><br>


### Result :

Thus , the Histogram equalization was successfully performed, improving the contrast of grayscale and color images.












            
