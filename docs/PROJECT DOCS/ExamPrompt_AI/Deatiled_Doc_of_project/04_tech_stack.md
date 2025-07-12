# Tech Stack

This document outlines the core technologies and libraries that power the ExamPrompt AI platform. It includes the backend framework, language model integration, document handling tools, deployment setup, and optional future enhancements.

---

## Core Web Application

| Package           | Purpose                                                             |
|-------------------|----------------------------------------------------------------------|
| Flask             | Lightweight web framework used for API endpoints and routing logic. |
| Flask-Session     | Manages server-side session state (e.g., chat history).              |
| Werkzeug          | Secure file handling and WSGI utility functions.                    |
| python-dotenv     | Loads environment variables from a `.env` file securely.             |
| gunicorn          | WSGI server used for running the app in production environments.     |

---

## LangChain & LLM Ecosystem

| Package                    | Purpose                                                                 |
|----------------------------|-------------------------------------------------------------------------|
| langchain                  | Framework for building LLM applications using chains and agents.        |
| langchain-community        | Collection of integrations for data loaders, retrievers, and tools.     |
| langchain-google-genai     | Provides embedding support using Google's Generative AI APIs.           |
| langchain-groq             | Integration for fast inference using Groq-hosted LLMs.                  |
| faiss-cpu                  | Local vector store used for semantic document retrieval.                |

---

## Document and PDF Processing

| Package        | Purpose                                                                 |
|----------------|-------------------------------------------------------------------------|
| PyMuPDF        | Extracts text from PDFs with high speed and accuracy.                   |
| pdf2image      | Converts PDF pages to images (used when OCR fallback is required).      |
| python-docx    | Enables reading and parsing of `.docx` Word files.                      |
| Pillow         | Image processing library used in OCR workflows.                         |
| easyocr        | OCR engine for reading text from scanned or image-based PDFs.           |
| numpy          | Used internally by image/OCR tools for matrix and numerical operations. |

---

## Deployment and Tooling

| Tool/Package           | Purpose                                                            |
|------------------------|---------------------------------------------------------------------|
| Docker                 | Containerization for consistent deployment across environments.     |
| Render / Hugging Face  | Hosting environments for public access (Render for Docker; HF Spaces for Streamlit or Flask apps). |
| .env + python-dotenv   | Manages API credentials and environment settings securely.          |

---

## Optional / Future Integrations

| Tool / Service         | Intended Use                                                       |
|------------------------|---------------------------------------------------------------------|
| Firebase               | Authentication and Firestore database integration.                 |
| LangSmith              | Debugging, evaluation, and tracing of LangChain chains.             |
| Supabase               | Real-time database, storage, and user auth (PostgreSQL-backed).     |
| Weaviate / Pinecone    | Cloud-native vector DB alternatives for scalable similarity search. |

---

## 📦 Summary: Key Python Requirements

These are the primary Python packages used to power the **ExamPrompt AI** backend and document processing logic.

---

### Core Web App

```txt
Flask               # Web framework
Flask-Session       # Server-side session management
Werkzeug            # Secure file uploads & utilities
python-dotenv       # Load environment variables from .env
gunicorn            # WSGI server for production deployment
```

---

### LangChain & LLM Integrations

```txt
langchain                 # Core LLM chaining framework
langchain-community       # Community-maintained integrations
langchain-google-genai    # Google Generative AI embeddings
langchain-groq            # Integration with Groq LLMs
faiss-cpu                 # Local vector store for document search
```

---

### Document & PDF Processing

```txt
PyMuPDF          # High-performance PDF text extraction
pdf2image        # Convert PDF pages to images (for OCR)
python-docx      # Word document reading support
Pillow           # Image processing support for OCR workflows
easyocr          # Lightweight OCR engine
numpy            # Math array library (used in OCR/image tools)
```

---

