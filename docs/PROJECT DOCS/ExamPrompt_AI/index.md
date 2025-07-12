# 📚 ExamPrompt AI

**Transform your documents into intelligent, interactive study companions**

* **Deployed on**: [Hugging Face Spaces](https://huggingface.co/spaces/samxengineer/ExamPrompt-AI)
* **Environment**: Docker (Flask + Gunicorn)
* **Memory**: Free CPU Tier (\~16 GB available)

---

## 🎯 Overview

**ExamPrompt AI** revolutionizes studying by transforming static documents into dynamic, conversational learning experiences. Upload any PDF or scanned document and instantly generate an AI-powered study assistant that can answer questions, explain concepts, and help you master the material.

---

## ✨ Key Features

* **Multi-Format Support** — Accepts PDFs, scanned images, and plain text files
* **Advanced Processing** — OCR and intelligent text extraction from any document
* **Conversational Interface** — Ask natural-language questions about your content
* **Context-Aware Responses** — Uses retrieval-augmented generation (RAG) for accuracy
* **Real-Time Performance** — Fast document analysis and query response
* **Web-Based UI** — No installation needed; works in all major browsers
* **Privacy-Focused** — Files are processed locally and not stored permanently

---

## 🚀 Live Demo

**🔗 Try it now**: [ExamPrompt AI on Hugging Face Spaces](https://huggingface.co/spaces)

* **Environment**: Docker container
* **Runtime**: Flask + Gunicorn
* **Memory**: 16 GB on free tier
* **Deployment**: Automated using Docker

---

## 🛠️ Technology Stack

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

## 📁 Project Structure

```
ExamPrompt_AI/
├── app/
│   ├── app.py                 # Main Flask application
│   ├── document_handler.py    # Document/OCR processing logic
│   ├── static/
│   │   ├── style.css          # Frontend styles
│   │   └── script.js          # Frontend behavior
│   └── templates/
│       └── index.html         # Web interface template
├── requirements.txt           # Python dependencies
├── Dockerfile                 # Container configuration
├── README.md                  # Project documentation
├── .env.example               # Environment variable template
└── .gitignore                 # Git ignore rules
```

---

## ⚙️ Quick Start

### 🔧 Prerequisites

* Python 3.10+
* Docker
* Google Generative AI API Key
* Groq API Key

### 🧪 Local Development

1. **Clone the Repository**

   ```bash
   git clone https://github.com/yourusername/examprompai.git
   cd examprompai
   ```

2. **Create Virtual Environment**

   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install Dependencies**

   ```bash
   pip install -r requirements.txt
   ```

4. **Configure Environment Variables**

   ```bash
   cp .env.example .env
   # Edit the .env file with your API keys
   ```

5. **Run the App**

   ```bash
   # Development server
   python app/app.py

   # Production server
   gunicorn --bind 0.0.0.0:7860 --timeout 120 --workers 1 app.app:app
   ```

6. **Visit in Browser**

   ```
   http://localhost:7860
   ```

---

### 🐳 Docker Deployment

```bash
# Build the Docker image
docker build -t examprompai .

# Run the container
docker run -p 7860:7860 --env-file .env examprompai
```

---

## 🔐 Environment Variables

Create a `.env` file in the root directory:

```env
# Required API Keys
GOOGLE_API_KEY=your_google_generative_ai_key_here
GROQ_API_KEY=your_groq_api_key_here

# Optional Settings
FLASK_ENV=production
FLASK_DEBUG=False
SESSION_SECRET_KEY=your_session_secret
```

---

## 🔑 Getting API Keys

* **Google AI API**

  * Visit [Google AI Studio](https://makersuite.google.com/app/apikey)
  * Create and copy a new API key
  * Enable the Generative AI API

* **Groq API**

  * Go to [Groq Console](https://console.groq.com/)
  * Generate a new key from the API Keys section

---

## 📖 Usage Guide

### 📤 Upload Documents

1. Click **"Choose File"**
2. Select a PDF or image (Max size: 10MB)
3. Wait for the file to be processed
4. Start chatting with the AI

### 💬 Ask Questions Like:

* “What is the main thesis of chapter 3?”
* “Explain the concept of machine learning.”
* “Compare Keynesian vs classical economics.”
* “Summarize section 2.4.”

### ✅ Best Practices

* Ask clear, specific questions
* Reference headings or sections where possible
* Use follow-ups to continue a conversation
* Maintain context across questions for better accuracy

---

## 🔧 Advanced Configuration

### 🔢 Memory & Chunking

```python
CHUNK_SIZE = 1000
CHUNK_OVERLAP = 200
```

### 🧠 FAISS Index Type

```python
FAISS_INDEX_TYPE = "IndexFlatL2"  # or "IndexIVFFlat"
```

### 🤖 Available Groq Models

```python
GROQ_MODELS = [
    "deepseek-r1-distill-llama-70b",  # currently used
    "mixtral-8x7b-32768",
    "llama2-70b-4096",
    "gemma-7b-it"
]
```

---

## 🐛 Troubleshooting

| Issue              | Solution                                      |
| ------------------ | --------------------------------------------- |
| Out of Memory      | Reduce file size or lower chunk size          |
| OCR Not Accurate   | Use high-quality images with clear text       |
| Slow Responses     | Monitor API limits or upgrade to paid tiers   |
| Docker Build Fails | Check your internet connection and disk space |

### 🐞 Enable Debug Mode

```bash
export FLASK_DEBUG=True
export FLASK_ENV=development
python app/app.py
```

---

## 🤝 Contributing

We welcome contributions!

1. Fork the repo
2. Create a feature branch: `git checkout -b feature/amazing-feature`
3. Commit your changes: `git commit -m "Add amazing feature"`
4. Push to GitHub: `git push origin feature/amazing-feature`
5. Open a Pull Request

### Contributor Guidelines

* Follow PEP 8 formatting
* Include tests for any new features
* Update docs if functionality changes
* Ensure Docker builds without errors

---

## 🗺️ Roadmap

### 🔄 Current Sprint

* [ ] Multi-file upload support
* [ ] Source citation for responses
* [ ] Exportable conversation history

### 🎯 Upcoming Features

* [ ] Firebase Authentication
* [ ] Mobile-responsive improvements
* [ ] Advanced document filters
* [ ] Custom model selection

### 🚀 Future Plans

* [ ] Multilingual support
* [ ] Collaborative study mode
* [ ] LMS (Learning Management System) integration
* [ ] Insight and analytics dashboard

---

## 🆚 Why We Chose Hugging Face Spaces

| Platform      | RAM   | Storage  | Cost | AI Friendly |
| ------------- | ----- | -------- | ---- | ----------- |
| Render (Free) | 512MB | Limited  | ✅    | ❌           |
| HF Spaces     | 16 GB | Generous | ✅    | ✅           |

**Hugging Face Spaces** supports:

* Large document handling with OCR
* FAISS vector operations
* LangChain pipelines and LLM processing
* Cost-effective, scalable deployment

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

---

## 🙏 Acknowledgments

* **LangChain** — LLM orchestration
* **Groq** — High-performance LLM inference
* **Google** — Generative AI embeddings
* **Hugging Face** — Free deployment infrastructure
* **Open Source Community** — For the amazing tools & libraries

---

📘 **Documentation**: [Detailed Doc](https://samxengineer-docs.onrender.com/PROJECT%20DOCS/ExamPrompt_AI/Deatiled_Doc_of_project/00_idea_spark/)

---
