# Unit 3

## Q.1 Discuss how to measure the properties of the region in a labeled image.

## Measuring Properties of Regions in a Labeled Image

## Introduction

In digital image processing, after segmenting an image, **labeling** assigns a unique label (number) to each connected region.  
To analyze these regions, we measure their **properties** such as **area**, **perimeter**, **centroid**, **bounding box**, etc.

---

## Common Properties Measured

### 1. Area

- **Definition**: Number of pixels that belong to a region.
- **Formula**:
  \[
  \text{Area} = \text{Total number of pixels with same label}
  \]

---

### 2. Perimeter

- **Definition**: Total length of the boundary of the region.
- **Measurement**: Count the number of edge pixels or use chain codes to estimate perimeter more accurately.

---

### 3. Centroid

- **Definition**: Geometric center of the region.
- **Formula**:
  \[
  (x_c, y_c) = \left( \frac{\sum{x_i}}{N}, \frac{\sum{y_i}}{N} \right)
  \]
  Where:
  - \( (x_i, y_i) \) are the coordinates of the pixels,
  - \( N \) is the total number of pixels in the region.

---

### 4. Bounding Box

- **Definition**: The smallest rectangle that completely contains the region.
- **Measurement**:
  - Find minimum and maximum \(x\) and \(y\) coordinates.
  - Create a rectangle using these points.

---

### 5. Major and Minor Axis Lengths

- **Definition**:
  - **Major axis**: Longest diameter of the fitted ellipse.
  - **Minor axis**: Shortest diameter of the fitted ellipse.
- Useful for describing elongated shapes.

---

### 6. Eccentricity

- **Definition**: Ratio of the distance between the foci of the ellipse and its major axis length.
- **Use**: Describes how much a region deviates from being circular.

---

### 7. Orientation

- **Definition**: Angle between the x-axis and the major axis of the fitted ellipse.

---

### 8. Solidity

- **Definition**: Ratio of region area to convex hull area.
- **Formula**:
  \[
  \text{Solidity} = \frac{\text{Area of Region}}{\text{Area of Convex Hull}}
  \]
- Used to detect convex or concave shapes.

---

## Steps to Measure Properties

1. **Label the Image**: Assign unique labels to connected components.
2. **Extract Pixels**: For each label, extract all pixels belonging to that region.
3. **Calculate Features**: Apply formulas to measure area, perimeter, centroid, etc.
4. **Store or Display Results**: Save the properties for further analysis like classification or object recognition.

---

## Applications

- **Object recognition**.
- **Medical image analysis** (e.g., tumor size measurement).
- **Shape analysis**.
- **Industrial inspection** (e.g., measuring manufactured parts).

---

## Conclusion

Measuring region properties in a labeled image helps in **quantitative analysis** and **decision-making** in many image processing and computer vision applications.

---

## Q.2 Explain in brief view class matching.

## View Class Matching

## Introduction

**View Class Matching** is a concept in computer vision and image recognition.  
It refers to the process of **matching a new (unknown) view of an object** to a set of **stored views** (known classes) to recognize or classify the object.

Instead of trying to reconstruct the 3D shape of an object, view class matching directly compares the input image with stored 2D images (views) of objects.

---

## Key Points

- **Stored views** are created from different angles, positions, and scales.
- A **new input image** is compared to these stored views to find the best match.
- It is based on the **appearance-based recognition** approach.
- It avoids complex 3D modeling and simplifies recognition tasks.

---

## Working Steps

1. **Database Preparation**:

   - Capture multiple 2D views of each object.
   - Store these views as the "class" for matching.

2. **Feature Extraction**:

   - Extract key features from both stored views and the new image.
   - Features could include edges, corners, textures, etc.

3. **Matching**:

   - Compare features of the new image with features of stored views.
   - Use similarity measures like Euclidean distance, correlation, etc.

4. **Classification**:
   - The object is classified based on the best matching stored view class.

---

## Applications

- **Face recognition** (matching face images under different poses).
- **Object tracking** in robotics.
- **Augmented reality** (AR) applications.
- **Gesture recognition**.

---

## Advantages

- No need for 3D reconstruction.
- Fast and effective for certain applications.
- Works well for objects with limited appearance variations.

---

## Limitations

- Requires a large number of stored views for objects with high variability.
- Performance decreases with extreme viewpoint changes or occlusions.
- Sensitive to lighting and scale changes.

---

## Conclusion

View Class Matching provides a **simple and efficient** way to recognize objects based on their **2D appearances**, making it useful for many practical computer vision tasks.

---
