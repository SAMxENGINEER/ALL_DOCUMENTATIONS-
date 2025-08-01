# Brain Tumor Detection System

An end-to-end deep learning application for brain MRI validation, tumor classification, and tumor region segmentation — developed in two structured phases: research and deployment.

---

## Overview

The Brain Tumor Detection System is a deep learning–based medical imaging tool designed to assist in the preliminary diagnosis of brain tumors using MRI scans. It performs three key tasks:

* Validates whether the uploaded image is a brain MRI.
* Classifies the image into one of four categories: Glioma, Meningioma, Pituitary, or No Tumor.
* Segments and highlights the tumor region if present.
* Generates a downloadable diagnostic report summarizing predictions and overlays.

Initially developed as a research prototype for a technical writing competition, the project later evolved into a production-ready web application with robust architecture, improved models, and user-facing features.

---

## Live Demo

Access the deployed application at the following link:

[Brain Tumor Detection Web App](https://braintumor-ai.streamlit.app/)

---

## Demo Walkthrough

A complete video walkthrough of the system is available here:

[Watch the Video](https://vimeo.com/1106384259?share=copy)

---

## Project Repositories

* 🔗 **Live App Repository** (used for Streamlit Cloud deployment):  
  [https://github.com/SAMxENGINEER/Brain_tumor_seg](https://github.com/SAMxENGINEER/Brain_tumor_seg)

* 🔗 **Main Code Repository** (includes models, training scripts, and full documentation):  
  [https://github.com/SAMxENGINEER/Brain_tumor_full_codebase](https://github.com/SAMxENGINEER/Brain_tumor_full_codebase)

> _Note: If the repositories are private, access must be requested._

---

## Publication

This work has been published in an IEEE conference. You can view the full research paper here:

[Read the IEEE Paper](https://ieeexplore.ieee.org/document/11059181)


---

## Project Phases

### Phase 1 – Research and Publication

* Built and evaluated the initial tumor classification model using TensorFlow and Keras on Google Colab.
* Drafted and submitted a technical research paper, which was later accepted for publication.
* Developed under the guidance of domain experts and academic mentors.

### Phase 2 – Application Development and Deployment

* Introduced an MRI validator model to filter out irrelevant inputs.
* Improved the classification model and added a segmentation pipeline.
* Built a user interface using Streamlit for ease of access.
* Integrated auto-generated test reports with visual overlays.
* Deployed the complete system on Streamlit Cloud.

---

## Key Features

| Feature              | Description                                                    |
| -------------------- | -------------------------------------------------------------- |
| MRI Validation       | Verifies whether the uploaded image is a brain MRI.            |
| Tumor Classification | Identifies tumor presence and type from MRI scans.             |
| Tumor Segmentation   | Highlights tumor regions using color-based overlays.           |
| Report Generation    | Provides downloadable visual and textual summaries of results. |
| Web-Based UI         | No installation needed — accessible via any browser.           |

---

## Tech Stack

| Component        | Technology        |
| ---------------- | ----------------- |
| Frontend UI      | Streamlit         |
| Image Processing | OpenCV, PIL       |
| Deep Learning    | TensorFlow, Keras |
| Visualization    | Matplotlib        |
| Deployment       | Streamlit Cloud   |

---

## Repository Structure

This project is distributed across two Git repositories:

1. **Frontend (Live Web App)** – contains the minimal app code deployed on Streamlit.
2. **Main Repository (Complete Project)** – includes all models, training notebooks, dataset preparation code, and documentation.

Due to deployment constraints and logical separation, we deviated from our standard monorepo structure. This has been clarified across the documentation files.

---

## Documentation Structure

```bash
docs/
├── index.md
├── 00_background/
│   ├── 00_idea_spark.md
│   ├── 01_problem_statement.md
│   ├── 02_phases_overview.md
│   └── 03_planning.md
├── 01_features_and_tech/
│   ├── 01_features.md
│   ├── 02_tech_stack.md
├── 02_phase_1_research/
│   ├── 01_model_development.md
│   ├── 02_training.md
│   ├── 03_results.md
│   └── 04_publication.md
├── 03_phase_2_app/
│   ├── 01_architecture.md
│   ├── 02_models.md
│   ├── 03_segmentation.md
│   ├── 04_validator_model.md
│   ├── 05_streamlit_ui.md
│   ├── 06_deployment.md
│   └── 07_limitations_future.md
├── 04_user_guide/
│   ├── 01_setup.md
│   ├── 02_usage.md
```

---

## Citation

If this work contributes to your academic or industrial research, please cite the original IEEE publication. Details can be found in the [Publication Section](./02_phase_1_research/04_publication.md).

---

## License

📄 Licensed under CC BY-NC 4.0

For full details, see the [LICENSE](LICENSE) file in the main repository.

---

## Acknowledgements

We extend our sincere gratitude to the following individuals and communities for their invaluable support throughout the project:

- **Dr. Anupama Mishra** – For her continuous academic guidance, mentorship, and critical feedback during the research and publication process.
- **Mr. Siddesh** – For his valuable contributions during the brainstorming phase, helping to shape the core idea and direction of the project.
- **Kaggle Community** – For sharing publicly available MRI datasets, which served as a foundation for training and validating our models.


**Documented on: Aug 1, 2025** (both phase 1 and 2)
