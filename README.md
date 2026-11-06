# EXP-3-Histogram Equalization Using OpenCV (Grayscale & Color Images)
## Name: Renick Fabian Rajesh
## Reg No: 212224230227
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
Read the image `dp.jpg` in grayscale format.

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
# Import required libraries
import cv2
import numpy as np
import matplotlib.pyplot as plt



# Read the image in grayscale format
img = cv2.imread('dp.jpg',cv2.IMREAD_GRAYSCALE)

# Display the grayscale image.
plt.imshow(img, cmap='gray')
plt.title('original_image')
plt.show()

```

<img width="371" height="412" alt="image" src="https://github.com/user-attachments/assets/213f0f80-cc15-4964-81ba-c717a3f965e5" />


```

# Plot the histogram of the grayscale image
plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()

```

<img width="572" height="411" alt="image" src="https://github.com/user-attachments/assets/8f45a3a4-1542-4b13-ad56-730447e6bdaf" />


```
# Perform histogram equalization
img_eq = cv2.equalizeHist(img)
plt.hist(img_eq.ravel(), 256, range = [0, 256]); 
plt.title('Equalized Histogram')

```

<img width="571" height="435" alt="image" src="https://github.com/user-attachments/assets/86cb14f2-6aca-487e-9dd3-b9d13adfe932" />


```
# Display [1] the Original Image (Gray Image) and its Histogram, and [2] the Enhanced Image and its Histogram using a 2×2 layout in Matplotlib.
plt.imshow(img_eq, cmap='gray')
plt.title('original image')
plt.show()
```

<img width="376" height="422" alt="image" src="https://github.com/user-attachments/assets/546ae9a1-b530-4910-824e-1501121d61b4" />


```
# Read the colorgiven dp.jpg image.

img = cv2.imread('dp.jpg', cv2.IMREAD_COLOR)
plt.subplot(121); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')

```

<img width="293" height="363" alt="image" src="https://github.com/user-attachments/assets/0596d5b2-e04f-4ae1-9fcf-4b75a006d6fb" />


```
# Plot the histogram of colour image

plt.subplot(223); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')


```

<img width="302" height="237" alt="image" src="https://github.com/user-attachments/assets/0d2800c2-ae61-47d6-8ac2-96c75026d7f9" />


```

# Convert to HSV.

img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)



# Perform histogram equalization
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
plt.subplot(224); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')

```

<img width="336" height="252" alt="image" src="https://github.com/user-attachments/assets/09447cab-ee92-4263-8ef9-8e3b3bcde94c" />


```
# Convert back to BGR format
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)



# Display
plt.figure(figsize = [12,10])
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')

```

<img width="807" height="422" alt="image" src="https://github.com/user-attachments/assets/0a2b6a60-5597-4f3a-a506-a4e2cf213b61" />


---

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
