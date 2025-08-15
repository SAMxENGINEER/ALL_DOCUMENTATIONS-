# Model Saving & Streamlit Integration (Machine Learning)**

## **12.1 Model Saving**

### **Purpose**

After the evaluation phase, the **best-performing machine learning models** were saved to enable reuse without retraining. This ensures faster deployment and easy portability across environments.

---

### **Why Joblib?**

* **Optimized for large NumPy arrays** – Ideal for storing models containing large numerical data.
* **Faster serialization/deserialization** – More efficient than Pickle for large objects.
* **Seamless Scikit-Learn support** – Directly supports most ML models without additional configuration.

---

### **Saving Process**

1. **Select the best model** – Based on evaluation results (e.g., **KNN**, Logistic Regression, or Random Forest).
2. **Save the model** – Exported to a `.joblib` file using:

   ```python
   import joblib
   joblib.dump(model, "best_model.joblib")
   ```
3. **Load for reuse** – The saved model can be reloaded instantly for inference:

   ```python
   model = joblib.load("best_model.joblib")
   ```
4. **Advantages** – Avoids retraining, enabling direct predictions in production systems.

---

## **12.2 Integration with Streamlit**

### **Purpose**

To transform the trained model into an **interactive, user-friendly web application** for lung cancer classification, enabling real-time predictions without requiring deep coding knowledge from end-users.

---

### **Why Streamlit?**

* **Minimal development time** – Build and deploy an app with just Python scripts.
* **Interactive features** – File uploads, sliders, and real-time updates.
* **Lightweight deployment** – Can run locally or be hosted on cloud platforms with minimal setup.

---

### **Integration Workflow**

1. **Load Saved Models** Import `.joblib` models into the Streamlit script for use.
2. **User Input Handling** Enable **image uploads** or manual entry of relevant medical features.
3. **Model Inference** Process the input data and generate predictions instantly.
4. **Result Display** Show predicted class and associated probability scores.
5. **Visualization Support** Include:
     * Bar charts of prediction probabilities
     * Confusion matrix displays
     * Summary of classification metrics

---

### **Outcome**

The final integration resulted in:

* **A complete ML pipeline** accessible via a browser-based UI.
* **Real-time decision support** for lung cancer classification.
* **Deployment-ready system** for medical professionals and researchers, without requiring deep programming expertise.