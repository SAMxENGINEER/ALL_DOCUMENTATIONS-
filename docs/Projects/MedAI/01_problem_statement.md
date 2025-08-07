# Problem Statement

Skin diseases represent one of the most prevalent categories of medical conditions worldwide. Despite this, access to reliable and early diagnosis remains a challenge for millions of people. In many parts of the world — particularly in low-resource or rural areas — individuals do not have easy access to dermatologists or specialized skin care facilities. This lack of access often leads to delayed diagnosis, self-medication, or no treatment at all, which can worsen otherwise manageable conditions.

With the growing adoption of artificial intelligence (AI) in healthcare, there is potential to bridge this gap. However, most existing AI-powered medical assistants focus exclusively on either textual symptom checkers or basic image classification tools. These solutions, while promising, are often too narrow in scope and fall short in terms of real-world usability and reliability.

## Key Challenges in Current Solutions

1. **Limited Modality Support**  
   Most chatbot-based assistants accept only text input. While this allows for symptom-based queries, it ignores the vast potential of visual information — which is essential in diagnosing skin-related conditions.

2. **Lack of Input Validation**  
   Even when image-based tools are used, very few systems verify if the uploaded image is suitable or valid. For example, users may upload blurry photos, pictures of objects, or unrelated content — and the model proceeds to give a diagnosis anyway. This introduces serious risks in interpretation and undermines the tool's credibility.

3. **Disjointed Experience**  
   Many systems isolate different functionalities. A user may chat with a bot in one interface and have to upload an image on another platform. There's often no contextual connection between what the user is saying and what they are uploading.

4. **Weak Integration with Research-Backed Sources**  
   Providing credible information is key in any medical support tool. Unfortunately, many solutions rely on static or shallow knowledge bases. Few integrate dynamic, research-backed resources like PubMed or reliable search engines to provide deeper, verifiable responses.

5. **Absence of Contextual Reasoning**  
   Many image analysis tools make predictions based only on pixel data, without taking into account what the user is asking or concerned about. This reduces the relevance and value of the results.

## What MedAI Aims to Solve

MedAI is designed to address these limitations through an integrated, intelligent system that supports both conversation and image-based interaction in a coherent and secure way.

### MedAI Introduces:

- **Multi-Modal Interaction**  
  MedAI allows users to interact using both **text** and **images** in a single session. This enables more detailed, human-like discussions around symptoms, supported by visual evidence.

- **Dual CNN Validation Pipeline**  
  A unique two-stage convolutional neural network (CNN) process ensures quality and reliability:
    1. **Image Validator** – First, a CNN model checks whether the uploaded image is a valid representation of human skin.
    2. **Skin Condition Classifier** – If valid, a second CNN processes the image to predict the most probable skin condition.

- **Context-Aware AI Chat**  
  Powered by **LangChain** and **Gemini**, the chatbot understands user intent, retains conversation history, and augments its answers with real-time outputs from the skin analysis model and online tools.

- **Trusted Information Access**  
  MedAI integrates with sources like **PubMed**, **DuckDuckGo**, and **TavilySearch** to provide verified, medically relevant information when responding to user queries.

- **Secure and Personalized Experience**  
  By using **Firebase** for authentication and session storage, MedAI ensures that each user’s interactions are secure and can be contextually personalized through stored chat history.

### Why This Matters

By validating image inputs before analysis and supporting contextual conversation, MedAI ensures that users receive **more accurate, safer, and reliable responses** — something that is often lacking in existing AI-driven medical assistants.

