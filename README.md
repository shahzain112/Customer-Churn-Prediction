# 🏦 Customer Churn Prediction

![Customer Churn Prediction](Customer_Churn_Prediction.png)

> *Model accuracy over training epochs – the graph shows how well our neural network learned to spot customers likely to leave the bank.*

## 📌 Overview

This project is a deep dive into a real-world banking dataset to figure out **why customers close their accounts**.
Using Python and machine learning, I’ve analyzed customer behaviour, identified strong churn signals, and built a neural network to predict churn before it happens.

If we can predict who’s about to leave, we can intervene early and keep them happy.

## 📊 About the Dataset

The dataset (`Churn_Modelling.csv`) contains **10,000 customer records** with 14 features.Here’s the breakdown:

- **Target:** `Exited` – 1 means the customer churned, 0 means they stayed.
- **Features:** Age, Credit Score, Balance, Estimated Salary, Tenure, Number of Products, Active Member status, Geography, Gender, and more.

### Quick Stats

- **Churn Rate:** ~20.4% – that’s **2,037 customers** who left.
- **Zero-balance customers:** 36.2% – a surprisingly large group.

## 🔍 Key Insights from Analysis

### 1. Age is the Strongest Predictor

- **Average age of retained customers:** ~37 years
- **Average age of churned customers:** ~45 years
- Customers in the **51–60 age group** have the highest churn rate (around 34%).

### 2. Active Members Stay, Inactive Members Leave

- **Active members:** Only **14.3%** churn.
- **Inactive members:** A whopping **26.9%** churn.
  👉 Keeping customers engaged makes a *huge* difference.

### 3. Geography Matters

- German customers show a **higher churn rate** compared to French or Spanish customers.
- Region-specific retention strategies might be needed.

### 4. More Products ≠ More Loyalty (Counter-Intuitive!)

- Customers with **3 to 4 products** have significantly higher churn rates.
- In fact, all customers with 4 products in this dataset churned.
  👉 Sometimes *too much* complexity drives people away.

### 5. Correlation with Churn (Top Factors)

| Feature             | Correlation |
| ------------------- | ----------- |
| Age                 | +0.285      |
| Geography (Germany) | +0.173      |
| Balance             | +0.119      |
| Is Active Member    | -0.156      |
| Gender (Male)       | -0.107      |
| NumOfProducts       | -0.048      |

## 🧠 Machine Learning Approach

### Preprocessing

- Dropped `RowNumber`, `CustomerId`, and `Surname` – these don't add value.
- One-hot encoded `Geography` and `Gender`.
- Scaled numerical features for better model performance.

### Model

I built a **Neural Network** using TensorFlow/Keras.
The training accuracy graph (the image at the top) shows how the model improved over time, reaching solid performance on the validation set.

## 🚀 How to Run This Project

1. **Clone this repo** to your local machine.
2. Make sure `Churn_Modelling.csv` is in the same folder as the notebook.
3. Open `project_code.ipynb` in Jupyter Notebook or VS Code.
4. Run all the cells – they’re arranged to guide you step-by-step.

### Required Python Packages

```bash
pip install pandas numpy matplotlib seaborn scikit-learn tensorflow
```
