# credit-card-fraud-detection
# Credit Card Fraud Detection – Banking Project

## Project Overview
This project aims to build a complete data pipeline for credit card fraud detection,
covering data collection, data cleaning, data processing and exploratory analysis
using Python.

The project is designed from a banking and risk management perspective, with a strong
focus on class imbalance and fraud-specific evaluation metrics.

---

## Business Context
Financial institutions must detect fraudulent transactions while minimizing:
- False negatives (missed frauds leading to financial losses)
- False positives (unnecessary transaction blocks and customer friction)

This project addresses these challenges using real-world transaction data.

---

## Dataset
- Source: Public dataset (Credit Card Fraud Detection – Kaggle)
- Type: Credit card transactions
- Target variable:
  - `Class = 1`: Fraudulent transaction
  - `Class = 0`: Legitimate transaction
- Strong class imbalance (~0.17% fraud)

⚠️ The raw dataset is not included in this repository.  
Expected file path:


---

## Data Pipeline

### 1. Data Collection
- Loading raw transaction data from CSV using Pandas
- Initial structure and integrity checks

### 2. Data Cleaning
- Duplicate detection and removal
- Verification of missing values
- Data type validation

### 3. Data Processing
- Feature engineering (transaction hour from timestamp)
- Feature scaling (Amount and Time normalization)
- Train/Test split with stratification to preserve fraud ratio

---

## Exploratory Data Analysis
- Analysis of class imbalance
- Distribution of transaction amounts
- Temporal fraud patterns
- Fraud rate evaluation

---

## Tech Stack
- Python
- Pandas / NumPy
- Scikit-learn
- Matplotlib / Seaborn
- Jupyter Notebook

---

## Project Structure
