A compact, reproducible exploration of Support Vector Machines (SVMs) on both toy and real-world data.  
This repository demonstrates SVM decision boundaries, hyperparameter tuning, kernel comparison, support vector analysis, and model interpretability (SHAP).  

It contains two Jupyter notebooks:

- **`1_toy_make_moons.ipynb`** — visualization and diagnostics on the `make_moons` dataset  
- **`2_breast_cancer.ipynb`** — full SVM workflow on the UCI Breast Cancer dataset

---

## Table of Contents

- [Motivation](#motivation)  
- [What I Built](#what-i-built)  
- [Key Findings (Summary)](#key-findings-summary)  
- [Notebook Details](#notebook-details)  
- [Dependencies](#dependencies)   
- [Suggested Next Steps](#suggested-next-steps)  
- [Summary for Résumé](#summary-for-résumé)  

---

## Motivation

SVMs are classical, robust classifiers useful for structured/tabular datasets and small–medium sized real-world problems.  
This project aims to:

- Visualize how SVM kernels behave  
- Explore the effects of hyperparameters (`C`, `gamma`)  
- Diagnose support vector behavior  
- Apply SVMs to a real clinical dataset  
- Interpret predictions using SHAP  

---

## What I Built

-  Decision boundary visualizations on toy data  
-  SVM pipeline (`StandardScaler` → `SVC`) with cross-validation  
-  GridSearchCV for kernel and hyperparameter tuning  
-  Accuracy vs. `C` and #support vectors analysis   
-  End-to-end SVM classifier on the Breast Cancer dataset  
-  Global model interpretation using SHAP  

---

## Key Findings (Summary)

### **Toy Model (make_moons)**
- RBF kernel performs best during hyperparameter tuning using GridSearchCV.
- Support vectors were plotted along with the decision boundary.

### **Breast Cancer Dataset**
- Standardized pipeline + SVM achieves strong performance.
- Accuracy increases with `C` up to an optimal value, then plateaus or fluctuates slightly.  
- Number of support vectors decreases as `C` increases and eventually stabilizes: 
- Important features (from SHAP):  
  *worst concavity, worst concave points, perimeter error, worst area, worst radius*.  
- High values of these features push SHAP values toward **malignant** (class 0), aligning with clinical intuition.  
- SVM relies on a minimal set of boundary-defining samples for large `C`.  
- SHAP correctly explains predictions relative to class `1` (benign).  

---

## Notebook Details

### **1_toy_make_moons.ipynb**
- Generate and visualize nonlinear toy data  
- Grid search across kernels and hyperparameters  
- Decision boundary plots with support vectors annotated  


### **2_breast_cancer.ipynb**
- Load sklearn Breast Cancer dataset   
- Pipeline + `GridSearchCV`  
- Support vector counts and effect of `C`  
- SHAP summary plot for global interpretability  

---
