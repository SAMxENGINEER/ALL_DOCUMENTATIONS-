# Setup & Installation Guide

This guide walks through setting up ExamPrompt AI for local development and deployment. The process includes installing dependencies, configuring environment variables, and running the application.

---

## 1. Prerequisites

Before starting, ensure the following tools are installed:

- **Python 3.10+**
- **pip** (Python package manager)
- **Git** (recommended for version control)
- **Docker** (optional, for containerized deployment)

---

## 2. Clone the Repository

```bash
git clone https://github.com/your-username/examprompt-ai.git
cd examprompt-ai
````

---

## 3. Set Up a Virtual Environment

It is recommended to isolate dependencies using a virtual environment.

```bash
python -m venv venv
source venv/bin/activate        # Linux / macOS
venv\Scripts\activate           # Windows
```

---

## 4. Install Python Dependencies

Install all required Python packages using:

```bash
pip install -r requirements.txt
```

If your application uses OCR features, you may also need system dependencies:

### For Ubuntu/Debian:

```bash
sudo apt-get update
sudo apt-get install -y poppler-utils tesseract-ocr
```

### For Windows:

* Install [Poppler for Windows](https://github.com/oschwartz10612/poppler-windows)
* Install [Tesseract OCR](https://github.com/tesseract-ocr/tesseract)

Ensure both tools are added to your system `PATH`.

---

## 5. Environment Variables

Create a `.env` file in the project root directory with the following structure:

```
GOOGLE_API_KEY=your_google_api_key
GROQ_API_KEY=your_groq_api_key
```

> Ensure this file is **never committed** to version control. Add `.env` to `.gitignore`.

---

## 6. Running the Application Locally

### If using Flask backend:

```bash
python app.py
```

This runs the app on:

```
http://localhost:7860/
```

---

## 7. Running with Docker (Optional)

To containerize and run the application:

```bash
docker build -t examprompt-ai .
docker run -p 7860:7860 examprompt-ai
```

Access the app at:

```
http://localhost:7860/
```

---

## 8. Troubleshooting

* **No response from LLM?** Check if API keys are set correctly in `.env`.
* **OCR errors?** Ensure `tesseract-ocr` and `poppler-utils` are installed and accessible via your system's path.
* **Dependencies not installing?** Ensure you're using Python 3.10+ and a clean virtual environment.

---

## 9. Production Recommendations

For deploying to production environments:

* Use `gunicorn` or `uvicorn` instead of Flask’s built-in server.
* Place a reverse proxy (e.g., Nginx) in front of the app for HTTPS support and load balancing.
* Use services like **Render**, **Hugging Face Spaces**, or **Docker Swarm/Kubernetes** for cloud deployment.
* Secure environment variables using a secret manager or cloud environment config.

---

## 10. Optional Integrations (Coming Soon)

* Firebase (Authentication, Firestore)
* Supabase (PostgreSQL, Auth, Storage)
* LangSmith (LangChain evaluation & observability)
* Pinecone / Weaviate (cloud vector store)

---
