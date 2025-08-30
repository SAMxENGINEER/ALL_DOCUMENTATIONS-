# Deployment

**ImgTechAI** can be deployed both locally and in the cloud. This section outlines recommended approaches for seamless deployment.

---

### 🚀 Streamlit Cloud (Recommended)

The simplest deployment method is using **[Streamlit Cloud](https://streamlit.io/cloud)**.

1. **Push Repository to GitHub**

   * Ensure your project is uploaded to GitHub:
     [https://github.com/SAMxENGINEER/ImgTechAI](https://github.com/SAMxENGINEER/ImgTechAI)

2. **Deploy on Streamlit Cloud**

   * Log in to [Streamlit Cloud](https://streamlit.io/cloud).
   * Click **New App** and link your GitHub repository.
   * Select the branch (e.g., `main`) and file (`app.py`).
   * Deploy — your app will be live in minutes.

3. **Access the Live App**

   * Public deployment link: [https://imgtechai.streamlit.app/](https://imgtechai.streamlit.app/)

---

### Local Deployment

1. Clone the repository:

   ```bash
   git clone https://github.com/SAMxENGINEER/ImgTechAI.git
   cd ImgTechAI
   ```

2. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

3. Run the app locally:

   ```bash
   streamlit run app.py
   ```

4. Access at: [http://localhost:8501](http://localhost:8501)

---

## Best Practices

* Always use **Python virtual environments** for dependency isolation.
* Keep `requirements.txt` updated for smooth deployment.
* For private repositories, configure **GitHub access tokens** in Streamlit Cloud.

---

With these deployment options, ImgTechAI can run smoothly for both **personal use** and **public sharing**.
