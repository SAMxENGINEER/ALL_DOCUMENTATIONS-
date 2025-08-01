# 03 - Results

## Overview

This section highlights the final outcomes from the training and evaluation of the brain tumor classification system. We provide a detailed analysis of model performance using various statistical and visual methods to validate the model's effectiveness.

---

## Evaluation Metrics

The model was tested on unseen data to validate its generalization capability. Below are the key evaluation results:

* **Test Accuracy:** 96.64%
* **Model Size:** \~39.5 MB
* **Classification Type:** Multiclass (4 classes)

### Detailed Classification Report:

| Class       | Precision | Recall | F1-Score | Support |
| ----------- | --------- | ------ | -------- | ------- |
| Glioma      | 0.97      | 0.94   | 0.96     | 300     |
| Meningioma  | 0.94      | 0.92   | 0.93     | 306     |
| No Tumor    | 0.97      | 1.00   | 0.99     | 405     |
| Pituitary   | 0.97      | 1.00   | 0.99     | 300     |
| **Overall** | **0.97**  | -      | -        | 1311    |

---

## Confusion Matrix

```
[[282  17   0   1]
 [  8 280  11   7]
 [  0   0 405   0]
 [  0   0   0 300]]
```

This matrix shows strong performance, particularly for "No Tumor" and "Pituitary" categories, with very few misclassifications.

---

## Visualizations

We plotted accuracy and loss over the 45 training epochs:

* **Training Accuracy** gradually improved and stabilized above 99%.
* **Validation Accuracy** remained consistently between 96–98%.
* **Training & Validation Loss** showed convergence, indicating minimal overfitting.

---

## Interpretation

* **Glioma and Meningioma** show slightly lower recall compared to others but still maintain strong F1-scores.
* **No Tumor and Pituitary** are almost perfectly classified.
* **The model exhibits balance and high performance** across all tumor classes.

---

## Final Thoughts

The results affirm the model's suitability for real-world deployment in clinical environments. With high classification accuracy and compact size, it can serve as a fast and accurate screening tool for radiologists.

In the next section, we will detail the system architecture and real-time inference pipeline.
