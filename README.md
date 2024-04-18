# EXP 7: EDGE--LINKING-HOUGH-TRANSFORM
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Read the image

### Step2:
Convert the input image to gray to get more details

### Step3:
Apply any smoothing filter, here we apply Gaussian blur

### Step4:
Apply an edge detector

### Step5:
Apply hough transform and show the detected edge on the original image


## Program:
 ## REG.NO: 212222230073
 ## NAME: LATHISH KANNA.M
```Python
 
# Read image and convert it to grayscale image
import cv2
import numpy as np
r=cv2.imread('catt.jpg',-1)
gray=cv2.cvtColor(r,cv2.COLOR_BGR2GRAY)
img = cv2.GaussianBlur(gray,(3,3),0)
cv2.imshow('origianl',r)
cv2.waitKey(0)
cv2.destroyAllWindows()
cv2.imshow('gray',gray)
cv2.waitKey(0)
cv2.destroyAllWindows()


# Find the edges in the image using canny detector and display
canny_edges = cv2.Canny(img, 50, 120)
cv2.imshow('canny',canny_edges)
cv2.waitKey(0)
cv2.destroyAllWindows()


# Detect points that form a line using HoughLinesP
lines =cv2.HoughLinesP(canny_edges, 1, np.pi/180,threshold = 15, minLineLength =5 ,
maxLineGap = 7)



# Draw lines on the image
for line in lines:
 x1,y1,x2,y2 = line[0]
 cv2.line(r, (x1,y1),(x2,y2),(255,0,0),3)



# Display the result
cv2.imshow('hough_detected',r)
cv2.waitKey(0)
cv2.destroyAllWindows()



```
## Output

### Input image and grayscale image
![Screenshot 2024-04-16 105543](https://github.com/lathishlathish/Edge-Linking-using-Hough-Transformm/assets/120359170/6eedeb12-44bb-4418-a903-33c00b957ef3)
![Screenshot 2024-04-16 105605](https://github.com/lathishlathish/Edge-Linking-using-Hough-Transformm/assets/120359170/ada81f13-648d-4824-87c4-cc0dd70240d7)



### Canny Edge detector output
![Screenshot 2024-04-16 105811](https://github.com/lathishlathish/Edge-Linking-using-Hough-Transformm/assets/120359170/cedc2b27-0cf3-4c2a-aed5-ce677da6119c)



### Display the result of the Hough transform
![Screenshot 2024-04-16 110054](https://github.com/lathishlathish/Edge-Linking-using-Hough-Transformm/assets/120359170/816d3fd1-8e57-4301-95c4-d29a7d22338f)


## Result:
Thus the program is written with Python and OpenCV to detect lines using Hough transform. 
