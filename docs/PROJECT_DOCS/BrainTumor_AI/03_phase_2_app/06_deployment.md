# 06 – Deployment Strategy

## Overview

The **Brain Tumor Detection System** was deployed as a fully interactive web application using **Streamlit Cloud**. This deployment allows users to easily test the system without needing to install any dependencies locally.

The deployed system incorporates a robust pipeline integrating three deep learning models, and provides a clean, interactive user interface for end-users to perform tumor analysis directly from brain MRI scans.

---

## Deployment Platform

We selected **Streamlit Cloud** for deployment due to its:

* Seamless integration with GitHub
* Simple and fast deployment process
* Built-in support for Python-based ML workflows
* Auto-scaling and minimal infrastructure management

---

## Repository Integration

The application was deployed by connecting the **Streamlit Cloud platform** to our **GitHub repository**. The deployment process includes:

1. Pushing all model files, scripts, and assets to the GitHub repository.
2. Linking the repository to Streamlit Cloud.
3. Configuring `app.py` as the entry point.
4. Setting up necessary dependencies in `requirements.txt`.
5. Enabling continuous deployment for automatic updates.

---

## Application Pipeline

Once the user uploads an image through the web UI, the system executes the following steps:

### 1. **Validator Model**

* Verifies if the uploaded image is a valid **brain MRI scan**.
* If the input is invalid, the system stops further processing and notifies the user.
* If valid, the image is passed to the next stage.

### 2. **Classification Model**

* Classifies the MRI into one of the following categories:

  * **No Tumor**
  * **Glioma**
  * **Meningioma**
  * **Pituitary**

### 3. **Segmentation Model**

* If a tumor is detected, the segmentation model highlights the tumor region on the original MRI using a U-Net-based architecture.
* The segmented image is overlaid for visual inspection.

---

## Web Interface (UI)

The application provides a user-friendly interface with the following capabilities:

* Image upload section with drag-and-drop functionality
* Real-time prediction status and confidence scores
* Segmentation overlay display
* Information popups and tumor descriptions
* Downloadable result visuals (optional)

---

## Application Access

* 🌐 **Live App**: [Open Deployed Application](https://braintumor-ai.streamlit.app/)
* 💻 **GitHub Source**: [View on GitHub](https://github.com/SAMxENGINEER/Brain_tumor_seg)

> These links provide open access for evaluation, demonstration, and feedback collection.
If you require access to the app.py and the model files, you may request access to the private repository.

---

## Notes

* The models are stored in compressed formats and loaded dynamically to optimize memory usage.
* The system is tested for multiple image types (.jpg, .png, .jpeg) and different channel formats (1-channel grayscale or 3-channel RGB).
* Security considerations such as upload limits and input filtering are applied to ensure system reliability.

