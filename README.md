# Predictive Maintenance using XGBoost

## 📌 Project Overview

This project builds a machine learning model to predict machine failures using industrial sensor data.
The goal is to identify potential failures early and reduce downtime in manufacturing systems.

The model is trained on the **AI4I 2020 Predictive Maintenance Dataset** and uses **XGBoost**, a powerful gradient boosting algorithm optimized for tabular data.

---

## ⚙️ Problem Statement

Predict whether a machine will fail based on features such as:

* Air temperature
* Process temperature
* Rotational speed
* Torque
* Tool wear
* Product quality type

This is a **binary classification problem** with **class imbalance**, where failure cases are relatively rare.

---

## 📊 Dataset

* Source: Kaggle – AI4I 2020 Predictive Maintenance Dataset
* Note: Dataset is **not included** in this repository due to licensing restrictions

### 👉 To use the dataset:

1. Download from Kaggle
2. Create a folder named `data/` in the project directory
3. Place the file:

```
data/ai4i2020.csv
```

---

## 🛠️ Data Preprocessing

* Removed leakage-related columns: `UDI`, `Product ID`
* Dropped failure subtype columns: `TWF`, `HDF`, `PWF`, `OSF`, `RNF`
* Encoded categorical variable (`Type`) using one-hot encoding
* Split data into features and target
* Applied **train-test split with stratification**

---

## 🤖 Model

* Algorithm: **XGBoost Classifier**
* Key configurations:

  * `n_estimators = 100`
  * `max_depth = 4`
  * `learning_rate = 0.1`
  * `scale_pos_weight` used to handle class imbalance

---

## ⚖️ Handling Class Imbalance

Failure cases are rare, so:

* Used `scale_pos_weight` to balance classes
* Tuned decision threshold instead of default 0.5

---

## 🎯 Threshold Tuning

Instead of using the default probability threshold (0.5), the model uses:

```
threshold = 0.75
```

This improves recall for failure detection while maintaining reasonable precision.

---

## 📈 Model Performance

### Confusion Matrix

```
[[1900   32]
 [  13   55]]
```

### Classification Report

| Metric    | Class 0 | Class 1 |
| --------- | ------- | ------- |
| Precision | 0.99    | 0.63    |
| Recall    | 0.98    | 0.81    |
| F1-score  | 0.99    | 0.71    |

### Key Insights

* High accuracy: **98%**
* Strong recall for failure detection: **81%**
* Balanced trade-off between precision and recall

---

## 📊 Feature Importance

The model identifies key predictors such as:

* Tool wear
* Rotational speed
* Torque

These features significantly influence machine failure predictions.

---

## 🚀 How to Run

## How to Run

1. Clone the repository:
   git clone https://github.com/DV1999-growth/predictive-maintenance-xgboost.git

2. Navigate to the project:
   cd predictive-maintenance-xgboost

3. Create a folder named `data/` in the project root.

4. Download the dataset from Kaggle and place:
   data/ai4i2020.csv

5. Install dependencies:
   pip install -r requirements.txt

6. Open and run the notebook:
   jupyter notebook

## 📁 Project Structure

```
predictive-maintenance-xgboost/
│
├── Predictive_Maintenance_xgboost.ipynb
├── README.md
├── requirements.txt
└── .gitignore
```

---

## 📌 Key Learnings

* Handling class imbalance in real-world datasets
* Importance of removing data leakage
* Threshold tuning for business-driven decisions
* Using XGBoost for high-performance tabular modeling

---

## 🔗 Author

## Author
DV1999-growth  
GitHub: https://github.com/DV1999-growth
