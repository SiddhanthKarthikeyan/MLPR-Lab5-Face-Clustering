# MLPR-Lab5-Face-Clustering

## Aim of the Assignment

The objective of this lab is to:

. Detect faces from a group image using a Haar Cascade classifier

. Extract simple color-based features (Hue and Saturation) from each detected face

. Perform unsupervised clustering using K-Means

. Classify a new template face image into one of the discovered clusters

. Understand how distance-based clustering works in practice


## Methodology

 ### 1. Face Detection

. The image Plaksha_Faculty.jpg is read using OpenCV.

. It is converted to grayscale.

. A Haar Cascade classifier (haarcascade_frontalface_default.xml) is used to detect faces.

. Rectangles are drawn around detected faces.

#### Example Output:
<img width="1597" height="1092" alt="faces detected" src="https://github.com/user-attachments/assets/c65fc5c7-1571-41cf-a88b-6acc0c5c1f2d" />

### 2. Feature Extraction

For each detected face:

. The image is converted from BGR → HSV color space.

. The mean Hue value is computed.

. The mean Saturation value is computed.

Each face is represented as:
(hue, saturation)

This creates a 2-D feature space.

### 3. K-Means Clustering

. K-Means is applied with k = 2.

. Faces are grouped into two clusters based on Hue–Saturation similarity.

. Cluster centroids are calculated.

Faces plotted in Hue–Saturation space:
<img width="1618" height="867" alt="output1" src="https://github.com/user-attachments/assets/09eb5a7a-b278-4997-8bf9-50003435a0a1" />

Cluster visualization with centroids:
<img width="1618" height="872" alt="output2" src="https://github.com/user-attachments/assets/e01125b3-944d-498b-a6c1-436be97af1b6" />

### 4. Template Classification

. The template image Dr_Shashi_Tharoor.jpg is processed.

. Its Hue–Saturation features are computed.

. The trained K-Means model predicts its cluster label.

Template classification result:
<img width="1617" height="867" alt="output3" src="https://github.com/user-attachments/assets/6c3c4721-aa45-4cb8-83b2-e901c7ea8dab" />
<img width="1620" height="877" alt="output4" src="https://github.com/user-attachments/assets/efaafe13-667d-456d-bcd9-bddc9384fef5" />


## Key Observations

. Faces cluster naturally based on color characteristics.

. Hue and Saturation provide a simple yet effective 2D feature representation.

. K-Means successfully separates faces into two visually meaningful groups.

. The template image is classified into the cluster whose centroid is closest in Euclidean distance.


## Concepts Used

. Haar Cascade Face Detection

. HSV Color Space

. Feature Engineering

. K-Means Clustering

. Distance-based classification


## Advantages of Distance-Based Methods

. Simple and easy to implement

. No assumptions about data distribution

. Works well for low-dimensional feature spaces


## Limitations

. Sensitive to feature scaling

. Computational cost increases with dataset size

. Performance depends on choice of k

. Can struggle in high-dimensional spaces (curse of dimensionality)


## Technologies Used

. Python 3

. OpenCV

. NumPy

. Matplotlib

. Scikit-learn
