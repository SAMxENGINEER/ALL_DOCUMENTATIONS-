# Deployment Guide

## Overview

This document outlines the deployment process for the MedAI web application.

---

## Hosting Platform: Render

MedAI is deployed on **Render**, a cloud hosting platform that supports Python-based web services.

---

## Deployment Architecture

* **Platform**: [Render](https://render.com)
* **Runtime Environment**: Python 3.10
* **Web Server**: Gunicorn (for production-grade deployment)
* **App Entrypoint**: `app.py`
* **Framework**: Flask
* **Memory Limit**: \~512MB (Free Tier)

> Note: Due to Render’s memory limitations, image-based model inference may occasionally fail. Text-based interactions and other features remain unaffected.

---

## Deployment Steps

1. **Prepare GitHub Repository**

   * Push all source code, `requirements.txt`, and `.env.example` to a public or private GitHub repository.

2. **Create a New Web Service on Render**

   * Visit [https://dashboard.render.com](https://dashboard.render.com)
   * Click on "New Web Service"
   * Connect your GitHub account and select the MedAI repository

3. **Configure Settings**

   * **Build Command**: `pip install -r requirements.txt`
   * **Start Command**: `gunicorn app:app`
   * **Environment**: Python 3.10
   * Add all necessary **Environment Variables** (as per your `.env` file)

4. **Deployment**

   * Click "Create Web Service"
   * Wait for the build and deploy to complete
   * Test the live link (usually `https://your-app-name.onrender.com`)

---

## Deployment Checklist

* [x] All dependencies listed in `requirements.txt`
* [x] Flask entrypoint (`app.py`) returns expected responses
* [x] Models (`.h5`) download via `gdown` if not found locally
* [x] Environment variables configured in Render dashboard
* [x] Firebase configuration validated
* [x] CORS enabled for web access

---

## Monitoring

* Use Render’s **Logs tab** to monitor errors and build issues
* Watch for **memory-related errors** during image uploads

---

## Final Deployment URL

The application is live and accessible at:
**[https://med-ai-bot-70qb.onrender.com](https://med-ai-bot-70qb.onrender.com)**

---

## License

This project is released under the **MIT License**. 

You are free to use, modify, and distribute the code with appropriate credit. For full licensing terms, please refer to the [`LICENSE`](LICENSE).

---