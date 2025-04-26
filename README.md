

# 📚 Merge Conflict Predictor

![Python](https://img.shields.io/badge/Python-3.12-blue)
![Jupyter](https://img.shields.io/badge/Notebook-Jupyter-orange)


This project uses various machine learning models in order to predict merge conflicts in version control systems (like Git) based on commit and pull request metadata.

👉 Notebook: [`MihocAlexandru.ipynb`](https://github.com/Alex7734/merge-conflict-predictor/blob/master/MihocAlexandru.ipynb)

---

## 📈 Project Overview

- Load and clean a **real-world merge conflict dataset**.
- **Feature engineer** new ratios based on developer activities.
- **Feature selection** using:
  - Correlation analysis
  - Random Forest importance
- Train and evaluate three models:
  - **Decision Tree**
  - **Random Forest**
  - **Naive Bayes**
- Use **GridSearchCV** to optimize hyperparameters.
- Save best models to **pickle** files.
- Measure performance using:
  - **Confusion Matrix**
  - **Classification Report**
  - **Precision-Recall Curve (PRC) and PR-AUC**

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

| Model           | F1 Score | PR-AUC | Notes |
|-----------------|----------|--------|-------|
| Decision Tree   | 0.65 → (after features) 0.65+ | 0.6782+ | Good interpretability, controlled depth |
| Random Forest   | 0.62 → (after features) 0.63+ | 0.7410 | Most robust |
| Naive Bayes     | 0.42 → (after features) 0.45  | 0.4930 | Struggles with complex patterns |

✅ Adding features like `commit ratio` and `added/deleted lines ratio` improved model performance!
