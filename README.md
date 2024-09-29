# EDGE--LINKING-HOUGH-TRANSFORM
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

```
Developed By : Pradeep S
Register Number : 212222100034
```
```Python

# Read image and convert it to grayscale image
import cv2
import numpy as np
r=cv2.imread('bird.jpg',-1)
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

![b1](https://github.com/user-attachments/assets/7b7a9fe0-ec6a-41d6-8473-d354ca9f1566)

![b2](https://github.com/user-attachments/assets/f22b52c5-bf9d-4ef9-8da8-3986901d835e)


### Canny Edge detector output

![b3](https://github.com/user-attachments/assets/e1c10f50-b1d6-4303-814c-899ae2628754)


### Display the result of the Hough transform

![b4](https://github.com/user-attachments/assets/d0065ba5-3410-400d-a6ff-1e1e85578bd8)

## Result:
Thus the program is written with Python and OpenCV to detect lines using Hough transform. 
