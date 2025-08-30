# Transformation Reference

This document provides a detailed catalog of the transformations available in **ImgTechAI**, including their parameters, expected input, and resulting output.

---

### 🧠 Segmentation & Edge Detection

* **Binary Thresholding**

  * *Parameters*: Threshold (0–255)
  * *Output*: Binary segmented image

* **Adaptive Thresholding**

  * *Parameters*: Block size (odd integer), Constant C
  * *Output*: Localized thresholded image

* **Otsu Thresholding**

  * *Parameters*: None (automatic)
  * *Output*: Optimally thresholded binary image

* **Watershed Segmentation**

  * *Parameters*: Distance transform threshold
  * *Output*: Objects separated with red boundary lines

* **K-Means Clustering**

  * *Parameters*: Number of clusters (k), Max iterations
  * *Output*: Clustered image with k colors

* **Canny Edge Detection**

  * *Parameters*: Low threshold, High threshold
  * *Output*: Edge map

* **Sobel Edge Detection**

  * *Parameters*: None (kernel size fixed)
  * *Output*: Gradient-based edge map

---

### 🌀 Fourier Transform & Frequency Analysis

* **2D FFT**

  * *Parameters*: None
  * *Output*: Frequency domain representation

* **Magnitude Spectrum**

  * *Parameters*: None
  * *Output*: Visualized frequency magnitude

* **Phase Spectrum**

  * *Parameters*: None
  * *Output*: Visualized frequency phase

* **Filtered Image**

  * *Parameters*: Filter type (Low-pass, High-pass, Band-pass), Cutoff values
  * *Output*: Image reconstructed after frequency filtering

---

### 🔍 Filtering & Smoothing

* **Gaussian Blur**

  * *Parameters*: Kernel size, Sigma
  * *Output*: Smoothed image

* **Sharpen**

  * *Parameters*: Strength factor
  * *Output*: Enhanced image with stronger edges

* **Median Filter**

  * *Parameters*: Kernel size
  * *Output*: Noise-reduced image (effective for salt-and-pepper noise)

---

### 🎨 Color & Pixel Transformations

* **Grayscale Conversion**

  * *Parameters*: None
  * *Output*: Monochrome image

* **Color Jitter**

  * *Parameters*: Brightness factor, Contrast offset
  * *Output*: Brightness and contrast adjusted image

* **Channel Shuffle**

  * *Parameters*: Channel order (RGB, RBG, GRB, etc., or Random)
  * *Output*: Image with rearranged color channels

* **Hue Shift**

  * *Parameters*: Hue angle (-180° to +180°)
  * *Output*: Hue-shifted image

* **Saturation Adjustment**

  * *Parameters*: Factor (0.0 – 3.0)
  * *Output*: Adjusted color vibrancy

---

### 🧪 Noise Injection

* **Gaussian Noise**

  * *Parameters*: Standard deviation (σ)
  * *Output*: Image with normally distributed noise

* **Salt & Pepper Noise**

  * *Parameters*: Amount (0.01 – 0.3)
  * *Output*: Image with random black and white pixels

* **Uniform Noise**

  * *Parameters*: Range (low, high)
  * *Output*: Image with uniformly distributed noise

---

### 🌈 Histogram & Contrast Enhancements

* **Histogram Equalization**

  * *Parameters*: None
  * *Output*: Improved global contrast

* **Gamma Correction**

  * *Parameters*: Gamma value (0.1 – 3.0)
  * *Output*: Non-linear brightness adjustment

* **CLAHE**

  * *Parameters*: Clip limit, Tile grid size
  * *Output*: Adaptive local contrast enhancement

* **Logarithmic Transform**

  * *Parameters*: Constant factor (c)
  * *Output*: Enhanced details in darker regions

---

### 🔄 Geometric Transformations

* **Rotation**

  * *Parameters*: Angle (-180° to +180°)
  * *Output*: Rotated image

* **Scaling**

  * *Parameters*: Scale factor (0.1 – 3.0)
  * *Output*: Resized image with cropping/padding

* **Shear Transform**

  * *Parameters*: Shear factor (-1.0 – 1.0)
  * *Output*: Sheared image

---

### 📦 Image Augmentations

* **Cutout (Random Erasing)**

  * *Parameters*: Cutout size, Number of cutouts
  * *Output*: Image with masked rectangular patches

* **Mixup Effect**

  * *Parameters*: Alpha value (0.1 – 1.0)
  * *Output*: Image blended with random patterns

---

## Notes

* All transformations are applied in a predefined pipeline order for consistency (see **[Architecture](05_architecture.md)**).
* Outputs are always exported in **PNG** format for lossless quality.
* Multiple transformations can be combined in one session, and the applied sequence is summarized at the end of processing.
