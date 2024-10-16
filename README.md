# Edge-Linking-using-Hough-Transformm
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:

Import all the necessary modules for the program.
### Step2:

Load a image using imread() from cv2 module.
### Step3:

Convert the image to grayscale.
### Step4:

Using Canny operator from cv2,detect the edges of the image.
### Step5:

Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.

## Program:
### Name: MUKESH P
### Register number: 212222240068
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('VJK.jpg')
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
edges = cv2.Canny(gray_image, 50, 150, apertureSize=3)

# Detect lines using the probabilistic Hough transform
lines = cv2.HoughLinesP(edges, rho=1, theta=np.pi/180, threshold=100, minLineLength=50, maxLineGap=10)

# Draw the lines on the original image
output_image = image.copy()

if lines is not None:
    for line in lines:
        x1, y1, x2, y2 = line[0]
        cv2.line(output_image, (x1, y1), (x2, y2), (0, 255, 0), 2)


# Displaying results using Matplotlib
plt.figure(figsize=(12, 12))

# Input Image and Grayscale Image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Input Image')
plt.axis('off')
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')

# Canny Edge Detection Output
plt.imshow(edges, cmap='gray')
plt.title('Canny Edge Detector Output')
plt.axis('off')

# Hough Transform Result
plt.imshow(cv2.cvtColor(output_image, cv2.COLOR_BGR2RGB))
plt.title('Hough Transform - Line Detection')
plt.axis('off')
```

## Output

### Input image and grayscale image

![WhatsApp Image 2024-10-16 at 16 11 25_fe2d69a8](https://github.com/user-attachments/assets/60e846d0-a899-47e9-8595-7df03b530324)

![WhatsApp Image 2024-10-16 at 16 10 31_4ad8333f](https://github.com/user-attachments/assets/69864e95-1576-40c9-94e9-b9e25086eaea)



### Canny Edge detector output

![WhatsApp Image 2024-10-16 at 16 10 37_53082bd6](https://github.com/user-attachments/assets/bd12d3e5-8fd6-495e-9eb3-7c2e1c686d1e)




### Display the result of Hough transform

![WhatsApp Image 2024-10-16 at 16 10 42_20dc7ef8](https://github.com/user-attachments/assets/6b27dead-af5a-4ca0-857d-4959e4dcc80f)




## Result:
Thus, the program to detect the lines using Hough Transform implemented successfully.
