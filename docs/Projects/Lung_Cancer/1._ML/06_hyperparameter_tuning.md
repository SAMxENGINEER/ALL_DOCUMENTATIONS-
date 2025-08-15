# Machine Learning Model Hyperparameter Tuning**

## **10.1 Introduction**

To improve the performance of the **Gaussian Naïve Bayes** model, **Optuna** was used for automated hyperparameter optimization.
The objective was to **maximize model accuracy** while maintaining computational efficiency.

---

## **10.2 Why Optuna?**

**Optuna** is an advanced hyperparameter optimization framework that uses **Bayesian optimization** to efficiently explore the search space.
It offers several advantages over manual tuning or traditional methods such as grid search:

* **Automated Optimization:** No need to manually test parameter combinations.
* **Efficient Search:** Uses Tree-structured Parzen Estimator (TPE) for intelligent exploration.
* **Fast Convergence:** Quickly identifies high-performing configurations.

---

## **10.3 Parameter Tuned**

**Parameter:** `var_smoothing`

* Purpose: Controls the amount of variance smoothing in **Gaussian Naïve Bayes**, preventing division by zero during probability calculations.
* Search Range: `1e-9` → `1e-1`
* Tuning Method: 100 trials using **Optuna**’s TPE sampler.
* Objective Metric: **Accuracy**

---

## **10.4 Optimization Process**

1. **Trial Generation:** Optuna suggested different `var_smoothing` values within the defined range.
2. **Model Training:** Each configuration was trained on the dataset.
3. **Evaluation:** Accuracy was measured for each trial.
4. **Selection:** The best-performing `var_smoothing` value was chosen.

---

## **10.5 Best Result Found**

* **Best `var_smoothing`:** *Value chosen by Optuna*
* **Accuracy:** 57.56%
* **Training Time:** 1.37 seconds

---

## **10.6 Observations**

* Accuracy improvement was **marginal** (from 57.31% → 57.56%).
* Training time remained **extremely low**, preserving the model’s speed advantage.
* Despite tuning, **Naïve Bayes** still performed significantly worse than other models, indicating its **inherent limitations** for this dataset.
* Tuning ensured the model operated at its **optimal settings** for the given data.

---

## **10.7 Conclusion**

While **Optuna hyperparameter tuning** optimized the Gaussian Naïve Bayes model, the accuracy gain was minimal.
This confirms that **model selection** plays a more crucial role than tuning when performance limitations stem from algorithmic assumptions (such as feature independence).
