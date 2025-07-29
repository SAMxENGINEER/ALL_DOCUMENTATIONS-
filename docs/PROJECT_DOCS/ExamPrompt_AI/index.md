# ExamPrompt AI

**Transform your documents into intelligent, interactive study companions**


* **Deployed on**: [Hugging Face Spaces](https://huggingface.co/spaces/samxengineer/ExamPrompt-AI)
* **Environment**: Docker (Flask + Gunicorn)
* **Memory**: Free CPU Tier (~16 GB available)

---

## Overview

**ExamPrompt AI** revolutionizes studying by transforming static documents into dynamic, conversational learning experiences. Upload any PDF or scanned document and instantly generate an AI-powered study assistant that can answer questions, explain concepts, and help you master the material.

---

## Key Features

* Multi-Format Support — Accepts PDFs, scanned images, and plain text files  
* Advanced Processing — OCR and intelligent text extraction from any document  
* Conversational Interface — Ask natural-language questions about your content  
* Context-Aware Responses — Uses retrieval-augmented generation (RAG) for accuracy  
* Real-Time Performance — Fast document analysis and query response  
* Web-Based UI — No installation needed; works in all major browsers  
* Privacy-Focused — Files are processed locally and not stored permanently  

---

## Live Demo

**Try it now**: [ExamPrompt AI on Hugging Face Spaces](https://huggingface.co/spaces)

### Demo Video

[ExamPrompt AI Demo](https://vimeo.com/1101411694?share=copy)

* Environment: Docker container  
* Runtime: Flask + Gunicorn  
* Memory: 16 GB on free tier  
* Deployment: Automated using Docker  

---

## Technology Stack

| Category            | Technology                   | Purpose                                    |
| ------------------- | ---------------------------- | ------------------------------------------ |
| Backend Framework   | Flask + Gunicorn             | Web server and WSGI application            |
| Frontend            | HTML, CSS, JavaScript        | Responsive user interface                  |
| AI Framework        | LangChain                    | LLM orchestration and pipeline             |
| Embeddings          | Google Generative AI         | Document vectorization                     |
| Vector Database     | FAISS                        | Similarity search and retrieval            |
| Language Model      | Groq API (Mixtral/Gemma)     | Question answering and response generation |
| OCR Engine          | EasyOCR + Tesseract          | Extract text from images and scanned docs  |
| PDF Handling        | PyMuPDF + pdf2image          | Parse and convert PDF content              |
| Deployment Platform | Docker + Hugging Face Spaces | Containerized deployment environment       |

---

## Project Structure

```

ExamPrompt\_AI/
├── app/
│   ├── app.py
│   ├── document\_handler.py
│   ├── static/
│   │   ├── style.css
│   │   └── script.js
│   └── templates/
│       └── index.html
├── requirements.txt
├── Dockerfile
├── README.md
├── .env.example
└── .gitignore

```

---

## Quick Start

### Prerequisites

* Python 3.10+  
* Docker  
* Google Generative AI API Key  
* Groq API Key  

### Local Development

```bash
git clone https://github.com/yourusername/examprompai.git
cd examprompai

python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

pip install -r requirements.txt

cp .env.example .env
# Edit the .env file with your API keys

python app/app.py  # Development server

# Or run production server
gunicorn --bind 0.0.0.0:7860 --timeout 120 --workers 1 app.app:app
````

Visit `http://localhost:7860`

---

### Docker Deployment

```bash
docker build -t examprompai .
docker run -p 7860:7860 --env-file .env examprompai
```

---

## Environment Variables

```env
GOOGLE_API_KEY=your_google_generative_ai_key_here
GROQ_API_KEY=your_groq_api_key_here
FLASK_ENV=production
FLASK_DEBUG=False
SESSION_SECRET_KEY=your_session_secret
```

---

## Getting API Keys

* **Google**: [Google AI Studio](https://makersuite.google.com/app/apikey)
* **Groq**: [Groq Console](https://console.groq.com/)

---

## Usage Guide

1. Upload a PDF or image (Max: 10MB)
2. Wait for processing
3. Ask natural-language questions

Examples:

* What is the main thesis of chapter 3?
* Explain the concept of machine learning.
* Summarize section 2.4.

---

## Advanced Configuration

```python
CHUNK_SIZE = 1000
CHUNK_OVERLAP = 200

FAISS_INDEX_TYPE = "IndexFlatL2"

GROQ_MODELS = [
    "deepseek-r1-distill-llama-70b",
    "mixtral-8x7b-32768",
    "llama2-70b-4096",
    "gemma-7b-it"
]
```

---

## Troubleshooting

| Issue              | Solution                                      |
| ------------------ | --------------------------------------------- |
| Out of Memory      | Reduce file size or lower chunk size          |
| OCR Not Accurate   | Use high-quality images with clear text       |
| Slow Responses     | Monitor API limits or upgrade to paid tiers   |
| Docker Build Fails | Check your internet connection and disk space |

---

## Contributing

Follow standard GitHub flow:

1. Fork
2. Create branch
3. Commit
4. Push
5. Pull Request

---

## Roadmap

### Current Sprint

* [ ] Multi-file upload
* [ ] Source citation
* [ ] Exportable conversation logs

### Upcoming

* [ ] Firebase login
* [ ] Mobile-friendly UI
* [ ] Model selector

---

## Why Hugging Face Spaces?

| Platform  | RAM   | Storage  | Cost | AI Friendly |
| --------- | ----- | -------- | ---- | ----------- |
| Render    | 512MB | Limited  | Yes  | No          |
| HF Spaces | 16 GB | Generous | Yes  | Yes         |

---

## License

Licensed under the [MIT License](LICENSE)

---

## Acknowledgments

* LangChain
* Groq
* Google
* Hugging Face
* Open Source tools

---

Documentation: [Detailed Doc](https://samxengineer-docs.onrender.com/PROJECT%20DOCS/ExamPrompt_AI/Deatiled_Doc_of_project/00_idea_spark/)

---

**Documented on: Jul 11, 2025**

