[Ex.4 (2).ipynb](https://github.com/user-attachments/files/32291796/Ex.4.2.ipynb)
# NAME: YOGAMAHENDRAN G
# REG NO:212225040500

# Aim
To write a Python program using OpenCV to perform various geometric transformations on an image.

The program performs the following operations:
 1)Image Translation
 
2)Image Scaling (Resizing)

3)Image Shearing

4)Image Reflection (Flipping)

5)Image Rotation

6)Software Used

7)Anaconda – Python 3.7

8)Jupyter Notebook / VS Code

9)OpenCV (cv2)

10)NumPy

11)Matplotlib

# Algorithm
Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

Step 2:
Read the input image in color mode.

Step 3: Image Translation
Create a translation matrix to shift the image
Move the image 50 pixels to the right and 80 pixels down
Apply transformation using cv2.warpAffine()
Display original and translated images

Step 4: Image Scaling
Resize the image to 0.5× (downscale)
Resize the image to 2× (upscale)
Use cv2.resize()
Display original, downscaled, and upscaled images

Step 5: Image Shearing
Create transformation matrices for:
Horizontal shearing
Vertical shearing
Apply transformations using cv2.warpAffine()
Display original and sheared images

Step 6: Image Reflection
Perform flipping using cv2.flip():
Horizontal reflection
Vertical reflection
Both axes
Display all reflected images

Step 7: Image Rotation
Create rotation matrices for:
45° rotation
90° rotation
Use cv2.getRotationMatrix2D() and cv2.warpAffine()
Display original and rotated images

# Program:
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
# Step 1: Load the image
image = cv2.imread('spider.png')  # Load the image from file
# Display the original image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB for correct display
plt.title("Original Image")  
plt.axis('off')

# Step 2: Image Translation
tx, ty = 100, 50  # Translation factors (shift by 100 pixels horizontally and 50 vertically)
M_translation = np.float32([[1, 0, tx], [0, 1, ty]])  # Translation matrix: 
# [1, 0, tx] - Horizontal shift by tx
# [0, 1, ty] - Vertical shift by ty
translated_image = cv2.warpAffine(image, M_translation, (image.shape[1], image.shape[0]))  
plt.imshow(cv2.cvtColor(translated_image, cv2.COLOR_BGR2RGB))  # Display the translated image
plt.title("Translated Image")  
plt.axis('off')
```

# output
<img width="483" height="409" alt="e773abb0-9ee9-4cc0-9c0f-5fceb8d14334" src="https://github.com/user-attachments/assets/a8273db8-e657-4877-b884-096ea9062b8f" />

```
import cv2
import numpy as np
import matplotlib.pyplot as plt
# Step 1: Load the image
image = cv2.imread('spider.png')  # Load the image from file
# Display the original image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB for correct display
plt.title("Original Image")  
plt.axis('off')
```
<img width="483" height="409" alt="9a150fc2-9dad-4a36-8015-12e8a4594e28" src="https://github.com/user-attachments/assets/cde7f12d-dec7-4bec-9b0d-d3a8e0b246fc" />

```
# Step 4: Image Shearing
shear_matrix = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  # Shearing matrix
# The matrix shears the image by a factor of 0.5 in both x and y directions
# [1, 0.5, 0] - Shear along the x-axis (horizontal)
# [0.5, 1, 0] - Shear along the y-axis (vertical)
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))
plt.imshow(cv2.cvtColor(sheared_image, cv2.COLOR_BGR2RGB))  # Display the sheared image
plt.title("Sheared Image")  # Set title
plt.axis('off')
```
<img width="515" height="198" alt="36020af3-68b0-4442-88cb-324ab43e05be" src="https://github.com/user-attachments/assets/b667c7aa-1f0e-4822-bce9-013303a16381" />

```
# Step 4: Image Shearing
shear_matrix = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  # Shearing matrix
# The matrix shears the image by a factor of 0.5 in both x and y directions
# [1, 0.5, 0] - Shear along the x-axis (horizontal)
# [0.5, 1, 0] - Shear along the y-axis (vertical)
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))
plt.imshow(cv2.cvtColor(sheared_image, cv2.COLOR_BGR2RGB))  # Display the sheared image
plt.title("Sheared Image")  # Set title
plt.axis('off')
```

<img width="483" height="409" alt="8a53e80c-7053-48d7-969e-c7e2d76e8c9f" src="https://github.com/user-attachments/assets/7d9989ee-3e53-42b9-b4a5-90e8f934067a" />

```
# Step 5: Image Reflection
reflected_image = cv2.flip(image, 2)  # Flip the image horizontally (1 means horizontal flip)
# flip: 1 means horizontal flip, 0 would be vertical flip, -1 would flip both axes
plt.imshow(cv2.cvtColor(reflected_image, cv2.COLOR_BGR2RGB))  # Display the reflected image
plt.title("Reflected Image")  # Set title
plt.axis('off')
```
<img width="483" height="409" alt="9f4ced66-6c48-49b2-8bc0-0597b4e621a4" src="https://github.com/user-attachments/assets/1c8022af-6b60-4f01-ace1-d0b726e98e9d" />

```
x, y, w, h = 100, 100, 200, 150  # Define the top-left corner (x, y) and the width (w) and height (h) of the crop
# Cropping the image from coordinates (x, y) to (x+w, y+h)
cropped_image = image[y:y+h, x:x+w]
# The crop is performed by slicing the image array in the y and x directions
plt.imshow(cv2.cvtColor(cropped_image, cv2.COLOR_BGR2RGB))  # Display the cropped image
plt.title("Cropped Image")  # Set title
plt.axis('off')
```
<img width="483" height="409" alt="e9e37ad8-1c4f-48d3-aaef-5144e17771e0" src="https://github.com/user-attachments/assets/ba289274-9907-4fb6-bc82-d8bcaa85ca24" />

```
x, y, w, h = 100, 100, 200, 150  # Define the top-left corner (x, y) and the width (w) and height (h) of the crop
# Cropping the image from coordinates (x, y) to (x+w, y+h)
cropped_image = image[y:y+h, x:x+w]
# The crop is performed by slicing the image array in the y and x directions
plt.imshow(cv2.cvtColor(cropped_image, cv2.COLOR_BGR2RGB))  # Display the cropped image
plt.title("Cropped Image")  # Set title
plt.axis('off')
```
<img width="512" height="409" alt="6dd938b4-a77f-4ac8-958d-7709edeace2e" src="https://github.com/user-attachments/assets/b7f6b08f-28bf-4cf2-94d0-cc2f827ca5f4" />



# Result
Thus, various geometric transformations such as translation, scaling, shearing, reflection, and rotation are successfully performed using OpenCV. These transformations demonstrate how images can be spatially manipulated for different computer vision applications.



















