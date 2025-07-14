# Tech Stack

MedAI brings together a variety of modern tools and frameworks from web development, AI/ML, and cloud infrastructure to deliver an integrated multi-modal chatbot experience.

---

## Core Technologies

| Category              | Technology                  | Purpose |
|-----------------------|-----------------------------|---------|
| Backend Framework     | Flask                       | Web server and routing |
| Authentication        | Firebase Authentication     | Secure user login and session handling |
| Database              | Firebase Firestore          | Store chat history and user metadata |
| Environment Config    | python-dotenv               | Load and manage `.env` variables |

---

## AI & NLP Stack

| Component             | Library / Tool              | Purpose |
|-----------------------|-----------------------------|---------|
| LLM Integration       | LangChain                   | Agent orchestration and tool integration |
| Language Model        | Gemini via `ChatGoogleGenerativeAI` | Conversational reasoning |
| Research Tools        | PubMed, DuckDuckGo, TavilySearch | Fetch medically relevant external content |
| Tool Agent Logic      | LangChain ReAct Agent       | Enables tool-calling with reasoning and context awareness |

---

## Machine Learning Models

| Component                    | Library / Framework     | Details |
|------------------------------|--------------------------|---------|
| Skin Condition Classifier    | TensorFlow (Keras)       | CNN model for detecting 4 skin conditions |
| Human Skin Validator         | TensorFlow (Keras)       | CNN model to filter non-human skin images |
| Image Preprocessing          | Pillow (PIL), NumPy      | Resize, normalize, convert image data |
| Model Management             | Joblib / gdown (optional) | Load/save pre-trained models or download from Google Drive |

---

## Frontend

| Component             | Tech                        | Purpose |
|-----------------------|-----------------------------|---------|
| Templates             | HTML (Jinja2 via Flask)     | Web interface rendering |
| Styling               | Bootstrap / Custom CSS      | Responsive layout and design |
| Forms & Requests      | HTML Forms, JS Fetch API    | Handle login, chat, and image uploads |

---

## Deployment & Environment

| Tool                  | Purpose |
|-----------------------|---------|
| Render                | Hosting for backend and frontend |
| Python 3.10+          | Runtime environment |
| .env File             | Secure API keys and model paths |
| Flask CORS            | Enable cross-origin requests for APIs |

---

## 📦 Python Dependencies

Below is the list of core Python packages used in this project. These are listed in the `requirements.txt` file:

```txt
flask
flask-cors
firebase-admin
langchain
langchain-community
langchain-google-genai
python-dotenv
Pillow
tensorflow
gdown
numpy
gunicorn
xmltodict
hf_xet
langchain-tavily

```

---

## Optional / Future Additions

| Area                  | Potential Technology |
|-----------------------|----------------------|
| Analytics & Logging   | Sentry, Firebase Analytics |
| CI/CD Pipeline        | GitHub Actions, Render Deploy Hooks |
| Mobile UI             | React Native or Flutter (for app version) |
| Offline Mode / Caching| Service Workers or IndexedDB (in frontend) |

---

This stack was chosen to balance simplicity, performance, and educational value — allowing the developer to integrate language models, vision models, and user authentication all in one streamlined project.
