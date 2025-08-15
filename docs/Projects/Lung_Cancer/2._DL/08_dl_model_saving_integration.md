# Model Saving & Streamlit Integration (Deep Learning)**

## **12.1 Model Saving and Callbacks**

### **Purpose**

After training and evaluating the deep learning models, saving them in their optimal state ensures they can be reused for inference or deployment without retraining. Callbacks were also implemented to improve training efficiency and avoid overfitting.

---

### **1. Model Checkpointing**

* **Implementation:** `ModelCheckpoint` callback from Keras/TensorFlow.
* **Functionality:** Saved the model at the epoch with the highest validation accuracy.
* **Configuration:**

      * `save_best_only=True` → Stores only the best weights, preventing unnecessary storage of suboptimal models.
      * **Format:** Saved as `.h5` files for easy loading.
      * **Naming:** Files were named according to the architecture (e.g., `multi_layer_cnn_best.h5`).

---

### **2. Early Stopping**

* **Purpose:** Prevent overtraining when no further improvement in validation loss is detected.
* **Configuration:**

      * Monitored `val_loss`.
      * Training stopped after a set patience period without improvement.
      * Reduced computational time while maintaining optimal performance.

---

### **3. Final Model Saving**

* After completing training, the **entire model** (architecture, weights, optimizer state) was saved using:

  ```python
  model.save("final_model_name.h5")
  ```

* This ensured:

      * Easy reloading for further training or inference.
      * Preservation of both structure and learned parameters.

---

### **Conclusion**

The combination of **ModelCheckpoint** and **EarlyStopping** ensured that:

* Only the **most optimal** version of each model was saved.
* Training time was reduced.
* Models are now deployment-ready for lung cancer classification.

---

## **12.2 Integration with Streamlit**

### **Purpose**

To create a **real-time, web-based classification tool** for lung CT scans, enabling predictions across four classes:

* **Adenocarcinoma**
* **Large Cell Carcinoma**
* **Normal**
* **Squamous Cell Carcinoma**

---

### **1. Model Loading**

* The best-performing `.h5` model was loaded into the Streamlit application using:

  ```python
  from tensorflow.keras.models import load_model
  model = load_model("best_model.h5")
  ```

---

### **2. User Interface Design**

* **File Uploader** – Allows users to upload CT scan images.
* **Preprocessing Pipeline** – Resizes and normalizes the uploaded image to the model’s expected input shape.
* **Prediction Button** – Executes inference when clicked.
* **Results Display** – Shows:
     * Predicted class.
     * Confidence scores for all classes.
     * Highlighted most probable class.

---

### **3. Model Inference**

Workflow after image upload:

1. Preprocess image to match input requirements.
2. Pass image to the loaded model.
3. Retrieve probability scores for each class.
4. Display results with clear labeling.

---

### **Outcome**

The integration provided:

* **Interactive, user-friendly classification tool** for medical professionals and researchers.
* **Deployment-ready** solution for real-time lung cancer detection.
* Ability to extend the system with visual aids such as **heatmaps** or **Grad-CAM** for explainability.