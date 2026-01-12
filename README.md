# 🛡️ ML-Based Intrusion Detection System (CIC-IDS2017)

![Python](https://img.shields.io/badge/Python-3.8%2B-blue) ![Sklearn](https://img.shields.io/badge/Library-Scikit_Learn-orange) ![Status](https://img.shields.io/badge/Status-Prototype-green)

## 📖 Overview

This project implements a Network Intrusion Detection System (NIDS) using the **CIC-IDS2017 dataset**. The system is designed to classify network traffic as **Benign** or specific attack types (e.g., **DDoS, Port Scan, Brute Force**) using Machine Learning.

The pipeline includes extensive data preprocessing, memory optimization, dimensionality reduction using **Incremental PCA**, and class balancing using **SMOTE**, culminating in a **Random Forest** classification model.

## 📂 Dataset

The project utilizes the **CIC-IDS2017** dataset developed by the Canadian Institute for Cybersecurity.
**Required Files:**
* `Friday-WorkingHours-Afternoon-DDos.pcap_ISCX.csv`
* `Tuesday-WorkingHours.pcap_ISCX.csv`
* `Wednesday-workingHours.pcap_ISCX.csv`
* `Thursday-WorkingHours-Morning-WebAttacks.pcap_ISCX.csv`
* `Thursday-WorkingHours-Afternoon-Infilteration.pcap_ISCX.csv`
* `Friday-WorkingHours-Morning.pcap_ISCX.csv`
* `Friday-WorkingHours-Afternoon-PortScan.pcap_ISCX.csv`

> **Note:** These files must be placed in the root directory (or update the paths in the script) before running.

## ⚙️ Technical Pipeline

### 1. Data Cleaning & Optimization
* **Concatenation:** Merges 8 separate daily traffic logs into a single dataframe.
* **Sanitization:** Strips whitespace from columns, removes duplicates, and handles `Infinity`/`NaN` values using median imputation.
* **Memory Optimization:** Downcasts `float64` to `float32` and `int64` to `int32` to significantly reduce RAM usage during processing.

### 2. Feature Engineering
* **Label Mapping:** Groups granular labels into broader categories (e.g., `DoS Hulk`, `DoS GoldenEye` → `DoS`).
* **Correlation Analysis:** Identifies features highly correlated with the target variable.
* **Outlier Detection:** Uses the Interquartile Range (IQR) method to analyze feature distribution.
* **Standardization:** Scales features using `StandardScaler`.

### 3. Dimensionality Reduction
* **Incremental PCA:** Reduces the feature space by 50% (retaining principal components) to improve training speed without overwhelming memory.

### 4. Class Balancing
* **Undersampling:** Reduces the overwhelming "Benign" class.
* **SMOTE (Synthetic Minority Over-sampling Technique):** Upsamples minority attack classes to ensure the model isn't biased toward majority classes.

### 5. Modeling
* **Algorithms:**
    * **Decision Tree:** Used for initial cross-validation and baseline testing (Max Depth 6 & 8).
    * **Random Forest:** The final deployed model (100 estimators).
* **Evaluation:** Outputs Confusion Matrix and Classification Report (Precision, Recall, F1-Score).

## 🛠️ Installation & Usage

### Prerequisites
Install the required Python libraries:
```bash
pip install pandas numpy seaborn matplotlib scikit-learn imbalanced-learn
