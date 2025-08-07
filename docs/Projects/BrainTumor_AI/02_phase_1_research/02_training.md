# 02 - Training and Testing

## Overview

This section outlines the complete training and evaluation process for the brain tumor classification model. We trained a lightweight and robust CNN on MRI images categorized into four classes: **Glioma**, **Meningioma**, **Pituitary**, and **No Tumor**. The pipeline includes dataset preparation, model training, validation, and testing with quantitative metrics.

---

## Dataset Preparation

Images were organized in a directory format and loaded using TensorFlow's `image_dataset_from_directory()` API with the following configuration:

```python
image_dataset_from_directory(
    directory="/content/Training",
    labels='inferred',
    label_mode='int',
    batch_size=32,
    color_mode='rgb',
    image_size=(256, 256)
)
```

To normalize the pixel values, a preprocessing function was applied:

```python
def normal(image, label):
    image = tensorflow.cast(image / 256.0, tensorflow.float32)
    return image, label
```

We split the dataset as follows:

* **Training Set**: 90%
* **Validation Set**: 10%

---

## Model Training

| Configuration  | Value                           |
| -------------- | ------------------------------- |
| Framework      | TensorFlow / Keras              |
| Epochs         | 45                              |
| Batch Size     | 32                              |
| Optimizer      | Adam                            |
| Loss Function  | Sparse Categorical Crossentropy |
| Image Size     | 256 × 256                       |
| Input Channels | RGB (3 channels)                |

The model was trained on the normalized training set using `model.fit()`:

```python
model.fit(
    normalized_train_data,
    epochs=45,
    validation_data=normalized_val_data,
    verbose=1
)
```

---

## Model Performance

After training, the model was evaluated on the test set. Key performance metrics:

| Metric            | Value  |
| ----------------- | ------ |
| **Test Accuracy** | 96.64% |

### Classification Report

| Class                | Precision | Recall | F1-Score | Support |
| -------------------- | --------- | ------ | -------- | ------- |
| Glioma               | 0.97      | 0.94   | 0.96     | 300     |
| Meningioma           | 0.94      | 0.92   | 0.93     | 306     |
| No Tumor             | 0.97      | 1.00   | 0.99     | 405     |
| Pituitary            | 0.97      | 1.00   | 0.99     | 300     |
| **Overall Accuracy** | **0.97**  | -      | -        | 1311    |

### Confusion Matrix

```txt
[[282  17   0   1]
 [  8 280  11   7]
 [  0   0 405   0]
 [  0   0   0 300]]
```

The confusion matrix shows excellent performance, especially for "No Tumor" and "Pituitary" cases.

---

## Training Curves

The model’s learning was monitored via accuracy and loss plots. Over 45 epochs:

* **Training Accuracy** rose steadily, nearing 99%.
* **Validation Accuracy** remained stable between 96%–98%.
* **Loss Curves** indicated low overfitting due to regularization and dropout layers.

---

## Summary

* The model demonstrated **high classification performance** across all tumor types.
* Minimal overfitting was achieved through normalization and data augmentation.
* The CNN's compact size (\~39.5 MB) makes it ideal for deployment in real-time clinical settings.

In the next section, we will present the evaluation and inference strategy used during real-world application testing.
