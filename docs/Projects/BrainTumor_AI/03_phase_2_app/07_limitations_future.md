# 07 – Limitations and Future Work

## Current Limitations

Despite the system's strong performance across validation and testing phases, several limitations exist that highlight opportunities for improvement in future iterations.

---

### 1. **Monomodal Input (MRI Only)**

The system is currently designed to process only **T1-weighted brain MRI images**. Other modalities such as CT, DTI, or PET are not supported, which limits its applicability across different diagnostic scenarios.

---

### 2. **Limited Clinical Generalization**

The models were trained on publicly available datasets that may not reflect the **full variability of clinical MRI scans**. Differences in scanner hardware, acquisition protocols, and noise profiles could reduce performance in real-world settings.

---

### 3. **Binary Image Validation**

The validator model is binary — it only detects whether an image is a valid brain MRI or not. It does not detect **image quality degradation** (e.g., motion artifacts, low resolution), which could still affect downstream predictions.

---

### 4. **Classification and Segmentation Scope**

The classifier and segmentation models only cover **four diagnostic classes** (Glioma, Meningioma, Pituitary, No Tumor). Other tumor types such as metastases or secondary cancers are not detected.

---

### 5. **Single Slice Analysis**

All predictions are made based on **2D axial slices**. The system does not yet incorporate 3D volumetric analysis, which is often required for accurate tumor boundary estimation in clinical practice.

---

### 6. **Lack of Explainability Features**

While the system provides visual outputs (such as tumor masks), there are currently no integrated **explainability techniques** like Grad-CAM, saliency maps, or attention heatmaps to offer deeper interpretability.

---

## Future Work

To improve system robustness, clinical utility, and model generalization, several enhancements are proposed:

---

### 🔄 1. **Multimodal Input Support**

Extend support to CT, PET, and other MRI modalities. This can improve diagnostic performance, especially in cases where tumor morphology is ambiguous in T1-weighted MRI.

---

### 2. **Volumetric (3D) Model Development**

Incorporate **3D CNNs** or **hybrid architectures** to analyze entire scan volumes instead of single slices. This would provide more comprehensive tumor localization and volumetric measurements.

---

### 3. **Artifact Detection and Filtering**

Develop a quality-check module to filter out **noisy or artifact-prone images** before prediction. This could be integrated as a second-stage validator model.

---

### 4. **Explainable AI Integration**

Add interpretability tools like **Grad-CAM** or **SHAP** to improve clinical trust and model transparency — especially for borderline predictions or high-risk cases.

---

### 5. **External Dataset Evaluation**

Evaluate and fine-tune the model on **hospital-grade, real-world datasets** to improve generalization across different imaging protocols and patient demographics.

---

### 6. **API and Mobile Deployment**

Wrap the system into a lightweight **REST API** or **mobile-first application**, allowing offline use or integration with radiology workflows.

