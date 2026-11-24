# Implementation of Erosion and Dilation Using OpenCV

## Aim

To write a Python program using OpenCV to perform morphological
operations such as Erosion and Dilation on an image.

## Learning Objectives

-   Understand morphological operations in image processing.
-   Learn how erosion reduces the boundaries of foreground objects.
-   Learn how dilation expands the boundaries of foreground objects.
-   Compare the results of erosion and dilation.

## Software Used

-   Anaconda -- Python 3.7
-   Jupyter Notebook / VS Code
-   OpenCV (`cv2`)
-   NumPy
-   Matplotlib

## Algorithm and Explanation

### Step 1: Import Libraries

Import OpenCV, NumPy, and Matplotlib for image processing and displaying
the results.

``` python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

### Step 2: Create Image and Insert Text

Create a blank black image using NumPy and insert the text `OPENCV`
using OpenCV.

``` python
image = np.zeros((300, 500), dtype=np.uint8)
cv2.putText(image, "OPENCV", (50, 170),
            cv2.FONT_HERSHEY_SIMPLEX, 3, 255, 8)
```

### Step 3: Create Kernel

Create a 5 × 5 structuring element (kernel) for the morphological
operations.

``` python
kernel = np.ones((5, 5), np.uint8)
```

### Step 4: Perform Erosion and Dilation

Erosion reduces the thickness of the foreground text, while dilation
increases its thickness.

**Erosion**

``` python
erosion = cv2.erode(image, kernel, iterations=1)
```

**Dilation**

``` python
dilation = cv2.dilate(image, kernel, iterations=1)
```

### Step 5: Display and Compare Results

Display the original, eroded, and dilated images together for
comparison.

``` python
images = [image, erosion, dilation]
titles = ["Original Image", "Erosion", "Dilation"]

plt.figure(figsize=(12, 4))

for i in range(3):
    plt.subplot(1, 3, i+1)
    plt.imshow(images[i], cmap='gray')
    plt.title(titles[i])
    plt.axis('off')

plt.tight_layout()
plt.show()

print("Erosion and Dilation Completed Successfully!")
```

## Expected Output

<img width="916" height="226" alt="image" src="https://github.com/user-attachments/assets/06ed54e5-522b-4b20-95d4-99eb22d8e57c" />


## Result

Thus, the morphological operations **Erosion** and **Dilation** are
successfully implemented using OpenCV.
