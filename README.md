# IMAGE-TRANSFORMATIONS


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import necessary libraries such as OpenCV, NumPy, and Matplotlib for image processing and visualization.

### Step2:
Read the input image using cv2.imread() and store it in a variable for further processing.

### Step3:
Apply various transformations like translation, scaling, shearing, reflection, rotation, and cropping by defining corresponding functions:

1.Translation moves the image along the x or y-axis. 2.Scaling resizes the image by scaling factors. 3.Shearing distorts the image along one axis. 4.Reflection flips the image horizontally or vertically. 5.Rotation rotates the image by a given angle.

### Step4:
Display the transformed images using Matplotlib for visualization. Convert the BGR image to RGB format to ensure proper color representation.

### Step5:
Save or display the final transformed images for analysis and use plt.show() to display them inline in Jupyter or compatible environments.

## Program:
```
Developed By:SANDHIYA R
Register Number:212223240146

import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('ex4.jpg')

image_rgb=cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

plt.imshow(image_rgb)  
plt.title("Original Image")  
plt.axis('off')

i)Image Translation
tx, ty = 100, 50 
M_translation = np.float32([[1, 0, tx], [0, 1, ty]])  
translated_image = cv2.warpAffine(image, M_translation, (1792,1792))
plt.imshow(translated_image[:,:,::-1])  
plt.title("Translated Image")  
plt.axis('off')

ii) Image Scaling
scaled_image = cv2.resize(image, None, fx=5.0, fy=2.0, interpolation=cv2.INTER_LINEAR)

plt.imshow(scaled_image[:,:,::-1])  
plt.title("Scaled Image") 
plt.axis('off')

iii)Image shearing
shear_matrix = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  
sheared_image = cv2.warpAffine(image, shear_matrix, (4002,6000))

plt.imshow(sheared_image[:,:,::-1])  
plt.title("Sheared Image")  
plt.axis('off')


iv)Image Reflection
reflected_image = cv2.flip(image, 2)

plt.imshow(reflected_image[:,:,::-1]) 
plt.title("Reflected Image") 
plt.axis('off')

v)Image Rotation

(height, width) = image.shape[:2]  
angle = 45  
center = (width // 2, height // 2) 
M_rotation = cv2.getRotationMatrix2D(center, angle, 1)  
rotated_image = cv2.warpAffine(image, M_rotation, (width, height))

plt.imshow(rotated_image[:,:,::-1]) 
plt.title("Rotated Image")  
plt.axis('off')

vi)Image Cropping

x, y, w, h = 100,150, 250, 150
cropped_image = image[y:y+h, x:x+w]

plt.imshow(cropped_image[:,:,::-1]) 
plt.title("Cropped Image")  
plt.axis('off')
```
## Output:

### Original image
![image](https://github.com/user-attachments/assets/7eeee99c-f173-4e87-ba35-712e61447dbe)

### i)Image Translation

![image](https://github.com/user-attachments/assets/9546584a-a798-40c4-96cd-1d06e7cc8c2a)


### ii) Image Scaling

![image](https://github.com/user-attachments/assets/3db70b5b-7f9f-4880-905c-060356ec5e1f)


### iii)Image shearing

![image](https://github.com/user-attachments/assets/91408e72-a1c8-422d-a182-7936af38a60c)



### iv)Image Reflection

![image](https://github.com/user-attachments/assets/cd458463-ee69-4067-9ef4-4ce5006b9aa2)



### v)Image Rotation

![image](https://github.com/user-attachments/assets/656c2d52-4834-43fe-91ec-387c0d93b5e8)


### vi)Image Cropping

![image](https://github.com/user-attachments/assets/a0d0299f-8360-4d4d-a4de-e339ffa70d3b)

## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
