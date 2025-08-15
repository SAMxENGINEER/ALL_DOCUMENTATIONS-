# **Introduction – Machine Learning Phase**

## **Background**

This phase of the project focuses on building a **Machine Learning (ML)** solution for lung cancer detection from CT scan images.
Instead of relying on deep feature extraction through convolutional networks, this approach uses **classical ML algorithms** that operate on engineered features derived from the preprocessed images.

The aim was to create a **computationally lightweight yet accurate** classification system that could run effectively on modest hardware without the need for GPU acceleration.

---

## **Objective**

1. Classify lung CT scan images into one of four categories:

   * Adenocarcinoma
   * Large Cell Carcinoma
   * Squamous Cell Carcinoma
   * Normal (Healthy)
2. Explore multiple ML algorithms to determine the best performer.
3. Compare the ML results with the Deep Learning (DL) phase for overall performance evaluation.

---

## **Approach**

* Preprocessed CT scan images to extract **structured feature representations**.
* Applied a range of ML classifiers including:

  * Logistic Regression
  * Decision Tree
  * Random Forest
  * K-Nearest Neighbors (KNN)
  * Gaussian Naïve Bayes
* Evaluated each algorithm based on accuracy, confusion matrix, and generalization performance.

---

## **Why ML First?**

Starting with ML provided:

* A baseline performance metric before investing in heavier DL architectures.
* Insight into the impact of **feature engineering** on classification accuracy.
* Faster experimentation cycles due to lower computational requirements.

