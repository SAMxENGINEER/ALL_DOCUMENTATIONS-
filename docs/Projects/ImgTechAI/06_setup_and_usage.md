# Setup and Usage

This guide provides instructions to set up and run **ImgTechAI** locally or in a cloud environment.

---

## Prerequisites

* **Python 3.10 or higher**
* **pip** (Python package manager)
* A virtual environment (recommended: `venv` or `conda`)

---

## Installation

1. **Clone the Repository**

   ```bash
   git clone https://github.com/SAMxENGINEER/ImgTechAI.git
   cd ImgTechAI
   ```

   > 📌 If the repository is private, please request access before cloning.

2. **Create and Activate Virtual Environment**

   ```bash
   # Using venv
   python -m venv venv
   source venv/bin/activate   # Linux/Mac
   venv\Scripts\activate      # Windows
   ```

3. **Install Dependencies**

   ```bash
   pip install -r requirements.txt
   ```

---

### Running the Application

1. **Start the Streamlit App**

   ```bash
   streamlit run app.py
   ```

2. **Access in Browser**

   * Open [http://localhost:8501](http://localhost:8501) in your web browser.

---

## Deployment Options

* **Streamlit Cloud (Recommended)**

  1. Push the repository to GitHub.
  2. Login to [Streamlit Cloud](https://streamlit.io/cloud).
  3. Deploy by linking the GitHub repo.

* **Custom Server / Docker (Optional)**

  * The app can be containerized using Docker for scalable deployment.

---

## Assets

* Ensure the following assets are in place before running:

  * `static/IMAGE_TECH_AI.png` → Logo for sidebar branding.
  * `static/IMAGE_TECH_AI_favicon.png` → Favicon for browser tab.

---

## Quick Start (One-Liner)

```bash
pip install -r requirements.txt && streamlit run app.py
```

---

With these steps, ImgTechAI can be set up and run locally within minutes, or deployed online for global access.
