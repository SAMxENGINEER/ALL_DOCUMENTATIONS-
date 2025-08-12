# Deployment & Integration

## 1. Overview

Once a model is trained and evaluated in **Creation Ground**, it can be:

1. **Deployed within the platform** for immediate testing and usage.
2. **Downloaded** for integration into other applications or workflows.
3. **Hosted online** using services like Streamlit Cloud or Render for public access.

---

## 2. Deployment Options

### 2.1 Streamlit Cloud

- Primary hosting platform for the Creation Ground web application.
- Enables direct user access without local installation.
- Supports interactive model usage and visualization.

**Live Link:** [Creation Ground on Streamlit Cloud](http://creation-ground.streamlit.app/)  

---

### 2.2 Render Hosting

- Alternative hosting platform, ideal for backend integrations or extended uptime requirements.
- Can be configured to serve both the application and an API endpoint.

**Live Link:** [Creation Ground on Render](https://creation-ground.onrender.com)  

---

### 2.3 Local Execution (Offline Mode)

- Users can clone the repository and run the application locally using Python.
- Recommended for private datasets or when internet access is limited.

**Basic Steps:**

```bash
git clone https://github.com/SAMxENGINEER/Creation-Ground.git
cd Creation-Ground
pip install -r requirements.txt
streamlit run main.py
```

---

## 3. Model Integration in External Projects

After downloading the trained model, integration can be done using Python.

**Example Code:**

```python
import pickle
import pandas as pd

# Load the trained model
with open('trained_model.pkl', 'rb') as f:
    model = pickle.load(f)

# Load new data for prediction
new_data = pd.read_csv('new_dataset.csv')

# Make predictions
predictions = model.predict(new_data)
print(predictions)
```

The `.pkl` or `.joblib` model file works with any Python environment that has the required dependencies installed.

---

## 4. GitHub Repository

**Repository:** [Creation Ground GitHub](https://github.com/SAMxENGINEER/Creation-Ground)

> **Note:** If this repository is set to private, then request for access permissions.

---

## 5. Workflow Position

Deployment & Integration is the **final stage** in the Creation Ground workflow:

1. Data is processed and features engineered.
2. Model is trained and evaluated.
3. Final model is exported or deployed.
4. Model is integrated into real-world workflows.
