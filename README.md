# Used Car Price Prediction
🚗 Used Car Analytics: Fair Market Value Estimation & Trust Score Modeling
📌 Project Overview

Buying a used car often involves uncertainty around pricing accuracy and listing reliability. This project addresses that challenge by leveraging large-scale automotive data, statistical modeling, and machine learning to estimate Fair Market Value (FMV) and assess the trustworthiness of used car listings.
Using over 5.6 million VIN-level dealership listings from the U.S. used car market (2013–2022), this analysis supports more transparent pricing, improved buyer confidence, and better-informed business decisions.

🎯 Business Problem

Used car markets are affected by information asymmetry, where sellers typically have more information than buyers. Inaccurate pricing or unreliable listings can lead to financial risk, delayed transactions, or loss of trust.
This project focuses on answering two core business questions:
What is the fair market value of a used vehicle?
How trustworthy is a given used car listing relative to market expectations?

📊 Dataset
Source: MarketCheck automotive listings (via Kaggle)
Market: United States
Time period: 2013–2022
Raw size: 6.2M+ listings
Final cleaned dataset: 5,649,563 listings, no missing values

Key Features
Vehicle details: year, make, model, engine size, engine block, drivetrain, fuel type, transmission
Usage metrics: mileage, miles per year, vehicle age
Engineered variables: log price, log mileage, residuals, trust flag, trust score, market segment

🔍 Methodology
1️⃣ Data Cleaning & Preparation
Removed incomplete records (~560K rows)
Standardized categorical variables
Applied log transformations to handle skewness
Flagged (but retained) price and mileage outliers to preserve real-world market behavior

2️⃣ Exploratory Data Analysis (EDA)
Distribution and outlier analysis
Correlation heatmaps (before vs. after feature engineering)
Market trends by year (listing volume, price, mileage)

3️⃣ Feature Engineering
Vehicle age derived from model year
Miles per year to capture usage intensity
Segment-based categorization (SUV, Sedan, Utility, etc.)
Interaction and residual-based features for trust modeling

🤖 Modeling Approach
Fair Market Value (FMV) Estimation
Model type: Multiple Linear Regression (log-price target)
Best model performance:
R²: ~0.83
RMSE: ~$7,846
Key predictors: vehicle age, miles per year, engine size, segment, fuel type, transmission

Trust Score Model
Model type: Logistic Regression
Uses residual analysis and segment-level statistics
Produces a Trust Score (0–1) indicating prediction reliability
Most listings score above 0.95, while lower scores flag listings needing closer review

📈 Forecasting

Method: Holt’s Linear Trend Model
Target: Median used-car price by year

Insights:
Prices show steady upward movement over time
Temporary dip around 2022 followed by recovery
Supports proactive pricing and inventory planning

💡 Key Insights
Pricing accuracy improves when contextual features (vehicle age, miles per year) are used instead of raw mileage alone
Market segmentation reduces volatility and improves interpretability for business users
Trust scores add a critical confidence layer beyond point price predictions
Extreme prices often reflect legitimate market behavior (e.g., luxury or specialty vehicles), not data errors

📌 Business Impact
Enables more accurate and explainable pricing strategies
Helps prioritize listings that require additional validation
Supports inventory planning through price trend forecasting
Improves transparency and confidence in used car transactions

🛠️ Tools & Technologies
Python (Pandas, NumPy, Scikit-learn, Statsmodels)
Regression & Logistic Models
Time Series Forecasting (Holt’s Method)
Data visualization (Matplotlib / Seaborn)

📎 References

Kaggle Dataset: Used Car Listings for US and Canada (https://www.kaggle.com/datasets/rupeshraundal/marketcheck-automotive-data-us-canada/data)
