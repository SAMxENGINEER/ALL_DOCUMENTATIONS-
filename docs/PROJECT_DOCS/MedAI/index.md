# MedAI: Skin Health Companion – Documentation Index

**MedAI** is a multimodal, AI-driven assistant designed to provide preliminary analysis and helpful feedback on common skin conditions. By integrating **image classification** and **natural language understanding**, it enables users to explore dermatological concerns through both **uploaded images** and **text-based medical queries**.

This documentation details the entire development lifecycle — from initial concept and planning to model training, deployment, and real-world usage.

---

## Why MedAI?

* Skin diseases are widespread but often underdiagnosed, especially in regions with limited access to dermatologists.
* Most existing tools handle either **image** or **text** inputs — MedAI bridges that gap by combining both.
* Features two custom-trained CNN models:

  * A model to **validate human skin images**
  * A classifier to categorize images into **four diagnostic skin condition groups**
* Integrated with **LangChain and Gemini** for intelligent, context-aware chat responses.
* Designed with privacy in mind: while text data is stored for improving conversations, **images are never saved**.

---

## Key Features

* Dual input support: **text queries** and **image uploads**
* Real-time classification with custom CNNs
* Automatic **skin validation** to filter irrelevant uploads
* Integration with **PubMed and web search** for enriched medical knowledge
* **Firebase backend** for secure authentication, chat logging, and session management
* Public deployment using **Render** for easy access and demonstration

---

## Documentation Index

| Title                         | Description                                                              |
| ----------------------------- | ------------------------------------------------------------------------ |
| **Idea Spark**                | Background, motivation, and inspiration behind MedAI                     |
| **Problem Statement**         | Key challenges in image-based medical support and how MedAI tackles them |
| **Planning & Objectives**     | System overview, flowcharts, and modular design structure                |
| **Features of MedAI**         | Overview of Flask backend, Firebase integration, and logic flow          |
| **Tech Stack**                | Complete list of tools, libraries, and dependencies used                 |
| **System Architecture**       | Functional diagrams, component breakdown, and privacy considerations     |
| **Exploratory Data Analysis** | Visual EDA performed after preprocessing for both CNN models             |
| **Model Training Details**    | Architectures, configurations, evaluation results, and model storage     |
| **Setup & Usage**             | Step-by-step guide to run the project locally and interact with the app  |
| **Usage Guide**               | Screenshots, interaction flow, and how to test queries and uploads       |
| **API Reference**             | Available endpoints with request/response formats                        |
| **Deployment Guide**          | Render deployment steps and environment setup instructions               |

---

## Key Links

* **Live App**: [med-ai-bot-70qb.onrender.com](https://med-ai-bot-70qb.onrender.com)
* **Demo Video**: [Watch Demo](https://vimeo.com/1101410221?share=copy)
* **Source Code**: [GitHub Repository](https://github.com/SAMxENGINEER/MedAI_Skin_)

---

## License

This project is released under the **MIT License**. 

You are free to use, modify, and distribute the code with appropriate credit. For full licensing terms, please refer to the [`LICENSE`](LICENSE).

---