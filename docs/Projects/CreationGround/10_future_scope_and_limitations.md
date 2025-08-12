# Future Scope & Limitations

## 1. Future Scope

Although **Creation Ground** is already a functional, end-to-end ML model creation platform, there are several enhancements planned for future versions:

### 1.1 Expanded Algorithm Library

- Addition of **deep learning models** (e.g., CNNs, RNNs, Transformers) for image, text, and time-series tasks.
- Integration of **AutoML** capabilities for automatic algorithm selection and hyperparameter tuning.

### 1.2 Data Source Integrations

- Support for **direct dataset imports** from cloud storage (Google Drive, Dropbox) and public data repositories (Kaggle, UCI ML Repository).
- Real-time **data streaming support** for IoT and live analytics.

### 1.3 Advanced Visualization

- Interactive plots with **Plotly** for dynamic data exploration.
- Model performance comparison dashboards for multiple algorithms.

### 1.4 Collaboration Features

- Multi-user workspace with role-based permissions.
- Shared projects with version tracking for datasets and models.

### 1.5 Deployment Enhancements

- One-click **API generation** for trained models.
- Export options to containerized environments (Docker) or cloud ML services (AWS SageMaker, Azure ML).

---

## 2. Current Limitations

While powerful, the current version of Creation Ground has certain constraints:

### 2.1 Algorithm Support

- Focused mainly on traditional ML algorithms; deep learning support is minimal.
- Some advanced models may require external libraries not yet integrated.

### 2.2 Data Size Handling

- Processing of very large datasets may be limited by **Streamlit Cloud** resource constraints.
- Recommended to use **local execution** for datasets exceeding 1–2 GB.

### 2.3 Deployment Restrictions

- Current hosted version **does not allow user-deployed models** directly to production environments for security and resource reasons.
- Deployment options are limited to **Streamlit Cloud** and **Render** in this release.

### 2.4 Custom Code Execution

- Users cannot execute arbitrary Python code within the hosted environment for safety.
- Any highly customized processing must be done locally before uploading data.

### 2.5 Private Repository Access

- If the GitHub repository is private, external users must request permission to access the source code.

---

## 3. Vision Statement

The long-term goal for Creation Ground is to become a **universal, no-code machine learning lab** —  
a place where anyone, from a beginner to an expert, can:

- Upload and explore their data.
- Build, train, and optimize models.
- Deploy and share results instantly.
- Collaborate in a secure, interactive environment.

While the current version sets a strong foundation, the **next iterations** will focus on making the platform **more scalable, collaborative, and AI-powered**.
