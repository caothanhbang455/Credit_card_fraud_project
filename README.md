# Credit card fraud detection

This project presents a machine learning approach to detect fraudulent credit card transactions using the dataset available on [Kaggle - Credit Card Fraud Detection](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud).

## Author

- Name: Cao Thanh Bằng  
- Notebook: `myanswer.ipynb`

## Objective

The goal of this project is to develop a reliable model to identify fraudulent credit card transactions from highly imbalanced data. Emphasis is placed on preprocessing, appropriate evaluation metrics, and addressing the class imbalance problem.

## Dataset overview

- Source: [Kaggle - Credit Card Fraud Detection](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)
- Records: 284,807 transactions
- Fraudulent cases: 492 (approx. 0.172%)
- Features:
  - `Time`: Time in seconds elapsed between each transaction and the first transaction
  - `Amount`: Transaction amount
  - `V1` to `V28`: Principal components obtained via PCA
  - `Class`: Target variable (0 = legitimate, 1 = fraud)

## Project steps

### 1. Import libraries

Standard libraries were used for data processing (`pandas`, `numpy`), visualization (`matplotlib`, `seaborn`), and modeling (`scikit-learn`).

### 2. Data exploration

- Verified data types and checked for null values
- Analyzed class imbalance
- Conducted descriptive analysis of `Amount` and `Time`

### 3. Data preprocessing

- Applied `StandardScaler` to normalize `Amount` and `Time`
- Identified and optionally handled outliers
- Features `V1` to `V28` were already transformed using PCA

### 4. Handling class imbalance
- Applied over-sampling techniques such as SMOTE

### 5. Model training

- Trained multiple classifiers including:
  - Logistic regression with no handle imablanced
  - Logistic regression with handle imablanced using SMOTE
- Evaluation focused on:
  - Precision
  - Recall
  - F1-score

### 6. Model evaluation

- Used confusion matrix for performance analysis
- Emphasized minimizing false negatives and improving recall for the minority class

## evaluation results

| Class | Precision | Recall | F1-score | Support |
|-------|-----------|--------|----------|---------|
| 0     | 0.92      | 0.97   | 0.95     | 70,599  |
| 1     | 0.97      | 0.92   | 0.95     | 71,028  |

- **Accuracy:** 0.95  
- **Macro average:** Precision = 0.95, Recall = 0.95, F1-score = 0.95  
- **Weighted average:** Precision = 0.95, Recall = 0.95, F1-score = 0.95  
- **Total samples:** 141,627


