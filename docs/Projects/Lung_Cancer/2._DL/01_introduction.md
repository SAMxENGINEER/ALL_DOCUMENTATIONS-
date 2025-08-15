# **Introduction – Deep Learning Phase**

## **Background**

This phase of the project focuses on leveraging **Deep Learning (DL)** for the detection and classification of lung cancer from CT scan images.
Unlike the ML phase, where manually engineered features were used, the DL phase employs **Convolutional Neural Networks (CNNs)** to automatically learn feature representations directly from pixel data.

The use of CNN architectures enables the model to capture **spatial patterns** in the CT images, which are crucial for distinguishing between different types of lung cancer and healthy tissue.

---

## **Objective**

1. Develop and train CNN-based models for classifying lung CT scan images into four categories:

   * Adenocarcinoma
   * Large Cell Carcinoma
   * Squamous Cell Carcinoma
   * Normal (Healthy)
2. Experiment with multiple architectures to identify the most effective design.
3. Compare the best DL model’s performance against the ML phase results.

---

## **Approach**

* Utilized **end-to-end learning** to process raw image data without manual feature extraction.
* Implemented multiple architectures:

  * Single Layer CNN
  * Multi-Layer CNN
  * ResNet-like architecture
  * VGG16 (Transfer Learning)
  * Artificial Neural Network (ANN) for comparison
* Applied **data augmentation** to improve generalization and reduce overfitting.
* Evaluated using accuracy, loss curves, and confusion matrices.

---

## **Why DL?**

The Deep Learning approach was chosen because:

* CNNs excel at **image-based pattern recognition**.
* Eliminates the need for **manual feature engineering**.
* Potential to achieve **higher accuracy** than classical ML when trained with sufficient data.