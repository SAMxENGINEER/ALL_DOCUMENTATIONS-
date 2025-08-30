# Tech Stack

The development of **ImgTechAI** leverages a combination of lightweight, powerful, and widely adopted tools to ensure accessibility, performance, and maintainability.

---

### 🌐 Framework

* **[Streamlit](https://streamlit.io/)**
  A fast, Python-based web application framework used to create interactive UIs with minimal boilerplate. Streamlit powers the entire front-end of ImgTechAI, enabling real-time parameter adjustments and side-by-side image comparisons.

### Computer Vision & Image Processing

* **[OpenCV (cv2)](https://opencv.org/)**
  Core computer vision library used for transformations like filtering, edge detection, segmentation, geometric operations, and histogram adjustments.

* **[scikit-image](https://scikit-image.org/)**
  Supplementary library offering additional image processing methods (e.g., noise injection).

* **[Pillow (PIL)](https://python-pillow.org/)**
  Used for image I/O, format handling, and in-memory operations.

### Numerical Computing

* **[NumPy](https://numpy.org/)**
  Provides array operations and mathematical foundations for processing, filtering, and Fourier analysis.

### Development Environment

* **Python 3.11** – Base language for the project.
* **pip** – Package manager for dependency installation.
* **Virtual Environment (venv/conda)** – Recommended for isolated development.

### Project Assets

* **static/IMAGE\_TECH\_AI.png** – Official project logo (to be used in documentation headers).
* **static/IMAGE\_TECH\_AI\_favicon.png** – Favicon for browser tab representation.

---

## Why This Stack?

The chosen stack emphasizes:

* **Ease of Deployment** – Streamlit enables instant cloud hosting and local execution.
* **Performance** – OpenCV and NumPy deliver efficient matrix operations.
* **Simplicity** – Minimal configuration, suitable for beginners and advanced users alike.
* **Extensibility** – Additional libraries (e.g., TensorFlow, PyTorch) can be integrated in the future for deep learning–based enhancements.
