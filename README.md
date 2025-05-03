# 📚 Merge Conflict Predictor

![Python](https://img.shields.io/badge/Python-3.12-blue)
![Jupyter](https://img.shields.io/badge/Notebook-Jupyter-orange)

This project uses various machine learning models to predict merge conflicts in version control systems (like Git) based on commit and pull request metadata.

👉 Notebook: [`MihocAlexandru.ipynb`](https://github.com/Alex7734/merge-conflict-predictor/blob/master/MihocAlexandru.ipynb)

---

## 📈 Project Overview

* Load and clean a **real-world merge conflict dataset**.
* **Feature engineer** new ratios based on developer activities.
* **Feature selection** using:

  * Correlation analysis
  * Random Forest importance
* Train and evaluate four models:

  * **Decision Tree**
  * **Random Forest**
  * **Naive Bayes**
  * **XGBoost**
* Use **GridSearchCV** to optimize hyperparameters where applicable.
* Save best models to **pickle** files.
* Measure performance using:

  * **Confusion Matrix**
  * **Classification Report**
  * **Precision-Recall Curve (PRC) and PR-AUC**

---

## 🛠 Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/Alex7734/merge-conflict-predictor.git
cd merge-conflict-predictor
```

### 2. Create and Activate Environment (optional but recommended)

```bash
conda create -n merge-predictor python=3.12
conda activate merge-predictor
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Launch JupyterLab

```bash
jupyter lab
```

Open `MihocAlexandru.ipynb` and run all cells!

---

## 📊 Model Summary

| Model         | F1 Score (orig → ext) | PR-AUC (orig → ext) | Notes                                                                      |
| ------------- | --------------------- | ------------------- | -------------------------------------------------------------------------- |
| Decision Tree | 0.683 → 0.711         | 0.7245 → 0.659      | Engineered features improved recall (F1 ↑) but added noise for ranking     |
| Random Forest | 0.722 → 0.723         | 0.7678 → 0.773      | Strong ensemble effect; small lift in ranking with new features            |
| Naive Bayes   | 0.414 → 0.373         | 0.4336 → 0.352      | Independence assumption limits benefit from correlated engineered features |
| XGBoost       | 0.685 → 0.680         | 0.7883 → 0.7811     | Already high-performance; new features add minimal signal                  |

✅ Adding features like `commit_ratio`, `added_deleted_ratio`, and `commit_message_range` helped some models—but reached a performance ceiling on this dataset!
