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

1.Translation moves the image along the x or y-axis.

2.Scaling resizes the image by scaling factors.

3.Shearing distorts the image along one axis.

4.Reflection flips the image horizontally or vertically.

5.Rotation rotates the image by a given angle.

### Step4:
Display the transformed images using Matplotlib for visualization. Convert the BGR image to RGB format to ensure proper color representation.

### Step5:
Save or display the final transformed images for analysis and use plt.show() to display them inline in Jupyter or compatible environments

## Program:

# Developed By:R.SUBHASHRI


# Register Number:212223230219


# i)Image Translation

```

tx, ty = 100, 200  # Translation factors (shift by 100 pixels horizontally and 50 vertically)
M_translation = np.float32([[1, 0, tx], [0, 1, ty]])  # Translation matrix: 
# [1, 0, tx] - Horizontal shift by tx
# [0, 1, ty] - Vertical shift by ty
translated_image = cv2.warpAffine(image, M_translation, (636, 438)) 

plt.imshow(translated_image[:,:,::-1])
plt.title("Translated Image")
plt.axis('on')
plt.show()


```

# ii) Image Scaling

```

fx, fy = 2.0, 1.0  
scaled_image = cv2.resize(image, None, fx=fx, fy=fy, interpolation=cv2.INTER_LINEAR)

plt.imshow(scaled_image[:,:,::-1]) 
plt.title("Scaled Image") 
plt.axis('on')
plt.show()

```

# iii)Image shearing

```

shear_matrix = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  
sheared_image = cv2.warpAffine(image, shear_matrix, (636, 438))

plt.imshow(sheared_image[:,:,::-1])
plt.title("Sheared Image") 
plt.axis('on')
plt.show()

```

# iv)Image Reflection

```

reflected_image = cv2.flip(image, 2) 
plt.figure(figsize=(10, 5))

plt.subplot(1, 2, 1)
plt.imshow(image[:, :, ::-1])
plt.title("Original Image")
plt.axis('off')




# Show reflected image 


plt.subplot(1, 2, 2)
plt.imshow(reflected_image[:,:,::-1])
plt.title("Reflected Image")
plt.axis('off')

plt.tight_layout()
plt.show()

```

# v)Image Rotation

```

(height, width) = image.shape[:2]  # Get the image height and width
angle = 45  # Rotation angle in degrees (rotate by 45 degrees)
center = (width // 2, height // 2)  # Set the center of rotation to the image center
M_rotation = cv2.getRotationMatrix2D(center, angle, 1)  # Get the rotation matrix
rotated_image = cv2.warpAffine(image, M_rotation, (width, height))  # Apply rotation

plt.imshow(cv2.cvtColor(rotated_image, cv2.COLOR_BGR2RGB))  # Display the rotated image
plt.title("Rotated Image")  # Set title
plt.axis('off')

image .shape

angle = 145  
center = (636 // 2, 438 // 2)  
M_rotation = cv2.getRotationMatrix2D(center, angle, 1)  
# getRotationMatrix2D: Takes the center of rotation, angle, and scale factor (1 means no scaling)
rotated_image = cv2.warpAffine(image, M_rotation, (width, height))

plt.imshow(rotated_image[:,:,::-1])  # Display the rotated image
plt.title("Rotated Image")  # Set title
plt.axis('off')
plt.show()

```

# vi)Image Cropping

```

x, y, w, h = 0, 0, 200, 150  

cropped_image = image[y:y+h, x:x+w]   # Format: image[start_row:end_row, start_col:end_col]

plt.figure(figsize=(10, 5))

plt.subplot(1, 2, 1)
plt.imshow(image[:, :, ::-1])
plt.title("Original Image")
plt.axis('on')

# Show reflected image 
plt.subplot(1, 2, 2)
plt.imshow(cropped_image[:,:,::-1])
plt.title("Cropped Image")
plt.axis('on')

plt.tight_layout()
plt.show()



```
## Output:
### i)Image Translation


<img width="552" height="384" alt="image" src="https://github.com/user-attachments/assets/1e317222-9548-4c31-b93a-f999b62f2166" />


### ii) Image Scaling

<img width="552" height="230" alt="image" src="https://github.com/user-attachments/assets/fcaecf1a-d6c1-447e-bdf7-7d1db63e73c6" />


### iii)Image shearing

<img width="566" height="394" alt="image" src="https://github.com/user-attachments/assets/4adb668a-2a74-400e-aa0f-470a4ffef7d1" />



### iv)Image Reflection


<img width="935" height="355" alt="image" src="https://github.com/user-attachments/assets/3d053a1b-6fe6-49c3-b5fb-e54116fb4f1d" />



### v)Image Rotation

<img width="483" height="359" alt="image" src="https://github.com/user-attachments/assets/20170182-aff6-4454-bcbb-d973a219684d" />


<img width="488" height="360" alt="image" src="https://github.com/user-attachments/assets/83a9c1d9-b48f-42bf-bbb2-da45f8b3eb21" />



### vi)Image Cropping

<img width="943" height="376" alt="image" src="https://github.com/user-attachments/assets/72190d5e-62ad-44b8-b712-799edc2ca3b5" />




## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
