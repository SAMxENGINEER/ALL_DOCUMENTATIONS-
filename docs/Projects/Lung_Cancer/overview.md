# **Lung Cancer Detection using Machine Learning & Deep Learning**

**[🎥 Watch the Project Demo on Vimeo](https://vimeo.com/1110242693?share=copy)**

## **Overview**

This project was developed as part of an **informal freelance engagement** for someone I personally knew.
It was not conducted through an online freelancing platform, so there was **no formal certificate or platform record** — the work was done directly, with payment provided upon delivery.

It represents one of my **earlier deep learning projects**, undertaken during the initial stages of my journey into AI and medical imaging. Despite being early in my career, the project successfully combined **traditional Machine Learning (ML)** methods with **modern Deep Learning (DL)** techniques to address a critical healthcare challenge: early detection of lung cancer from CT scan images.

---

## **Objective**

The primary aim was to design and implement a system capable of:

1. **Detecting lung cancer** from CT scan images.
2. **Classifying cases** into one of four categories:
    * Adenocarcinoma
    * Large Cell Carcinoma
    * Squamous Cell Carcinoma
    * Normal (Healthy lungs)
3. Evaluating performance using **two distinct approaches**:

   * **Machine Learning**: Classical algorithms for feature-based classification.
   * **Deep Learning**: Convolutional Neural Networks (CNNs) for automated feature extraction.

---

## **Dataset**

* **Source:** Kaggle – *Chest CT Scan Images Dataset* ([Link of dataset](https://www.kaggle.com/datasets/mohamedhanyyy/chest-ctscan-images))
* **Format:** JPG & PNG images.
* **Size:** Four classes, with balancing achieved through data augmentation.
* **Preprocessing:**
    * Removal of duplicates and corrupt images.
    * Standardization to RGB format.
    * Image resizing and normalization.
    * Augmentation techniques (horizontal flips, rotations, brightness/contrast adjustments, Gaussian noise).

---

## **Tools & Technologies**

| Category      | Tools / Libraries                  |
| ------------- | ---------------------------------- |
| **Languages** | Python                             |
| **ML**        | Scikit-learn, OpenCV               |
| **DL**        | TensorFlow, Keras, Albumentations  |
| **Utilities** | NumPy, Pandas, Matplotlib, Seaborn |

---

## **Approach & Methods**

**1. Machine Learning Phase**

* Algorithms: Logistic Regression, Decision Tree, Random Forest, KNN, Gaussian Naïve Bayes.
* Feature-based classification using preprocessed images.
* Best model: **KNN** with **97.69% accuracy**.

**2. Deep Learning Phase**

* Architectures: Single Layer CNN, Multi-Layer CNN, ResNet-like, VGG16 (Transfer Learning), ANN.
* Direct learning from image pixels through CNN-based feature extraction.
* Best model: **Multi-Layer CNN** with **98.81% accuracy**.

---

## **Results Summary**

| Approach | Best Model          | Accuracy |
| -------- | ------------------- | -------- |
| ML       | K-Nearest Neighbors | 97.69%   |
| DL       | Multi-Layer CNN     | 98.81%   |

---

## **Key Takeaways**

* Reinforced understanding of **data preprocessing** and its role in improving model accuracy.
* Learned to handle **class imbalance** through augmentation techniques.
* Experienced in **evaluating multiple models** across both ML and DL workflows.
* Delivered a fully functional solution meeting the client’s requirements.

---

## **Project Structure**

The documentation is organized into two main sections:

* **ML/** – Detailed documentation of the Machine Learning phase.
* **DL/** – Detailed documentation of the Deep Learning phase.

A comparative evaluation of both approaches is also provided for reference.