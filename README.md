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

## PROGRAM
```

import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('Screenshot 2025-04-21 183805.png')
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

![image](https://github.com/user-attachments/assets/321be5bb-5c30-443e-82bf-4d97aef4da12)

![image](https://github.com/user-attachments/assets/65984c65-6cf0-4ac5-ac04-72deb84b967a)

![image](https://github.com/user-attachments/assets/5c9f0b4f-df9c-45ac-af45-b0062c03de4c)

![image](https://github.com/user-attachments/assets/541246d6-0d3e-46b2-92fe-ef7ff2b1ced3)


# Result:
To perform edge linking using the Hough Transform and extract only one line, you typically follow these steps in Python using OpenCV and NumPy:










