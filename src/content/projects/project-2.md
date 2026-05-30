---
title: '2024 WiDS Datathon: Breast Cancer Treatment Prediction'
description: 'A binary classification model predicting whether metastatic breast cancer patients received timely treatment. this was built for the 2024 Women in Data Science Datathon using real patient records from Health Verity.'
image:
    url: '/images/laptop.webp'
    alt: '2024 WiDS Datathon: Breast Cancer Treatment Prediction'
worksImage1:
    url: '/images/image-1.webp'
    alt: 'Feature importance chart for treatment prediction model'
worksImage2:
    url: '/images/image-2.webp'
    alt: 'Model evaluation — ROC curve and classification report'
platform: Kaggle
stack: 'Python, Pandas, scikit-learn, XGBoost, SHAP, Plotly'
github: https://www.kaggle.com/jacobynetambe/competitions
---

## The Problem

The 2024 WiDS Datathon, organized by Stanford's Women in Data Science initiative, challenged participants to predict whether patients with metastatic breast cancer received timely treatment and specifically, whether a patient received treatment within 90 days of diagnosis.

The dataset came from Health Verity, a real-world evidence platform with de-identified patient records: diagnosis codes, demographics, prior medical history, and treatment records.

Treatment delays in metastatic breast cancer are associated with worse outcomes. Identifying patients at risk of delayed care, and understanding what predicts that delay, is a genuine public health question.

## The Approach

**Data preparation:** The dataset included ICD diagnosis codes, geographic region, age at diagnosis, insurance type, and prior treatment history. Significant feature engineering was required: encoding diagnosis codes meaningfully, creating interaction features between demographic and clinical variables, and handling missing values in a way that preserved the signal rather than masking it.

**Baseline:** Logistic regression because it is interpretable, fast to validate, and useful as a floor to beat. This step also surfaced which features carry linear signal before adding model complexity.

**Champion model:** XGBoost with cross-validated hyperparameter tuning. Tree-based models handle the feature interactions in medical record data better than linear models, and XGBoost's built-in handling of missing values simplified the preprocessing pipeline.

**Interpretability:** SHAP values to expose which features drove individual predictions beyond just global feature importance. In healthcare contexts, knowing *why* a model flags a patient matters as much as whether the flag is accurate.

**Evaluation metric:** AUC (area under the ROC curve), which handles the class imbalance in treatment outcomes without requiring a fixed threshold decision.

## Tech Stack

Python · Pandas · scikit-learn · XGBoost · SHAP · Plotly

## Outcome

A complete end-to-end ML pipeline on real patient-level data: raw records to submission-ready predictions.

This project sits alongside my BofA production work as evidence of a specific pattern applied in a different context: start with the problem, understand the data, build interpretably, validate rigorously.

[View competition on Kaggle →](https://www.kaggle.com/jacobynetambe/competitions)
