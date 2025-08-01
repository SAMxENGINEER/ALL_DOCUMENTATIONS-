# 01 – Setup and Usage

This section explains how to set up and use the Brain Tumor Detection System either **locally** or via the **deployed web application**.

---

## Repository Access

> **Note**: This GitHub repository is **private**.
> To clone or contribute, you must have collaborator access. If you require access, please contact the repository owner.

---

## 🔧 Local Setup Instructions

### 1. **Clone the Repository (with Authentication)**

You can clone using either **SSH** (recommended for contributors) or **HTTPS with personal access token (PAT)**.

#### Option A: Using SSH (if your key is added to GitHub)

```bash
git clone git@github.com:SAMxENGINEER/Brain_tumor_seg.git
```

#### Option B: Using HTTPS with GitHub Token

```bash
git clone https://<your-username>:<your-token>@github.com/SAMxENGINEER/Brain_tumor_seg.git
```

> Replace `<your-username>` and `<your-token>` with your GitHub credentials.
> To generate a token: [github.com/settings/tokens](https://github.com/settings/tokens)

---

### 2. **Create and Activate Virtual Environment**

```bash
python -m venv venv
source venv/bin/activate         # On Windows: venv\Scripts\activate
```

---

### 3. **Install Dependencies**

```bash
pip install -r requirements.txt
```

---

## ▶️ Run the Application Locally

```bash
streamlit run app.py
```

The app will open in your browser at:

```
http://localhost:8501
```

---

## 🌐 Access the Deployed Web App

For direct access without setup:

* **Live Web App**: [https://braintumor-ai.streamlit.app](https://braintumor-ai.streamlit.app)

---

## 📁 Project Structure

```txt
Brain_tumor_seg/
├── app.py
├── models/
│   ├── validator_model.h5
│   ├── classifier_model.h5
│   └── segmentation_model.h5
├── requirements.txt
└── README.md
```

---

## 📸 Upload Guidelines

* Upload images must be single-slice **brain MRI scans**.
* Supports `.jpg`, `.jpeg`, or `.png` formats.
* Validator model will reject non-brain or invalid images.
