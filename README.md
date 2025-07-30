# Uber Transactions Earnings Analysis & Prediction

---

## 📌 Project Overview

As an Uber driver, I have regular access to my weekly transaction statements, which include details such as:

- Event type  
- Your earnings  
- Refunds and Expenses  
- Balance  
- Processed Date  

The purpose of this project is to analyze these transactions and predict daily or monthly earnings based on key variables. This helps in identifying patterns in driving performance, optimizing work hours, and forecasting income trends more accurately.

---

## 🧠 Objectives

- Explore and clean Uber transaction data  
- Visualize trends in earnings, expenses, and ride activity  
- Engineer features relevant to driver performance  
- Model relationships using linear regression  
- Evaluate and refine the model using statistical techniques  

---

## 🔍 Data Summary

The data was extracted from weekly Uber statements and contains:

| Column            | Description                        |
|-------------------|----------------------------------|
| Processed_Date    | Date the transaction was recorded  |
| Your earnings     | Gross earnings for the day/event  |
| Refunds & Expenses| Deductions from the earnings       |
| Balance           | Final balance (earnings - expenses) |
| Event             | Category (UberX, Tips, Adjustments, etc.) |

---

## 🧪 Workflow Summary

### 📦 1. Library Imports
- `pandas`, `numpy`: Data handling  
- `matplotlib`, `seaborn`: Visualization  
- `statsmodels`, `sklearn`: Modeling and evaluation  

### 📁 2. Data Loading & Preprocessing

```python
import pandas as pd

df = pd.read_csv("uber_transactions_extracted.csv")
df = df.sort_values("Processed_Date")
df['Processed_Date'] = pd.to_datetime(df['Processed_Date'])

📈 3. Visual & Statistical Analysis
Monthly Trends: Group by Year and Month; plot total monthly balance

Weekday Analysis: Compare average earnings across weekdays; identify most/least profitable days

Distribution & Relationships: Histogram of earnings; scatter plots of earnings vs balance and expenses; correlation heatmap

🧠 Feature Engineering
Created Net_Earnings = Your earnings - Refunds & Expenses

Applied one-hot encoding to categorical features like Event

🧮 4. Linear Regression Modeling
Built Ordinary Least Squares (OLS) regression model using statsmodels

Applied Backward Feature Elimination to remove variables with p-value > 0.05

Improved Adjusted R² by retaining only significant predictors

🤖 5. Train/Test Evaluation
Used Scikit-learn’s LinearRegression

Evaluated with:

R² Score

MSE / RMSE / MAE

Plotted predicted vs actual results

🔍 Final Model Output
Significant Predictors: Net earnings, Refunds, Weekday, Event type (some)

Adjusted R²: Indicates the model explains a large proportion of earnings variability

Prediction Accuracy: Verified on unseen data using train-test split

🎯 Business Value
With this project, Uber drivers can:

Understand which days and ride types yield higher income

Predict earnings more accurately based on input features

Plan driving schedules based on trends in refunds, demand, and net earnings

📂 Project Structure
bash
Copy
Edit
uber_transactions_analysis/
│
├── data/                        # Raw and processed data files
├── notebooks/                   # Jupyter notebooks for EDA and modeling
├── scripts/                    # Python scripts for preprocessing, modeling
├── visuals/                    # Plots and charts
├── requirements.txt            # Python dependencies
└── README.md                   # Project documentation
📌 Contact
For questions or suggestions, feel free to open an issue or contact me.

