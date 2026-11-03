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
# Display the grayscale image.
plt.imshow(img, cmap='gray')
plt.title('original_image')
plt.show()

```

<img width="557" height="372" alt="image" src="https://github.com/user-attachments/assets/0c73180f-60c8-45bf-9fac-9efe002a0433" />

```

# Plot the histogram of the grayscale image
plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()

```

<img width="587" height="410" alt="image" src="https://github.com/user-attachments/assets/ea976333-70ec-491b-9572-08e1fb64a642" />

```
# Perform histogram equalization
img_eq = cv2.equalizeHist(img)
plt.hist(img_eq.ravel(), 256, range = [0, 256]); 
plt.title('Equalized Histogram')

```

<img width="607" height="435" alt="image" src="https://github.com/user-attachments/assets/d29ebf3f-6719-44cf-b1a8-2d26cd36bc84" />

```
# Display [1] the Original Image (Gray Image) and its Histogram, and [2] the Enhanced Image and its Histogram using a 2×2 layout in Matplotlib.
plt.imshow(img_eq, cmap='gray')
plt.title('original image')
plt.show()
```

<img width="615" height="387" alt="image" src="https://github.com/user-attachments/assets/7fc5978d-a2e4-4dab-9927-088a1321e39a" />

```
# Read the colorgiven parrot.jpg image.

img = cv2.imread('parrot.jpg', cv2.IMREAD_COLOR)
plt.subplot(121); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')

```

<img width="282" height="225" alt="image" src="https://github.com/user-attachments/assets/95c9c865-e55c-4a3e-875a-e2faa7f98f39" />

```
# Plot the histogram of colour image

plt.subplot(223); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')


```
<img width="315" height="246" alt="image" src="https://github.com/user-attachments/assets/f2432b46-4e04-45fd-b715-88560df1ea41" />

```

# Convert to HSV.

img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)



# Perform histogram equalization
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
plt.subplot(224); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')

```

<img width="357" height="250" alt="image" src="https://github.com/user-attachments/assets/dc881f01-155a-4ca3-a557-b89e685ccdbb" />

```
# Convert back to BGR format
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)



# Display
plt.figure(figsize = [12,10])
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')

```

<img width="952" height="361" alt="image" src="https://github.com/user-attachments/assets/95ec900f-aa66-425f-970f-cf83490f3c9d" />


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
