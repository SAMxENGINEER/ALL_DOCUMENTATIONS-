# 00 – Idea Spark 💡

The foundation of this project was laid during a college-level **technical writing competition**, where the objective was to present a meaningful application of technology backed by solid documentation. During early brainstorming sessions, a discussion with a close friend—an epidemiology postgraduate—sparked the idea of applying deep learning to **brain tumor detection**. 

Brain tumors can lead to a wide range of serious health issues—chronic headaches, seizures, memory loss, speech difficulties, and in severe cases, paralysis. Early detection is crucial, often determining both the effectiveness of treatment and the patient’s long-term outcome. However, access to timely diagnosis is often limited, especially in under-resourced healthcare environments.

This challenge presented an opportunity: to build an **AI-powered system** capable of assisting in the **preliminary detection of brain tumors** using MRI scans. The idea combined real-world medical need with technical feasibility, making it an ideal choice for both the competition and future development.

The initial phase focused on classification. A compact **Convolutional Neural Network (CNN)** was developed using TensorFlow and Keras. Trained on publicly available brain MRI datasets, the model demonstrated strong performance:

* **Training Accuracy**: 99.20%
* **Validation Accuracy**: 97.68%
* **Testing Accuracy**: 97.10%
* **Model Size**: 39.5 MB

The model could classify MRI images into four categories:

* **No Tumor**
* **Glioma**
* **Meningioma**
* **Pituitary**

What started as a simple prototype quickly gained momentum. With faculty mentorship, the work was formalized into a research paper and submitted to an IEEE conference—where it was accepted and published. 📄

This early recognition validated the direction of the project and laid the groundwork for **Phase 2**: transforming the research into a fully functional application with real-time inference, tumor segmentation, and a user-friendly web interface. 

