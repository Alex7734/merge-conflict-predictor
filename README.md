# 📚 Merge Conflict Predictor

![Python](https://img.shields.io/badge/Python-3.12-blue)
![Jupyter](https://img.shields.io/badge/Notebook-Jupyter-orange)

This project uses various machine learning models in order to predict merge conflicts in version control systems (like Git) based on commit and pull request metadata.

👉 Traditionl Models Notebook (Decision Tree, Random Forest, Naive Bayes): [`MihocAlexandru.ipynb`](https://github.com/Alex7734/merge-conflict-predictor/blob/master/MihocAlexandru.ipynb)  
👉 Deep Learning (Scikit-learn MLP): [`MihocAlexS.ipynb`](https://github.com/Alex7734/merge-conflict-predictor/blob/master/MihocAlexS.ipynb)  
👉 Deep Learning (TensorFlow): [`MihocAlexT.ipynb`](https://github.com/Alex7734/merge-conflict-predictor/blob/master/MihocAlexT.ipynb)

---

## 📈 Project Overview

- Load and clean a **real-world merge conflict dataset**.
- **Feature engineer** new ratios based on developer activities.
- **Feature selection** using:
  - Correlation analysis
  - Random Forest importance
- Train and evaluate five models:
  - **Decision Tree**
  - **Random Forest**
  - **Naive Bayes**
  - **MLPClassifier (Scikit-learn)**
  - **Neural Network (TensorFlow)**
- Use **GridSearchCV** and **EarlyStopping** for optimization.
- Save best models to `.pkl` or `.keras` files.
- Measure performance using:
  - **Confusion Matrix**
  - **Classification Report**
  - **Precision-Recall Curve (PRC) and PR-AUC**

---

## 🧠 Deep Learning Models Summary

| Model                  | Recall (Conflict Class) | Accuracy | Notes |
|------------------------|-------------------------|----------|-------|
| MLPClassifier (Scikit) | 0.86                    | 96%      | Balanced via manual oversampling + grid search |
| TensorFlow NN          | **0.95**                | 95%      | Class weights + early stopping, no oversampling |

✅ Both models were built to **maximize recall** — as required by assignment rules for names A–K.  
✅ TensorFlow significantly outperformed the Scikit-learn MLP in terms of recall.

---

## 🛠 Setup Instructions

### 1. Clone the Repository
```bash
git clone https://github.com/Alex7734/merge-conflict-predictor.git
cd merge-conflict-predictor
````

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

Open any of the notebooks:

* `MihocAlexandru.ipynb` (classic ML)
* `MihocAlexS.ipynb` (Scikit-learn MLP)
* `MihocAlexT.ipynb` (TensorFlow)

---

## 📊 Traditional ML Models Summary

| Model         | F1 Score                      | PR-AUC  | Notes                                   |
| ------------- | ----------------------------- | ------- | --------------------------------------- |
| Decision Tree | 0.65 → (after features) 0.65+ | 0.6782+ | Good interpretability, controlled depth |
| Random Forest | 0.62 → (after features) 0.63+ | 0.7410  | Most robust                             |
| Naive Bayes   | 0.42 → (after features) 0.45  | 0.4930  | Struggles with complex patterns         |

✅ Adding features like `commit ratio` and `added/deleted lines ratio` improved model performance!

