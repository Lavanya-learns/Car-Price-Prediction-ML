# Car Price Prediction with Machine Learning

#📌 Project Overview

This project predicts the selling price of used cars using machine learning techniques. The project uses a CarDekho vehicle dataset and follows a complete data science workflow, including data cleaning, feature engineering, exploratory data analysis, model training, evaluation, and prediction analysis.

# 🎯 Objective

The main objective is to build regression models that can estimate the selling price of a used car based on characteristics such as present price, kilometers driven, vehicle age, owner count, fuel type, seller type, transmission, and a derived brand category.

# 📊 Dataset

The project uses the **Vehicle Dataset from CarDekho**, containing information about used cars.

# Original Dataset

* Records: 301
* Features: 9
* Target variable: `Selling_Price`

### After Data Cleaning

* Records: 299
* Duplicate records removed: 2
* Missing values: None in the original dataset

### Main Features

| Feature         | Description                     |
| --------------- | ------------------------------- |
| `Car_Name`      | Vehicle model/name              |
| `Year`          | Year of manufacture             |
| `Selling_Price` | Used-car selling price in lakhs |
| `Present_Price` | Present/new price in lakhs      |
| `Kms_Driven`    | Kilometers driven               |
| `Fuel_Type`     | Fuel category                   |
| `Seller_Type`   | Dealer or individual            |
| `Transmission`  | Manual or automatic             |
| `Owner`         | Number of previous owners       |

## 🛠️ Feature Engineering

Two additional features were created:

* **Car_Age** — calculated from the vehicle's manufacturing year.
* **Brand** — derived from the first token of `Car_Name` and used as an approximate categorical feature.

A depreciation percentage was also calculated for exploratory analysis. It was **not used as a machine learning feature** because it is calculated using the target variable and would cause target leakage.

## 🔎 Exploratory Data Analysis

The project analyzes relationships between selling price and several vehicle characteristics.

### Key Findings

* `Present_Price` has a strong positive relationship with `Selling_Price`.
* Older vehicles generally show greater depreciation.
* Vehicle age and kilometers driven show a moderate positive relationship.
* Selling price and kilometers driven have almost no linear relationship in this dataset.
* Selling prices are right-skewed, with most observations concentrated in the lower price range.
* Some high-value vehicles create larger prediction errors.

## 🤖 Machine Learning Models

Two regression models were trained:

1. Linear Regression
2. Random Forest Regression

Categorical variables were encoded using **One-Hot Encoding**, and the preprocessing and models were combined using Scikit-learn pipelines.

### Train-Test Split

* Training
