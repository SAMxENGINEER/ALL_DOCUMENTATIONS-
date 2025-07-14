# API Reference

This document provides an overview of the key API endpoints exposed by the Flask backend of the MedAI system. These APIs handle both user authentication and multimodal interaction (text/image).

---

## Base URL

```
https://med-ai-bot-70qb.onrender.com
```

> All API routes listed below are relative to this base.

---

## Authentication Endpoints

### `POST /login`

**Description:** Authenticates a user and initiates a session.

**Form Data:**

```json
{
  "email": "user@example.com",
  "password": "your_password"
}
```

**Returns:** Redirects to `/chat` on success. Returns error message on failure.

---

### `POST /signup`

**Description:** Registers a new user with email and password.

**Form Data:**

```json
{
  "email": "newuser@example.com",
  "password": "new_password"
}
```

**Returns:** Redirects to `/chat` on success. Returns error message on failure.

---

### `GET /logout`

**Description:** Logs the user out and clears the session.

**Returns:** Redirects to the login page.

---

## Chat & Prediction Endpoints

### `POST /api/chat`

**Description:** Handles both text-based queries and image-based predictions.

**Usage Cases:**

* If a user sends a **text message**, it routes the input to LangChain agent with context.
* If the user **uploads an image**, it first checks for human skin validity and then predicts the skin condition.

**Headers:**

```http
Content-Type: application/json
or
Content-Type: multipart/form-data (for image)
```

#### Text Request Body

```json
{
  "message": "What is Actinic Keratosis?"
}
```

#### Image Upload Request

Send as form-data:

```bash
image: (binary file)
```

**Response:**

```json
{
  "response": "Model predicted: Actinic_Keratosis with 78.45% confidence."
}
```

Or

```json
{
  "error": "The uploaded image does not appear to contain human skin."
}
```

---

## Notes

* All sessions are authenticated via Firebase token stored in Flask session.
* Uploaded images are processed in-memory and **not stored**.
* Firestore stores the conversation context per user to improve coherence.

---

Let us know if you would like a Postman collection or sample cURL commands for testing these endpoints.
