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

![image](https://github.com/user-attachments/assets/7926550b-f0f3-4301-86c9-9441be65538d)

![image](https://github.com/user-attachments/assets/ef9c39be-c69c-4ae3-a270-e669084c1023)

![image](https://github.com/user-attachments/assets/2919189f-ce7f-425b-8a52-eea9ce9e9f39)

![image](https://github.com/user-attachments/assets/899adba7-aa53-409b-b45a-d14f8a9e809f)






### Input image and grayscale image
![output](./p1.png)

### Canny Edge detector output
![output](./p2.png)

### Display the result of Hough transform
![output](./p3.png)
