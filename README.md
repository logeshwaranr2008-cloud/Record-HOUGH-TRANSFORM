# Detect-the-lines-using-Hough-Transform

##  Developed By: LOGESHWARAN C

## Register: No: 212225040205

##  Aim

To implement a basic lane detection pipeline using OpenCV by completing missing code segments at specified locations.

---

## Learning Objective

* Understand each stage of image processing
* Learn how to build a complete computer vision pipeline
* Practice writing code in guided sections

---

##  Software Used

* Anaconda – Python 3.7
* Jupyter Notebook / VS Code
* OpenCV (cv2)
* NumPy
* Matplotlib

---

##  Algorithm & Explanation

---

###  Step 1: Import Libraries

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

---

###  Step 2: Read the Image

```
image = cv2.imread('sai1.jpeg') 
```

---

###  Step 3: Convert to Grayscale

```
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
```

---

###  Step 5: Display Images

```

plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  
plt.title("Input Image")
plt.axis('off')
```

```
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
```

---

### Step 6: Edge Detection (Canny)

```
edges = cv2.Canny(gray_image, 50, 150)
```

```
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
```

---


###  Step 7: Hough Transform

```
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)

for line in lines:
    x1, y1, x2, y2 = line.flatten()
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)
```

---

### Step 8: Display the result of Hough Transform (Image with lines):
```
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB)) 
plt.title("Result of Hough Transform")
plt.axis('off')
```

---

## Output:

## Original image:

<img width="227" height="405" alt="image" src="https://github.com/user-attachments/assets/0cab7b72-68ce-49a6-8a41-9fab58c5be99" />

## Grayscale image:

<img width="231" height="401" alt="image" src="https://github.com/user-attachments/assets/1fb6cc8e-18be-4598-9387-2e38010cc64c" />


## Canny Edge Detector:

<img width="260" height="411" alt="image" src="https://github.com/user-attachments/assets/6e96b80c-61c9-4ced-b09e-eddb6e0d15b0" />

## Hough Transform:

<img width="295" height="407" alt="image" src="https://github.com/user-attachments/assets/47ba7933-027d-42b6-b493-eab4fe32a6e9" />


## Result

Thus, the lane detection pipeline is successfully implemented by completing the missing code sections. The system detects and highlights lane lines effectively.

---
