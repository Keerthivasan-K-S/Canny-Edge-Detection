# Canny Edge Detection using OpenCV

## Overview
This project demonstrates the implementation of the **Canny Edge Detection Algorithm** using Python and OpenCV. Edge detection is one of the most important image processing techniques used to identify object boundaries within an image. The Canny algorithm detects sharp intensity changes and produces a clean edge map while reducing noise.

In this project, a sample grayscale image is processed using Gaussian Blur to remove noise, followed by the Canny Edge Detection algorithm to extract significant edges. The detected edges are then displayed alongside the original image for comparison.

---

## Features
- Reads a grayscale image using OpenCV.
- Applies Gaussian Blur to reduce image noise.
- Implements the Canny Edge Detection algorithm.
- Displays both the original image and detected edges.
- Simple and easy-to-understand implementation.
- Demonstrates the impact of threshold values on edge detection results.

---

## Technologies Used
- **Python**
- **OpenCV** – Image processing and edge detection
- **Matplotlib** – Image visualization

---

## Algorithm Used: Canny Edge Detection

The Canny Edge Detection algorithm consists of the following steps:

### 1. Noise Reduction
A Gaussian filter is applied to smooth the image and remove noise.

### 2. Gradient Calculation
Intensity gradients are calculated to identify regions with strong edge information.

### 3. Non-Maximum Suppression
Thin edges are obtained by suppressing non-maximum gradient values.

### 4. Double Thresholding
Two threshold values are used to classify strong and weak edges.

### 5. Edge Tracking by Hysteresis
Weak edges connected to strong edges are retained, while others are discarded.

---

## Python Code

```python
import cv2
import matplotlib.pyplot as plt

img = cv2.imread(
    "E://Digital Image//Workshop//Workshop-3(Photo).jpg",
    cv2.IMREAD_GRAYSCALE
)

blurred = cv2.GaussianBlur(img, (5, 5), 0)

edges = cv2.Canny(blurred, 50, 150)

plt.figure(figsize=(10,5))

plt.subplot(121)
plt.imshow(img, cmap='gray')
print("Keerthivasan K S")
print("212224230120")
plt.title('Original Image')
plt.axis('off')

plt.subplot(122)
plt.imshow(edges, cmap='gray')
plt.title('Detected Edges')
plt.axis('off')

plt.show()
```

---

## How to Run

### 1. Install Required Libraries

```bash
pip install opencv-python matplotlib
```

### 2. Place the Input Image
Store the image in the specified path or update the image path in the code.

### 3. Run the Program

```bash
python canny_edge_detection.py
```

### 4. View Results
The program displays:
- Original Image
- Edge Detected Image

---

## Output Description

### Original Image
The original grayscale image is loaded and displayed for processing.

### Detected Edges
The Canny algorithm identifies significant intensity changes and highlights object boundaries as white pixels on a black background.

The detected edges help in:
- Object recognition
- Shape analysis
- Image segmentation
- Computer vision applications

---

## Impact of Different Parameter Settings

### 1. Gaussian Blur Kernel Size

Small kernel:

```python
cv2.GaussianBlur(img, (3,3), 0)
```

- Preserves more image details.
- May retain noise.

Large kernel:

```python
cv2.GaussianBlur(img, (9,9), 0)
```

- Removes more noise.
- Some fine edges may disappear.

---

### 2. Lower Threshold Value

Example:

```python
cv2.Canny(blurred, 20, 150)
```

- Detects more edges.
- May include unwanted noise.

Higher value:

```python
cv2.Canny(blurred, 80, 150)
```

- Removes weak edges.
- Produces cleaner output.

---

### 3. Upper Threshold Value

Example:

```python
cv2.Canny(blurred, 50, 100)
```

- More edges are detected.
- May increase false detections.

Higher value:

```python
cv2.Canny(blurred, 50, 250)
```

- Detects only strong edges.
- Some important edges may be missed.

---

## Comparison of Threshold Settings

| Lower Threshold | Upper Threshold | Result |
|----------------|----------------|---------|
| 20 | 100 | Detects many edges, including noise |
| 50 | 150 | Balanced and accurate edge detection |
| 100 | 200 | Detects only strong edges |
| 150 | 250 | Very few edges detected |

---

## Discussion of Detected Edges

The Canny Edge Detection algorithm successfully identifies the prominent boundaries and structural features present in the image. Applying Gaussian Blur before edge detection reduces noise and prevents false edge detection. The selected threshold values (50 and 150) provide a balanced output by retaining significant edges while eliminating weak and noisy edges.

The resulting edge image clearly highlights object outlines and major intensity transitions, making it useful for image analysis and computer vision tasks.

---

## Applications

- Object Detection
- Image Segmentation
- Face Detection
- Medical Image Analysis
- Autonomous Vehicles
- Industrial Inspection
- Computer Vision Research

---

## Result

This project successfully implements the **Canny Edge Detection Algorithm** using OpenCV. By applying Gaussian smoothing followed by edge detection, significant object boundaries are extracted from the image. The quality of detected edges depends heavily on the blur kernel size and threshold values. Proper parameter tuning enables accurate edge extraction for various image processing applications.

---
