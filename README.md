# Scientific-Computing-Data-Analysis
# Handwritten Digit Classifier using SVD

**Course:** Scientific Computing for Data Analysis (1TD352) - Uppsala University
**Authors:** Arvid Axelsson, Hannes Lundström, Neo Sjöström

## Overview
This project implements a simple and interpretable classifier for handwritten digits based on Singular Value Decomposition (SVD). The core concept behind this approach is that images of the same digit, despite having different handwriting styles, tend to lie approximately within a low-dimensional subspace.

## Methodology
* **Data Representation:** Each handwritten digit is represented as a 28x28 pixel grayscale image, which is flattened into a vector of size 784.
* **Model Training:** We construct a training matrix for each digit (0-9) by stacking these vectors. By computing the SVD of each matrix, we keep the first *k* left singular vectors to form an orthonormal basis that captures the dominant variations and patterns of that specific digit.
* **Classification:** To classify a new test image, we project it onto each of the 10 digit subspaces and calculate the reconstruction residual. The algorithm classifies the test image as the digit whose subspace yields the smallest residual.

## Key Results
* The classifier was tested using varying numbers of basis functions (from k=5 to k=15).
* Overall classification success rates generally improved as the number of basis functions increased.
* The model achieved its best success rate when classifying the digit 1, while the digit 8 proved to be the most difficult to classify accurately due to its visual similarities with other digits.

---

### ⚠️ Note on Data Files
*Please note that the NumPy arrays containing the raw test and training data matrices are too large to attach directly to this repository.*
