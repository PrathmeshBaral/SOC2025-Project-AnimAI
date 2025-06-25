# 📊 Week 1 - Data Cleaning and Visualization

This assignment is focused on learning core data science libraries in Python: **NumPy**, **Pandas**, **Seaborn**, and **Matplotlib**.

## 📁 Dataset Overview
We analyzed a CSV file containing:
- Cartoon popularity scores by country
- Average episodes watched per year
- Merchandise revenue in million USD

## ❗ Issues Identified
1. **Non-numeric values** in columns meant to be numeric (e.g., stored as strings)
2. **Missing values** in both categorical and numerical columns

## ✅ Solutions Applied

### 🔹 Data Type Conversion
- Converted object (string) data to numeric types using Pandas functions.

### 🔹 Handling Missing Values
- **Categorical data**: filled using the **mode** (most frequent value)
- **Numerical data**:
  - Popularity → filled with **mean**
  - Episodes Watched & Revenue → filled with **median**

### 🔹 Text Cleaning
- Capitalized all string values for consistency.
- Corrected spelling errors in country names.

### 🔹 Outlier Detection & Treatment
- Used **box plots** to identify outliers.
- Capped outlier values at calculated upper and lower bounds.

### 🔹 Feature Scaling
- Applied **normalization** to popularity scores:
  \[
  x_{\text{normalized}} = \frac{x - \min(x)}{\max(x) - \min(x)}
  \]

### 🔹 Feature Engineering
Created two new derived features:
1. **Popularity per Episode** = Popularity Score / Avg Episodes Watched Per Year  
2. **Revenue per Episode** = Merchandise Revenue / Avg Episodes Watched Per Year

## 📈 Visualizations
Once cleaned, the data was visualized using **Seaborn** and **Matplotlib** to uncover patterns and insights.
