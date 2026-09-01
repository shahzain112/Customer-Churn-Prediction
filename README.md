
# 🏦 Customer Churn Prediction

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-2.0+-orange.svg)](https://www.tensorflow.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

![Customer Churn Prediction](Customer_Churn_Prediction.png)

## 📌 Overview

Customer churn (or attrition) is a critical metric for businesses, especially in the banking sector. This project aims to **predict whether a bank customer will leave (churn) or stay** based on their demographic and transactional data. By identifying potential churners early, banks can take proactive measures to retain customers and improve satisfaction.

We built a **binary classification model** using a **deep neural network** (TensorFlow/Keras) and performed comprehensive **Exploratory Data Analysis (EDA)** to uncover key drivers of churn.

---

## 📊 Dataset

We used the **Churn_Modelling.csv** dataset, which contains 10,000 customer records with the following features:

| Feature             | Description                                 |
| ------------------- | ------------------------------------------- |
| `CreditScore`     | Customer's credit score                     |
| `Geography`       | Country (France, Spain, Germany)            |
| `Gender`          | Male / Female                               |
| `Age`             | Age in years                                |
| `Tenure`          | Number of years with the bank               |
| `Balance`         | Account balance                             |
| `NumOfProducts`   | Number of bank products used                |
| `HasCrCard`       | Has credit card? (1 = yes)                  |
| `IsActiveMember`  | Active member? (1 = yes)                    |
| `EstimatedSalary` | Estimated salary                            |
| `Exited`          | **Target**: 1 = churned, 0 = retained |

---

## 🧠 Project Workflow

### 1. **Exploratory Data Analysis (EDA)**

- Visualized target distribution (churn vs. retained) – class imbalance observed (≈20% churn).
- Analyzed numerical features using histograms, box plots, and scatter plots.
- Examined categorical features (Geography, Gender, HasCrCard, IsActiveMember, NumOfProducts) with bar charts and churn rate by category.
- Key insights:
  - **Older customers** (age > 40) have significantly higher churn rates.
  - **Germany** and **Female** customers show higher churn.
  - Customers with **zero balance** or **inactive membership** are more likely to churn.
  - Higher credit score and tenure are associated with lower churn.

### 2. **Data Preprocessing**

- Removed unnecessary columns: `RowNumber`, `CustomerId`, `Surname`.
- Converted `Age` to numeric (handled errors).
- Applied one‑hot encoding to `Geography` and `Gender` with `drop_first=True`.
- Scaled numerical features (standardization) – *to be implemented in the modeling notebook*.

### 3. **Model Building**

- We chose a **feed‑forward neural network** (Sequential model) using TensorFlow/Keras.
- Architecture:
  - Input layer (number of features after encoding)
  - Hidden layers with ReLU activation (e.g., 64, 32 neurons)
  - Output layer with sigmoid activation for binary classification.
- Model compiled with `binary_crossentropy` loss, `adam` optimizer, and `accuracy` metric.
- Training and evaluation will be performed on a train/test split (80/20) with early stopping to avoid overfitting.

### 4. **Evaluation**

- Model performance will be assessed using:
  - **Accuracy**, **Precision**, **Recall**, **F1‑score**
  - **ROC‑AUC** and **Confusion Matrix**
  - Comparison with baseline models (Logistic Regression, Random Forest) – *optional*.

---

## 🚀 How to Run

1. **Clone the repository**:
   ```bash
   git clone https://github.com/yourusername/customer-churn-prediction.git
   cd customer-churn-prediction
   ```
