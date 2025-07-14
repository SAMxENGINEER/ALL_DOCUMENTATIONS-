# Setup & Usage Instructions

This section provides a step-by-step guide for setting up and running the MedAI application locally or in a cloud environment.

---

## 1. Clone the Repository

```bash
git clone https://github.com/SAMxENGINEER/MedAI_Skin_.git
```

---

## 2. Install Dependencies

Make sure you have Python 3.10+ installed. Then, install the required packages:

```bash
pip install -r requirements.txt
```

---

## 3. Environment Configuration

Create a `.env` file in the root directory and define all necessary environment variables.

### Required Variables:

#### Firebase Credentials

```env
FIREBASE_API_KEY=
FIREBASE_ADMIN_TYPE=
FIREBASE_ADMIN_PROJECT_ID=
FIREBASE_ADMIN_PRIVATE_KEY_ID=
FIREBASE_ADMIN_PRIVATE_KEY=
FIREBASE_ADMIN_CLIENT_EMAIL=
FIREBASE_ADMIN_CLIENT_ID=
FIREBASE_ADMIN_AUTH_URI=
FIREBASE_ADMIN_TOKEN_URI=
FIREBASE_ADMIN_AUTH_PROVIDER_X509_CERT_URL=
FIREBASE_ADMIN_CLIENT_X509_CERT_URL=
FIREBASE_ADMIN_UNIVERSE_DOMAIN=
FIREBASE_COLLECTION_NAME=
```

#### Application Configuration

```env
FLASK_SECRET_KEY=
SKIN_MODEL_PATH=
HUMAN_SKIN_MODEL_PATH=
```

---

## 4. Run the Application Locally

```bash
python app.py
```

The app will be available at `http://localhost:5000`.

---

## 5. Deploying to Cloud (Render Example)

1. Push your code to a Git repository (e.g., GitHub).
2. Create a new **Web Service** on [Render](https://render.com/).
3. Connect your Git repository and choose:

   * **Environment**: Python 3.10
   * **Build Command**: `pip install -r requirements.txt`
   * **Start Command**: `gunicorn app:app`
4. Add all environment variables in the **Environment** tab.

---

## 6. Usage Flow

### Logging In

* Navigate to `/`
* Login or sign up using email and password

### Chatting

* You can:

    * Ask medical or general questions via text
    * Upload a skin image to detect possible conditions

---

## Notes

* Uploaded images are processed **in-memory** and are **not stored**.
* Chat history is stored per session in Firebase Firestore for continuity.
* Ensure a stable internet connection for API and LLM inference.

---

