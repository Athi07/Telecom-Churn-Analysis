# Telecom Churn Analysis using EDA

This project aims to analyze customer churn in the telecom industry using Exploratory Data Analysis (EDA). The goal is to identify key factors contributing to churn and provide actionable insights to reduce customer turnover.

## Project Overview

Customer churn is a significant issue for telecom companies, as acquiring new customers is often more expensive than retaining existing ones. By analyzing churn data, we can uncover patterns and trends that help in understanding why customers leave and how to improve retention strategies.

## Files in the Repository

- `Telecom_Churn_Analysis.ipynb`: Jupyter notebook containing the data loading, cleaning, and EDA steps.
- `Telecom Churn.xlsx`: Excel file containing the dataset used for analysis.

## Key Features

- **Data Loading**: Loads data from an Excel file for analysis.
- **Data Cleaning**: Handles missing values, duplicates, and data type conversions to prepare the dataset for analysis.
- **Exploratory Data Analysis (EDA)**: Uses various statistical and visualization techniques to explore the dataset and identify key factors contributing to customer churn.
- **Insights and Recommendations**: Provides actionable insights based on the EDA findings to help reduce churn.

## Requirements

- Python 3.7 or higher
- Jupyter Notebook
- Pandas
- NumPy
- Matplotlib
- Seaborn

# Sample Code
## Data Loading and Cleaning
```
import pandas as pd

# Load dataset
df = pd.read_excel('Telecom Churn.xlsx')

# Display basic information
print(df.info())

# Handle missing values
df = df.dropna()

# Convert data types if necessary
df['TotalCharges'] = pd.to_numeric(df['TotalCharges'], errors='coerce')

# Drop duplicates
df = df.drop_duplicates()

print(df.head())
```
## Exploratory Data Analysis(EDA)
```
import seaborn as sns
import matplotlib.pyplot as plt

# Plot distribution of churn
sns.countplot(x='Churn', data=df)
plt.title('Distribution of Churn')
plt.show()

# Plot correlation matrix
corr = df.corr()
plt.figure(figsize=(10, 8))
sns.heatmap(corr, annot=True, cmap='coolwarm', vmin=-1, vmax=1)
plt.title('Correlation Matrix')
plt.show()

# Box plot of monthly charges by churn status
sns.boxplot(x='Churn', y='MonthlyCharges', data=df)
plt.title('Monthly Charges by Churn Status')
plt.show()

# Histogram of tenure
sns.histplot(df['tenure'], bins=30, kde=True)
plt.title('Distribution of Tenure')
plt.show()
```
# Output
