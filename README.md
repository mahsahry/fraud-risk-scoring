# Credit Card Fraud Detection with Imbalanced Learning Analysis

## Project Overview
This project investigates credit card fraud detection on a highly imbalanced transaction dataset. The goal is to build a machine learning pipeline that can identify fraudulent transactions while balancing fraud capture and false alarm rate.

The project includes:
- exploratory data analysis
- baseline modeling with Logistic Regression
- model comparison with tree-based methods
- Random Forest tuning
- threshold tuning
- feature importance analysis

## Dataset
The project uses the **Credit Card Fraud Detection** dataset from Kaggle.

Because the dataset is highly imbalanced, standard accuracy is not sufficient for evaluation. Instead, the project focuses on:
- Precision
- Recall
- F1-score
- ROC-AUC
- PR-AUC

## Problem Motivation
Fraud detection is a classic imbalanced classification problem. Fraudulent transactions are rare, which means a model can achieve high accuracy while still performing poorly on the minority class. This project therefore focuses on evaluation methods and decision thresholds that are more meaningful in practice.

## Workflow
1. Exploratory Data Analysis
2. Baseline Logistic Regression
3. Model comparison:
   - Logistic Regression
   - Decision Tree
   - Random Forest
4. Random Forest variant comparison
5. Threshold tuning
6. Feature importance analysis

## Key Results

### Baseline Logistic Regression
- Precision: 0.827
- Recall: 0.633
- F1-score: 0.717
- ROC-AUC: 0.961
- PR-AUC: 0.741

### Best Standard Model: Random Forest
- Precision: 0.941
- Recall: 0.816
- F1-score: 0.874
- ROC-AUC: 0.963
- PR-AUC: 0.873

Confusion Matrix:
- True Negatives: 56859
- False Positives: 5
- False Negatives: 18
- True Positives: 80

### Threshold Tuning
The default threshold of 0.5 was compared with lower thresholds. A threshold of **0.4** provided the best overall tradeoff:

- Precision: 0.933
- Recall: 0.857
- F1-score: 0.894
- False Positives: 6
- False Negatives: 14

This showed that the default threshold was not the optimal operating point for fraud detection.

## Feature Importance
The Random Forest model relied most strongly on a relatively small subset of transformed variables, especially:
- V17
- V14
- V12
- V10
- V16

This suggests that the fraud signal is concentrated in a limited number of anonymized features.

## Repository Structure
```text
.
├── README.md
├── requirements.txt
├── notebooks/
├── images/
├── data/
└── results/
