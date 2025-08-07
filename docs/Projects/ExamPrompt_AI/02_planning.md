# Planning and Approach

## Overview

ExamPrompt AI is being developed as a comprehensive exam-preparation assistant that allows users to upload academic content—such as syllabi, notes, textbooks, or handwritten material—and receive AI-generated questions, answers, and summaries tailored to that content. The core idea is to transform static documents into interactive, personalized learning tools using a flexible and modular AI-driven pipeline.

---

## Document Handling Strategy

A key technical challenge lies in reliably extracting usable content from a wide range of document types. To address this, the system uses a hybrid extraction strategy based on file type and content structure.

### Supported Formats

| Format     | Strategy                                    |
|------------|---------------------------------------------|
| `.pdf`     | Extract text with PyMuPDF; fallback to OCR if scanned |
| `.txt`     | Directly read using Python file I/O         |
| `.docx`    | Parse using `python-docx`                   |
| `.jpg/.png`| OCR using EasyOCR                           |

### Smart Content Routing

- **Text-based files** are processed with direct parsers (`PyMuPDF`, `python-docx`, `open()`).
- **Scanned or handwritten content** is processed using **EasyOCR**.
- **Each page or section is auto-classified** to determine whether text is extractable or OCR is needed.

This layered approach ensures support for mixed documents and edge cases such as scanned PDFs with embedded tables or handwritten annotations.

---


## Processing Flow

```mermaid
flowchart TD


    A[User Uploads File]--> B{File Type?}
    
    B --> C1[PDF] 
    B --> C2[TXT] 
    B --> C3[DOCX]
    B --> C4[Image JPEG/JPG/PNG]

    C1 --> D1{Text Present?}
    D1 -->|Yes| E1[Extract with PyMuPDF]
    D1 -->|No| F1[Convert to Image → OCR with EasyOCR]

    C2 --> E2[Read using open]
    C3 --> E3[Parse with python-docx]
    C4 --> F2[OCR with EasyOCR]

    E1 --> G[Text Preprocessing]
    F1 --> G
    E2 --> G
    E3 --> G
    F2 --> G
   
   G[Text Preprocessing] --> G1[DocumentHandler Class]
    G1 --> H[Chunk & Clean Text]
    H --> I[Embed with LangChain]
    I --> J[Store Embeddings → FAISS or Firestore Memory]

    J --> K[User Asks a Question]
    K --> K1[Add Chat History + Tools Calculator, etc.]
    K1 --> L[Retrieve Relevant Chunks]
    L --> M1[LLM: Groq / Gemini / GPT]
    M1 --> M[Send to LLM via LangChain]
    M --> N[Generate Answer/Questions/Summary]
    N --> O[Display Output in Web UI]

```

---

1. **User Upload**
   - Supported formats: `.pdf`, `.txt`, `.docx`, `.jpg`, `.png`
   - Each file is inspected and routed to its appropriate parser

2. **Text Extraction**
   - Pages with digital text: parsed using PyMuPDF or python-docx
   - Image-only or scanned pages: processed using EasyOCR
   - Output is unified into a clean, structured format

3. **Preprocessing & Chunking**
   - Clean and normalize extracted text
   - Split into logical sections for easier embedding and context retrieval

4. **Embedding & Storage**
   - Use LangChain to generate vector embeddings
   - Store in memory or persistent store for similarity search

5. **Query & Generation**
   - User asks a question via frontend
   - Relevant chunks are retrieved and passed to the LLM
   - Response is generated using context-aware prompting

6. **Output**
   - Generated content is displayed (answers, summaries, or follow-up questions)
   - Users can interact further or modify input scope

---

## Design Principles

- **Robust Input Handling**: Built to support a wide variety of academic document formats
- **Modular Architecture**: Each processing stage is replaceable or upgradeable
- **User-Friendly Experience**: Minimal effort needed to get meaningful output
- **Scalability**: Designed to grow in complexity, scope, and performance
- **Extensibility**: Easy to integrate more file types, new models, or UI features

---

