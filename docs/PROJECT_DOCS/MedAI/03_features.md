# Features of MedAI

MedAI is a multi-modal AI-driven skin health assistant designed to provide intelligent, contextual responses to both text and image-based inputs. Below are its core features, grouped by functionality.

---

## 1. User Authentication & Session Management

- **Firebase Integration**  
  Secure user registration, login, and logout are handled through Firebase Authentication.  
- **Session Persistence**  
  User sessions are tracked via Flask sessions, and all chat history is stored per user in Firestore, ensuring a personalized and consistent experience.

---

## 2. Conversational AI (Text Input)

- **Powered by LangChain + Gemini**  
  Users can ask questions related to skin health or general medical topics. The chatbot is built using LangChain with Google’s Gemini model for high-quality, contextual answers.

- **Integrated Tools for Richer Responses**  
  - **PubMed**: Medical research results to support AI responses.
  - **DuckDuckGo & TavilySearch**: Web search tools to expand beyond static knowledge.
  - **Conversation Memory**: Chat history is passed to the agent to retain and build on prior context.

---

## 3. Image-Based Skin Condition Analysis

- **Dual CNN Architecture**
  - **Human Skin Validation (CNN-1)**  
    Verifies whether the uploaded image is a valid photo of human skin. Prevents misuse or irrelevant inputs that could corrupt predictions.
  - **Skin Condition Classification (CNN-2)**  
    If valid, the image is passed to a second CNN model that classifies it into one of four categories:
    - Actinic Keratosis
    - Benign Tumors
    - Normal
    - Skin Cancer

- **Preprocessing Pipeline**  
  Uploaded images are resized, normalized, and converted to the required format before prediction.

- **Confidence Reporting**  
  Predictions are returned along with a confidence score to help the user assess reliability.

---

## 4. Chat Integration for Images

- **Hybrid Flow**  
  If an image is uploaded, the skin condition prediction result is combined with the ongoing conversation history and presented within the chatbot interface.

- **Response Management**  
  All image responses are also stored in the Firebase chat history along with user prompts.

---

## 5. Web Interface (Flask + HTML)

- **Pages**
  - `login.html`: Authentication page for login and signup.
  - `chat.html`: Main chat interface with image upload support.

- **Routing**
  - `/login`, `/signup`, `/logout`: Handle user auth.
  - `/chat`: Chat interface.
  - `/api/chat`: Accepts both JSON (text) and multipart (image) requests.

---

## 6. Deployment and Hosting

- **Deployed on Render**  
  Live instance available at: [https://med-ai-bot-70qb.onrender.com](https://med-ai-bot-70qb.onrender.com)
- **.env Config Support**  
  Environment variables are managed via `.env`, supporting secrets, Firebase config, and model paths.
- **Model Downloads**  
  Skin models can be pre-downloaded or loaded via scripts using `gdown` from Google Drive.

---

## Additional Highlights

- Robust error handling for:
    1. Invalid login attempts
    2. Malformed inputs
    3. Corrupted or incorrect image formats
- Modular backend design using:
    1. Flask for routing
    2. LangChain for agent orchestration
    3. Keras for CNN model inference

---

## Notes

- This tool is designed for **educational and research purposes** only.
- It is not a replacement for licensed medical diagnosis.

