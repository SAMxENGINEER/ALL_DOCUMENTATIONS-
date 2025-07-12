# Usage Guide

This guide explains how to use ExamPrompt AI from a user’s perspective — from uploading documents to interacting with the AI for question answering.

---

## 1. Access the Application

Depending on your setup, open the app in your browser:

- **Flask version**: `http://localhost:5000/`
- **Streamlit version**: `http://localhost:8501/`
- **Dockerized version**: `http://localhost:7860/`

---

## 2. Upload a Document

On the homepage:

- Click on the **Upload** button.
- Select a `.pdf` file (OCR will be used for scanned documents).
- Once uploaded, the system begins preprocessing:
  - Extracts text using PyMuPDF (or OCR fallback)
  - Splits the text into manageable chunks
  - Converts chunks into embeddings using Google GenAI
  - Stores them in a FAISS vector store

You will see a message when the document is ready for interaction.

---

## 3. Ask Questions

Once the document is loaded:

- Use the chat interface to ask questions in plain English.
- Example questions:
  - *“What is the main topic of chapter 3?”*
  - *“Summarize the conclusion section.”*
  - *“Define the term ‘entropy’ as used in this PDF.”*

---

## 4. How It Works (Behind the Scenes)

Every question triggers this flow:

1. **Your query** is converted into a vector using the same embedding model.
2. The vector is **matched against the document** in the FAISS store.
3. The most relevant chunks are retrieved.
4. These chunks, along with your question, are passed to the **Groq-powered LLM**.
5. A final answer is generated and returned to you.

This ensures all answers are context-aware and document-grounded.

---

## 5. Multi-turn Chat Support

During the session:

- Chat history is preserved in memory.
- You can ask follow-up questions and the system retains context.
- For example:
  - Q1: *What does the author say about ecosystems?*
  - Q2: *Can you elaborate on that with examples from the PDF?*

---

## 6. Tips for Better Responses

- Ask direct and focused questions.
- Use terms or keywords that actually appear in the document.
- Avoid overly generic prompts like “Explain this document” (unless summarization is enabled).

---

## 7. What Happens After Upload?

Uploaded documents are:

- Stored temporarily on the server (cleared after session or restart).
- Not shared externally unless you explicitly integrate cloud storage.

---

## 8. Limitations

- Currently supports only one document at a time.
- Chat history is session-based (lost after refresh unless you add persistence).
- No citation or source highlighting yet (planned).

---

## 9. Planned Features

- Multi-document upload and comparison
- Citation display with each answer
- Document summarization feature
- User login and document history via Firebase
- Mobile-optimized interface

---

## 10. Example Use Cases

- **Students**: Ask questions on textbooks, lecture slides, or exam PDFs.
- **Researchers**: Extract key insights from technical papers.
- **Professionals**: Interact with manuals, policies, or contracts in natural language.

