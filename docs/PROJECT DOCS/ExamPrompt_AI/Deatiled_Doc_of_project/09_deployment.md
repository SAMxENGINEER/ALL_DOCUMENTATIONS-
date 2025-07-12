# Deployment Guide

This document covers the full deployment strategy for **ExamPrompt AI**, using Docker with Flask and static templates. The project has been tested and successfully deployed on Hugging Face Spaces after Render's memory limit issues.

---

## 🗂 Folder Structure (Actual Project)

Your project is structured like this:

```

ExamPrompt\_AI/
├── app/
│   ├── app.py
│   ├── document\_handler.py
│   ├── static/
│   │   ├── script.js
│   │   └── style.css
│   └── templates/
│       └── index.html
├── Dockerfile
├── requirements.txt
├── README.md
└── .gitignore

```

---

## ✅ Hugging Face Spaces Deployment (Docker)

This is the recommended approach based on your setup.

### Step-by-Step:

1. Go to [huggingface.co/spaces](https://huggingface.co/spaces) and **create a new Space**
   - Choose **Docker** as the runtime
   - Name it something like `your-username/ExamPrompt-AI`

2. Push your repo to Hugging Face:
   - Include your full folder structure, including:
     - `app/` (with `app.py`, static, and templates)
     - `Dockerfile`
     - `requirements.txt`

3. Hugging Face will automatically build the Docker image and run your app

4. Add your environment variables securely via the **"Secrets"** tab:

```

GOOGLE\_API\_KEY=your\_google\_api\_key
GROQ\_API\_KEY=your\_groq\_api\_key

```

---

## 🐳 Dockerfile (Production Ready)

This is the Dockerfile you already use — and it works great for Hugging Face:

```dockerfile
FROM python:3.10-slim

# Set environment variables
ENV PORT=7860
ENV EASYOCR_CACHE_DIR=/tmp/.easyocr
ENV HOME=/tmp

# Set working directory
WORKDIR /code

# Copy files
COPY . .

# Install dependencies for OCR & PDF
RUN apt-get update && apt-get install -y \
 poppler-utils \
 tesseract-ocr \
 libgl1 \
 && apt-get clean \
 && rm -rf /var/lib/apt/lists/*

# Install Python packages
RUN pip install --no-cache-dir -r requirements.txt

# Expose app port
EXPOSE $PORT

# Run Flask app using Gunicorn
CMD ["gunicorn", "--bind", "0.0.0.0:7860", "--timeout", "120", "--workers", "1", "app.app:app"]
````

---

## 🔥 Why Render Didn’t Work

Render's free tier only offers **512 MiB RAM**, which isn’t enough for:

* EasyOCR
* LangChain embeddings
* FAISS vector operations
* Google/Groq API calls with in-memory vectors

Result: your deployment **crashed during build or runtime** due to memory overflow.

---

## ✅ Local Development

To test before deploying:

```bash
# Run app locally
python app/app.py

# Or using Gunicorn (mimics prod)
gunicorn --bind 0.0.0.0:7860 --timeout 120 --workers 1 app.app:app
```

Then go to:

```
http://localhost:7860/
```

---

## 🛡 Environment Variable Setup

Do **not** commit your `.env` file.

Instead, set secrets like this on Hugging Face:

* Go to **Settings → Secrets**
* Add:

  ```

  GOOGLE_API_KEY=your_api_key
  GROQ_API_KEY=your_groq_key

  ```

---

## 📦 Summary Table

| Platform            | Status | Notes                         |
| ------------------- | ------ | ----------------------------- |
| Hugging Face Spaces | ✅ ✅    | Best option using Docker      |
| Render (Free Tier)  | ❌      | Out of memory (512 MiB limit) |
| Local with Gunicorn | ✅      | Works for development         |
| Docker on VPS       | ✅      | Easily portable anywhere      |

---

## ✅ Deployment Recap

* [x] Flask backend with templates + static
* [x] Works via Docker with OCR + FAISS
* [x] Gunicorn serves app at port `7860`
* [x] Deployable for free via Hugging Face Spaces

