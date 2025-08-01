# 03 – Tumor Segmentation

## Overview

After identifying the presence and type of brain tumor, the final and crucial phase of our diagnostic pipeline is **tumor segmentation**. This stage involves generating a **pixel-wise binary mask** that highlights the tumor region in an MRI scan. Unlike classification, which tells us *what* is present, segmentation informs us *where* the anomaly is located.

Segmentation is not just a cosmetic step—it enhances diagnostic interpretability, guides surgical planning, and provides quantifiable tumor boundaries.

---

## Importance of Tumor Segmentation

Accurate tumor segmentation plays a pivotal role in real-world medical applications:

* **Precision Localization**: Identifies exact tumor regions for surgical intervention
* **Quantitative Insights**: Enables tumor volume estimation and progression tracking
* **Clinical Interpretability**: Enhances radiologists’ understanding through visual outputs
* **Pipeline Synergy**: Feeds into hybrid workflows like 3D reconstructions or radiotherapy simulations

---

## Model Architecture

Our segmentation model is a **U-Net variant**, specifically adapted for brain MRI images. It performs binary classification on each pixel, labeling it as either tumor (`1`) or background (`0`).

### ✨ Architecture Summary

* **Model Type**: Modified U-Net
* **Input Size**: 256×256 (grayscale MRI)
* **Output**: 256×256 binary mask
* **Activation**: Sigmoid
* **Loss Function**: Binary Cross-Entropy (BCE)
* **Optimizer**: Adam

#### Core Components

* Contracting Path: `Conv2D → ReLU → MaxPooling`
* Bottleneck Layer
* Expanding Path: `UpSampling → Concatenation → Conv2D`
* Skip Connections: Enhance feature preservation

![Segmentation Architecture](images/segmentation_model_architecture.png)

---

## Training Configuration

* **Dataset**: Labeled brain MRIs with corresponding tumor masks
* **Split Ratio**: 80% Training, 20% Validation
* **Image Preprocessing**:

  * Intensity normalization
  * Resizing to 256×256
* **Data Augmentations**:

  * Random horizontal & vertical flips
  * Rotation and zoom
  * Elastic transformations

---

## Evaluation Report

### 🔹 Confusion Matrix (Threshold = 0.40)

|                       | Predicted Background | Predicted Foreground |
| --------------------- | -------------------- | -------------------- |
| **Actual Background** | 257,943              | 961                  |
| **Actual Foreground** | 246                  | 2,994                |

* **True Positives (TP)**: 2,994
* **True Negatives (TN)**: 257,943
* **False Positives (FP)**: 961
* **False Negatives (FN)**: 246

### 🔹 Global Pixel Metrics

* **Precision**: 0.8208
* **Recall**: 0.7785
* **F1 Score**: 0.7991
* **IoU** (Foreground): $\frac{2994}{2994 + 961 + 246} \approx 0.719$

### 🔹 Per-Image Average Metrics

* **Mean IoU**: 0.6267
* **Mean Dice Coefficient**: 0.7258
* **Mean Pixel Accuracy**: 0.9936

These metrics reflect the model’s robustness across varied patient cases and image qualities.

---

## Visual Examples of Segmentation

![example](images\seg_exp.png)

These visualizations clearly demonstrate the model’s ability to localize tumors with high precision and overlap, building confidence in its real-world usage.

---

## Post-Classification Integration

The segmentation module is **only triggered after** the image passes the classification pipeline and is labeled as a valid brain MRI. This conditional execution ensures computational efficiency and avoids unnecessary predictions on irrelevant or invalid input images.

---

## Summary

* The segmentation model uses a robust U-Net architecture for binary mask generation.
* Performs strongly with an F1 score of \~0.80 and IoU of \~0.72.
* Supports downstream applications via accurate tumor localization.
* Visualization outputs offer strong clinical interpretability.

This segmentation stage completes the intelligent imaging pipeline, bridging raw diagnostic input to structured, actionable output.
