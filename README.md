# EDGE-DETECTION
## Aim:
To perform edge detection using Sobel, Laplacian, and Canny edge detectors.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import all the necessary modules for the program.

### Step2:
Load a image using imread() from cv2 module.

### Step3:
Convert the image to grayscale

### Step4:
Using Sobel operator from cv2,detect the edges of the image.

### Step5:

Using Laplacian operator from cv2,detect the edges of the image and Using Canny operator from cv2,detect the edges of the image.

## Program:
```
Developed By :HARSHITHA V
Register No :212223230074
```
```
import cv2
import matplotlib.pyplot as plt

img = cv2.imread(r"C:\Users\admin\Downloads\digitalimage\river.jpeg")
if img is None:
    print("Error: Could not load image. Check the file path.")
else:
    gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)
    gray = cv2.GaussianBlur(gray, (3, 3), 0)

    #Sobel X
    sobelx = cv2.Sobel(gray, cv2.CV_64F, 1, 0, ksize=5)
    #Sobel Y
    sobely = cv2.Sobel(gray, cv2.CV_64F, 0, 1, ksize=5)
    #Sobel XY
    sobelxy = cv2.Sobel(gray, cv2.CV_64F, 1, 1, ksize=5)
    #Laplacian
    lap = cv2.Laplacian(gray, cv2.CV_64F)
    #Canny
    canny = cv2.Canny(gray, 120, 150)

```
### SOBEL EDGE DETECTOR
```
#Plot 1: Grayscale and Sobel X
plt.figure(figsize=(10, 5))
plt.subplot(1, 2, 1)
plt.imshow(gray, cmap='gray')  # Display the grayscale image
plt.title("Grayscale Image")
plt.axis("off")

plt.subplot(1, 2, 2)
plt.imshow(sobelx, cmap='gray')  # Display the Sobel X result
plt.title("Sobel X")
plt.axis("off")

plt.tight_layout()
plt.show()
```

### LAPLACIAN EDGE DETECTOR
```
#Plot 2: Original and Laplacian
plt.figure(figsize=(10, 5))
plt.subplot(1, 2, 1)
plt.imshow(cv2.cvtColor(img, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB for correct display
plt.title("Original Image")
plt.axis("off")

plt.subplot(1, 2, 2)
plt.imshow(lap, cmap='gray')
plt.title("Laplacian")
plt.axis("off")

plt.tight_layout()
plt.show()

```

### CANNY EDGE DETECTOR
```
#Plot 3: Original and Canny
plt.figure(figsize=(10, 5))
plt.subplot(1, 2, 1)
plt.imshow(cv2.cvtColor(img, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB for correct display
plt.title("Original Image")
plt.axis("off")

plt.subplot(1, 2, 2)
plt.imshow(canny, cmap='gray')
plt.title("Canny Edge")
plt.axis("off")

plt.tight_layout()
plt.show()

```
## Output:
### SOBEL EDGE DETECTOR

![image](https://github.com/user-attachments/assets/dfb36a79-d2bc-44db-957b-0106eec881b1)

### LAPLACIAN EDGE DETECTOR

![image](https://github.com/user-attachments/assets/f4d35edc-638a-49dd-b58f-6f7aee0cfeb5)

### CANNY EDGE DETECTOR

![image](https://github.com/user-attachments/assets/e2fe9240-48b5-4d1f-9ba7-a094005a32b1)

## Result:
Thus the edges are detected using Sobel, Laplacian, and Canny edge detectors.
