# 🌍 Classifying Potentially Hazardous Asteroids

This project applies machine learning to classify **potentially hazardous near-Earth objects (NEOs)** using publicly available NASA data.  
The goal is to explore whether physical and orbital characteristics of asteroids can help predict NASA’s *hazardous* label — and to understand the strengths and limitations of such models.

This project was completed as part of an individual take-home assignment in **Machine Learning**.

---

## 🚀 Motivation

I have always been fascinated by space — partly because it is beautiful, partly because it is chaotic, and partly because there are gigantic rocks zooming around the Solar System.

NASA tracks thousands of near-Earth objects, but telescope time and attention are limited.  
This project explores whether machine learning can help **prioritize which asteroids deserve closer inspection**, using a simplified tabular dataset.

Spoiler: machine learning is cool — but planetary defense is *very* hard.

---

## 📊 Dataset

- **Source:** NASA Near-Earth Object (NEO) dataset (via Kaggle)
- **Observations:** ~90,000 asteroids
- **Target variable:** `hazardous` (binary)
- **Features used include:**
  - Estimated diameter
  - Relative velocity
  - Miss distance
  - Absolute magnitude (brightness)
  - Sentry flag

> Note: Absolute magnitude uses a **reverse scale** — lower values indicate brighter (and often larger) objects.

---

## 🧠 Models Used

- **Logistic Regression**
  - Baseline linear classifier
  - Feature scaling with `StandardScaler`
  - Hyperparameter tuning via grid search

- **Random Forest Classifier**
  - Nonlinear, tree-based model
  - Hyperparameter tuning for depth, splits, and number of trees
  - Best overall performance on the hazardous class

Evaluation focused on **ROC-AUC, precision, recall, and confusion matrices**, rather than accuracy alone, due to strong class imbalance.

---

## 📈 Key Findings

- The dataset is **highly imbalanced** (≈10% hazardous).
- Logistic Regression achieves high accuracy but **misses most hazardous asteroids**.
- Random Forest significantly improves recall and AUC for hazardous objects.
- **Absolute magnitude (brightness)** is the strongest single predictor.
- The model’s limitations highlight how much more information NASA uses in reality (orbital simulations, uncertainty propagation, repeated observations).

---

## ⚠️ Important Disclaimer

This project does **not** attempt to predict real asteroid impacts.

The models only try to **reproduce NASA’s existing labels** using a small set of features.  
NASA’s real hazard assessment involves complex physics, long-term trajectory simulations, and continuous updates — far beyond the scope of this dataset.

---

## 🛠️ How to Run

1. Clone the repository
2. (Optional) Install dependencies:
   ```bash
   pip install -r requirements.txt
