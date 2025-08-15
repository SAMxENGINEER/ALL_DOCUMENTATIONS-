# Model Building**

## **Introduction**

For lung cancer classification, multiple **machine learning algorithms** from the **Scikit-Learn** library were implemented.
Each model was chosen for its unique strengths, interpretability, and ability to capture different patterns in the dataset.
The primary objective was to compare these algorithms and determine the most effective one for our problem.

---

## **8.1 Logistic Regression**

**Description:**
A linear model that estimates the probability of a sample belonging to each class using the logistic (sigmoid) function.
For multi-class classification, we used the **multinomial** option.

**Configuration:**

* Solver: `lbfgs`
* Max Iterations: `1000`
* Multi-class Mode: `multinomial`
* Random State: Not required (deterministic solver)

**Strengths:**

* Fast training and prediction
* Works well when classes are linearly separable

**Limitations:**

* Struggles with complex, non-linear boundaries

---

## **8.2 Decision Tree Classifier**

**Description:**
A tree-based model that recursively splits the dataset based on feature values to maximize class purity.

**Configuration:**

* Criterion: `gini` (default)
* Random State: `42` (for reproducibility)

**Strengths:**

* Easy to interpret
* Handles both numerical and categorical features

**Limitations:**

* Prone to **overfitting** on small datasets

---

## **8.3 Random Forest Classifier**

**Description:**
An ensemble method that combines multiple decision trees, each trained on random subsets of the data and features.

**Configuration:**

* Number of Trees (`n_estimators`): `100`
* Random State: `42`

**Strengths:**

* Reduces overfitting compared to single Decision Trees
* Handles high-dimensional data well

**Limitations:**

* Less interpretable compared to a single Decision Tree

---

## **8.4 K-Nearest Neighbors (KNN) Classifier**

**Description:**
A non-parametric algorithm that assigns a class to a sample based on the majority vote of its nearest neighbors.

**Configuration:**

* Number of Neighbors (`n_neighbors`): `3`
* Distance Metric: Euclidean (default)

**Strengths:**

* Captures non-linear relationships
* No training phase (lazy learner)

**Limitations:**

* Slow prediction on large datasets
* Sensitive to irrelevant features

---

## **8.5 Gaussian Naïve Bayes**

**Description:**
A probabilistic classifier based on Bayes’ Theorem, assuming conditional independence between features.
The Gaussian variant assumes features follow a normal distribution.

**Configuration:**

* Default parameters from Scikit-Learn

**Strengths:**

* Extremely fast training and prediction
* Performs well on small datasets

**Limitations:**

* Independence assumption rarely holds perfectly

---

## **8.6 Summary Table**

| Model               | Type           | Handles Non-linear Patterns | Probabilistic Output | Prone to Overfitting | Main Strength       |
| ------------------- | -------------- | --------------------------- | -------------------- | -------------------- | ------------------- |
| Logistic Regression | Linear Model   | No                          | Yes                  | Low                  | Simplicity & speed  |
| Decision Tree       | Tree-based     | Yes                         | No                   | High                 | Interpretability    |
| Random Forest       | Ensemble       | Yes                         | No                   | Low                  | Robustness          |
| KNN                 | Instance-based | Yes                         | No                   | Low                  | Flexibility         |
| Gaussian NB         | Probabilistic  | Limited                     | Yes                  | Low                  | Speed on small data |

---

## **Conclusion**

By testing multiple algorithms—ranging from **linear models** to **ensemble methods**—we ensured a comprehensive evaluation of model performance.
This approach allowed us to:

1. Identify the strengths and weaknesses of each model
2. Compare their performance on the same dataset
3. Select the most effective model for our classification task