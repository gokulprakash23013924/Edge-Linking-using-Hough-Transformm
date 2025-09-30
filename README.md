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
## PROGRAM:
```
NAME: Gokul prakash M
REG: 212223240041
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('exp7img.jpg')
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  
plt.title("Input Image")
plt.axis('off')
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)
for line in lines:
    x1, y1, x2, y2 = line[0]
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  
plt.title("Result of Hough Transform")
plt.axis('off')
```
## Output

### Input image and grayscale image
<img width="825" height="471" alt="image" src="https://github.com/user-attachments/assets/0f00a6bb-c39f-49da-abc9-ea354e7702d6" />
### Canny Edge detector output
<img width="733" height="486" alt="image" src="https://github.com/user-attachments/assets/9d4855cf-113b-4784-b0d1-df759d0a2f62" />


### Display the result of Hough transform
<img width="730" height="476" alt="image" src="https://github.com/user-attachments/assets/deec676c-fe2e-4e29-8630-71328850d1cc" />
