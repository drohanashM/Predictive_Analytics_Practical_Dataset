# Predictive Analytics – Body Fat Shrinkage Analysis

A practical comparison of regression shrinkage methods using the Body Fat dataset.

---

## Overview

This project demonstrates and compares four regression techniques — **OLS**, **Ridge**, **LASSO**, and **Elastic Net** — on a real-world body measurements dataset to predict body fat percentage. It is structured as a step-by-step Jupyter Notebook with supporting presentation slides and a PDF report.

---

## Repository Contents

| File | Description |
|---|---|
| `bodyfat.csv` | Dataset with 252 observations and 15 body measurement variables |
| `bodyfat_shrinkage_analysis.ipynb` | Main Jupyter Notebook with full analysis |
| `Bodyfat Analysis.pptx` | Presentation slides summarising the findings |
| `Bodyfat Analysis.pdf` | PDF version of the analysis report |

---

## Dataset

**Source:** `bodyfat.csv`  
**Observations:** 252  
**Response Variable:** `BodyFat` (%)  
**Predictors (13):** Age, Weight, Height, Neck, Chest, Abdomen, Hip, Thigh, Knee, Ankle, Biceps, Forearm, Wrist

> `Density` is excluded from modelling as it has a direct mathematical relationship with BodyFat.

---

## Methods Compared

| Model | Description |
|---|---|
| OLS | Ordinary Least Squares — baseline linear regression |
| Ridge | L2 regularisation — shrinks all coefficients, retains all predictors |
| LASSO | L1 regularisation — shrinks some coefficients to exactly zero (variable selection) |
| Elastic Net | Combines L1 + L2 — balances sparsity and grouping of correlated predictors |

All shrinkage methods use **10-fold cross-validation** to select the optimal regularisation parameter (lambda).

---

## Results

| Model | Test MSE | Predictors Used |
|---|---|---|
| OLS | 21.50 | 13 |
| Ridge | 20.98 | 13 |
| LASSO | 20.37 | 4 |
| Elastic Net | **20.28** | 4 |

**Key finding:** Elastic Net achieves the best test accuracy. LASSO and Elastic Net both identify **Age, Abdomen, Forearm, and Wrist** as the most important predictors. Abdomen circumference is the single strongest predictor of body fat, consistent with medical knowledge.

---
