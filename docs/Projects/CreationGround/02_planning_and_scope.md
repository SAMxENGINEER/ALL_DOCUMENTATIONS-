# Planning and Scope

## Project Vision

The vision for **Creation Ground** is to develop a platform where **anyone** — whether a complete beginner or an experienced practitioner — can create, customize, and export machine learning models with **full control** over the process.

From the outset, the goal was **not merely to simplify ML**, but to **open it up completely**:

* **Lower the barrier to entry** so beginners can start building models quickly without coding expertise.
* **Provide deep customization** for advanced users who want to fine-tune every stage of the workflow.
* **Ensure complete transparency** so the platform serves as both a **learning tool** and a **model development environment**.

By combining accessibility with flexibility, Creation Ground is designed to be both a **gateway for newcomers** and a **sandbox for innovators**.

---

## Objectives

To bring this vision to life, the project focused on the following objectives:

1. **Dataset Handling**

   * Support uploading datasets in common formats (CSV, Excel).
   * Provide quick dataset inspection features — view structure, detect missing values, and check data types.
   * Offer built-in visualization tools for basic exploratory data analysis (EDA).

2. **Preprocessing Tools**

   * Implement essential preprocessing steps: cleaning, encoding, scaling, PCA, and variance-based feature removal.
   * Allow users to control which steps to apply and in what sequence.

3. **Model Training**

   * Support both classification and regression tasks.
   * Provide a library of algorithms sourced from **scikit-learn** and compatible libraries.
   * Include intuitive hyperparameter tuning options for improved performance.

4. **Model Evaluation**

   * Display clear performance metrics: accuracy, precision, recall, F1-score, and RMSE.
   * Include visualizations like confusion matrices, ROC curves, and model comparison charts.
   * Support side-by-side comparisons of multiple models.

5. **Export and Integration**

   * Enable exporting trained models in `.joblib` format.
   * Provide documentation on integrating exported models into external projects.

---

## Scope of the Project

The scope was carefully defined to ensure the project was **feasible within the semester** while delivering a fully functional product.

**In Scope:**

* User interface development using **Streamlit**.
* Modular workflow for dataset upload, preprocessing, model selection, training, and evaluation.
* Multiple algorithm options for classification and regression.
* Export of trained models in `.joblib` format.
* Patent preparation and academic thesis documentation.

**Out of Scope:**

* Hosting or deploying models directly from within the platform.
* Real-time or streaming data processing.
* Advanced deep learning frameworks (TensorFlow, PyTorch) — reserved for future development.

---

## Constraints and Considerations

* **Timeframe:** Development aligned with the **6th semester minor project** schedule.
* **Resources:** Limited to local hardware and free-tier cloud services for testing.
* **Technical Focus:** Emphasis on classical ML algorithms for faster training and easier integration.
* **User Base:** Designed to cater to students, hobbyists, educators, and small startup teams.

---

## Planned Outcomes

By the end of the project, Creation Ground was expected to:

* Deliver a **functional, user-friendly ML workspace**.
* Provide **full visibility** into each step of the ML workflow.
* Serve as both a **tool for building models** and a **platform for learning**.
* Be documented through a **filed patent** and a **technical thesis**.
