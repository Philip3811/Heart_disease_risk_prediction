# Heart Disease Risk Prediction (R): Logistic Regression, LDA, and QDA

[![Language: R](https://img.shields.io/badge/language-R-blue.svg)](#)
[![Status: Complete](https://img.shields.io/badge/status-complete-brightgreen.svg)](#)
[![License: MIT](https://img.shields.io/badge/license-MIT-lightgrey.svg)](#)

Predicting the risk of heart disease using classical statistical learning methods in R.  
This project covers end‑to‑end preprocessing (EDA, transformations, encoding), model development (Logistic Regression, LDA, QDA), and evaluation using cross://wmich-my.sharepoint.com/personal/pzp8712_wmich_edu/Documents/Microsoft%20Copilot%20Chat%20Files/STAT_5850_FINAL_PROJECT%20_REPORT.pdf)

---

## 📌 Overview

Heart disease remains a leading global cause of mortality. Accurate, interpretable models can support early intervention and clinical decision‑making. This project develops and evaluates **Logistic Regression**, **Linear Discriminant Analysis (LDA)**, and **Quadratic Discriminant Analysis (QDA)** on a structured clinical dataset with ~13 predictors (mix of continuous and categorical). The workflow includes data quality checks, Box‑Cox transformations for skewed features, one‑hot encoding where appropriate, model training with cross‑validation, and comprehensive evaluation on a held‑out test set. [1](https://wmich-my.sharepoint.com/personal/pzp8712_wmich_edu/Documents/Microsoft%20Copilot%20Chat%20Files/STAT_5850_FINAL_PROJECT%20_REPORT.pdf)

---

## 📂 Repository Structure
> The report (PDF) summarizes methodology, experiments, and results and informs this README. [1](https://wmich-my.sharepoint.com/personal/pzp8712_wmich_edu/Documents/Microsoft%20Copilot%20Chat%20Files/STAT_5850_FINAL_PROJECT%20_REPORT.pdf)

---

## 🧠 Problem Statement

**Goal:** Classify whether a patient is at risk of heart disease based on clinical and physiological variables.  
**Key Questions:**
- Which predictors are most informative for heart disease risk?
- How accurately can classical statistical models classify risk on unseen data?
- Do additional demographic features improve performance? [1](https://wmich-my.sharepoint.com/personal/pzp8712_wmich_edu/Documents/Microsoft%20Copilot%20Chat%20Files/STAT_5850_FINAL_PROJECT%20_REPORT.pdf)

---

## 🗃️ Data

- **Features:** ~13 predictors (5 categorical, 8 continuous).  
- **Target:** Presence/absence of heart disease.  
- **Notes:**  
  - Categorical variables converted to factors; selected variables one‑hot encoded to avoid imposing artificial order.  
  - Outlier handling via capping/removal after EDA; class imbalance explored via undersampling where necessary.  
  - Box‑Cox transformations applied to skewed continuous variables to better meet model assumptions. [1](https://wmich-my.sharepoint.com/personal/pzp8712_wmich_edu/Documents/Microsoft%20Copilot%20Chat%20Files/STAT_5850_FINAL_PROJECT%20_REPORT.pdf)

> **Dataset access:** If the dataset is license‑restricted, place files under `data/raw/` (excluded via `.gitignore`) and update paths in `01_load_clean_data.R`. Otherwise, include a link to the public source here (e.g., UCI/Kaggle) and instructions to download. [1](https://wmich-my.sharepoint.com/personal/pzp8712_wmich_edu/Documents/Microsoft%20Copilot%20Chat%20Files/STAT_5850_FINAL_PROJECT%20_REPORT.pdf)

---

## 🔎 Methods

1. **Exploratory Data Analysis (EDA)**  
   - Univariate: Histograms (continuous), bar charts (categorical).  
   - Bivariate: Box plots; chi‑square tests for categorical associations. [1](https://wmich-my.sharepoint.com/personal/pzp8712_wmich_edu/Documents/Microsoft%20Copilot%20Chat%20Files/STAT_5850_FINAL_PROJECT%20_REPORT.pdf)

2. **Preprocessing**  
   - Missing value checks and cleaning.  
   - Factor encoding for categoricals; one‑hot encoding where appropriate.  
   - Outlier treatment (capping/removal).  
   - **Box‑Cox** transformation of skewed features.  
   - Train/test split strategy. [1](https://wmich-my.sharepoint.com/personal/pzp8712_wmich_edu/Documents/Microsoft%20Copilot%20Chat%20Files/STAT_5850_FINAL_PROJECT%20_REPORT.pdf)

3. **Models**  
   - **Logistic Regression** (baseline, interpretable coefficients).  
   - **LDA** and **QDA** (generative classifiers; LDA assumes shared covariance, QDA class‑specific).  
   - **5‑fold cross‑validation** to estimate generalization error. [1](https://wmich-my.sharepoint.com/personal/pzp8712_wmich_edu/Documents/Microsoft%20Copilot%20Chat%20Files/STAT_5850_FINAL_PROJECT%20_REPORT.pdf)

4. **Evaluation**  
   - Confusion matrices on train/test.  
   - Accuracy, Sensitivity (Recall for positive class), Specificity.  
   - Comparison across models and discussion of trade‑offs (accuracy vs. sensitivity). [1](https://wmich-my.sharepoint.com/personal/pzp8712_wmich_edu/Documents/Microsoft%20Copilot%20Chat%20Files/STAT_5850_FINAL_PROJECT%20_REPORT.pdf)

---

## 📈 Results

**Logistic Regression (Test Set)**
- **Accuracy:** 87.5%  
- **Sensitivity:** 87.3%  
- **Specificity:** 87.8%  
- Comparable train/test metrics indicate good generalization with limited overfitting. [1](https://wmich-my.sharepoint.com/personal/pzp8712_wmich_edu/Documents/Microsoft%20Copilot%20Chat%20Files/STAT_5850_FINAL_PROJECT%20_REPORT.pdf)

**LDA vs. QDA (with 5‑fold CV)**
- **LDA:** Accuracy ≈ 83.33%, **Sensitivity ≈ 88.24%** (better at identifying true disease cases).  
- **QDA:** Accuracy ≈ 83.85%, Sensitivity ≈ 84.31% (slightly higher overall accuracy).  
- In medical contexts, higher sensitivity can be preferable, favoring LDA in this dataset. [1](https://wmich-my.sharepoint.com/personal/pzp8712_wmich_edu/Documents/Microsoft%20Copilot%20Chat%20Files/STAT_5850_FINAL_PROJECT%20_REPORT.pdf)

> See `plots/model_results/` and the PDF report for confusion matrices, coefficient summaries, and feature importance commentary. [1](https://wmich-my.sharepoint.com/personal/pzp8712_wmich_edu/Documents/Microsoft%20Copilot%20Chat%20Files/STAT_5850_FINAL_PROJECT%20_REPORT.pdf)

---

## 🚀 How to Run

### 1) Prerequisites
- **R (≥ 4.x)** and Rscript
- Recommended R packages:
  ```r
  install.packages(c("tidyverse", "MASS", "caret", "ggplot2", "reshape2"))
