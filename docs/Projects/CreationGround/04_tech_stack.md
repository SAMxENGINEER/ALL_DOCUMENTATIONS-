# Technology Stack

## Overview

**Creation Ground** is built on a **modular, Python-centric stack** that integrates powerful machine learning libraries with an **interactive web interface** — ensuring both technical depth and beginner accessibility.

---

## 1. Frontend & User Interface

* **[Streamlit](https://streamlit.io/)** — primary framework for building interactive, data-driven web apps in Python.
* **[streamlit-option-menu](https://pypi.org/project/streamlit-option-menu/)** — enhanced sidebar navigation with icons.
* **HTML/CSS (via Streamlit Markdown)** — fine-tuned control over headings, layouts, and visual styling.

---

## 2. Backend Logic

* **Python 3.x** — core application logic, data handling, and ML integration.
* **Pickle** / **joblib** — serialization and export of trained models.

---

## 3. Machine Learning & Data Processing

* **[scikit-learn](https://scikit-learn.org/)** —

  * Data preprocessing (encoding, scaling, feature selection, PCA)
  * ML algorithms (classification, regression)
  * Evaluation metrics
* **[pandas](https://pandas.pydata.org/)** — dataset loading, cleaning, and manipulation.
* **[numpy](https://numpy.org/)** — numerical computing and array operations.
* **[matplotlib](https://matplotlib.org/)** & **[seaborn](https://seaborn.pydata.org/)** — visualizations for datasets, metrics, and model results.

---

## 4. File Handling

* Supports **.csv** and **.xlsx** dataset formats.
* Automatic file validation for compatible uploads.

---

## 5. Model Export

* **joblib** — save trained models and preprocessing pipelines.
* Fully compatible with any Python environment using scikit-learn.

---

## 6. Deployment & Hosting

- **[Streamlit Cloud](http://creation-ground.streamlit.app/)** — live hosting and sharing of the interactive application.
- **[Render Hosting](https://creation-ground.onrender.com)** — alternative deployment for backend integration and extended hosting options.
- Local execution available for offline use via Python environment.

---

## 7. Development & Documentation

* **MkDocs** — static site generator for project documentation.
* **MkDocs Material Theme** — modern, responsive documentation design.
* **Git** / **GitHub** — version control and collaborative development.
* Patent documentation prepared alongside the technical thesis.

---

## 8. Source Code

The complete source code for **Creation Ground** is available on GitHub:  
🔗 **[Creation Ground Repository](https://github.com/SAMxENGINEER/Creation-Ground)**

> **Note:** If the repository is private, please contact to request access.

---

## Summary Table

| Layer                  | Technology / Library                       | Purpose                                   |
| ---------------------- | ------------------------------------------ | ----------------------------------------- |
| **UI / Frontend**      | Streamlit, streamlit-option-menu, HTML/CSS | Interactive interface & navigation        |
| **Core Language**      | Python 3.x                                 | Application logic                         |
| **ML & Data Handling** | scikit-learn, pandas, numpy                | Preprocessing, model training, evaluation |
| **Visualization**      | matplotlib, seaborn                        | Data and metric visualizations            |
| **File I/O**           | pandas, CSV, Excel support                 | Dataset import/export                     |
| **Model Export**       | joblib, pickle                             | Model and pipeline saving                 |
| **Deployment**         | Streamlit Cloud                            | Hosting and sharing                       |
| **Docs & Versioning**  | MkDocs, MkDocs Material, Git/GitHub        | Documentation & source control            |
| **Source Code**        | [GitHub Repo](https://github.com/SAMxENGINEER/Creation-Ground)                                           | Private code repository            |



