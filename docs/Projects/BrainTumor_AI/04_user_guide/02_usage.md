# 02 – Usage

This section describes how users can interact with the deployed **Brain Tumor Detection System** web application, including its step-by-step flow and key features.

---

## Application Overview

The system consists of three integrated deep learning models:

1. **Validator Model** – Filters out invalid or unrelated images.
2. **Classifier Model** – Identifies tumor type.
3. **Segmentation Model** – Locates and highlights the tumor region.

These components ensure the pipeline is robust, accurate, and resistant to inappropriate inputs.

---

## Demo Video

Watch a quick walkthrough of the app in action:

**🎥 Vimeo Demo**: [Watch Now](https://vimeo.com/1106384259?share=copy)

> This video demonstrates how to upload images, view predictions, and understand segmentation output.

---

## Using the Application

### Step 1: Upload an MRI Image

* Supported formats: `.jpg`, `.jpeg`, `.png`
* Upload must be a grayscale brain MRI scan
* Non-MRI images will be rejected during validation

---

### Step 2: Image Validation

* The system automatically runs the **Validator Model**
* If invalid, an error message prompts re-upload
* If valid, the pipeline continues to classification

---

### Step 3: Tumor Classification

* The **Classifier Model** determines the tumor type:

    * Glioma
    * Meningioma
    * Pituitary
    * No Tumor

* Confidence scores are displayed along with the prediction

---

### Step 4: Tumor Segmentation

* If a tumor is detected, the **Segmentation Model** activates
* It produces a segmentation mask over the MRI image
* Users can compare the original and segmented images

---

## ⚙️ Features

* One-click upload and instant prediction
* Clear visual feedback with overlayed segmentation
* Error handling for unsupported inputs
* Mobile and desktop compatible interface

---

## Best Practices

* Upload isolated MRI slices (not composite screenshots)
* Recommended input size: 256x256 grayscale
* Avoid noisy or blurred scans for optimal accuracy
