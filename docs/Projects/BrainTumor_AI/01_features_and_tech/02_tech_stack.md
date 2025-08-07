# ⚙️ Tech Stack Overview

The Brain Tumor Detection System is built using a combination of open-source libraries, frameworks, and platforms. Each component of the stack plays a crucial role—from data handling and image processing to model training, user interaction, and deployment. This section outlines the tools and technologies used throughout the development of the system.

---

## 1. Deep Learning and Model Development

| Tool / Framework                     | Role & Usage                                                                                        |
| ------------------------------------ | --------------------------------------------------------------------------------------------------- |
| **TensorFlow**                       | Core deep learning framework used for building and training classification and segmentation models. |
| **Keras**                            | High-level API built on TensorFlow, used to quickly define and train CNN architectures.             |
| **Adam Optimizer**                   | Efficient optimization algorithm for faster convergence during training.                            |

---

## 2. Image Processing and Augmentation

| Tool / Library         | Role & Usage                                                                                   |
| ---------------------- | ---------------------------------------------------------------------------------------------- |
| **OpenCV**             | Used for validating input images (MRI type checking), resizing, and visualization.             |
| **Pillow (PIL)**       | Lightweight image handling during preprocessing stages.                                        |
| **ImageDataGenerator** | Built-in TensorFlow/Keras tool used for data augmentation (flipping, rotating, zooming, etc.). |

---

## 3. Data Handling and Management

| Tool / Library      | Role & Usage                                                                   |
| ------------------- | ------------------------------------------------------------------------------ |
| **NumPy**           | Efficient array manipulation and matrix operations for model input/output.     |
| **Pandas**          | For organizing and storing dataset labels, logs, and performance metrics.      |
| **Kaggle Datasets** | Source of publicly available brain MRI datasets used for training and testing. |

---

## 4. Evaluation and Visualization

| Tool / Library   | Role & Usage                                                                                            |
| ---------------- | ------------------------------------------------------------------------------------------------------- |
| **Matplotlib**   | Used for plotting training/validation curves, confusion matrices, and visualizing segmentation results. |
| **Seaborn**      | Enhanced visualization of heatmaps and classification results.                                          |
| **Scikit-learn** | Generating evaluation metrics such as accuracy, precision, recall, and F1-score.                        |

---

## 5. User Interface and Experience

| Tool / Framework                     | Role & Usage                                                                                                                      |
| ------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------- |
| **Streamlit**                        | Lightweight Python framework for creating the web interface. It allows users to upload images, run predictions, and view results. |
| **Streamlit Widgets**                | Enables file uploads, buttons, and display elements for interaction.                                                              |
| **Matplotlib/Streamlit Integration** | Used to render segmentation overlays and prediction visualizations inside the app.                                                |

---

## 6. Deployment and Accessibility

| Tool / Platform       | Role & Usage                                                                    |
| --------------------- | ------------------------------------------------------------------------------- |
| **Streamlit Cloud**   | Used to deploy the web application for public access. No server setup required. |
| **GitHub**            | Version control and open-source hosting of the project’s source code.           |
| **Render (for Docs)** | Hosted the full project documentation using markdown files.                     |

---

## Summary

The choice of tools was based on ease of integration, open-source accessibility, and strong community support. Together, this tech stack supports an end-to-end solution—from loading and validating MRI scans, to classification and tumor segmentation, to interactive results display and public deployment.
