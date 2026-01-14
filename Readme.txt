Premium vs Standard Car Sales Classification
Problem Understanding

Car dealerships generate large volumes of sales transaction data, but often lack structured insights into what differentiates high-value (premium) sales from standard sales. Understanding these differences is important for improving sales strategies, evaluating salesperson performance, and identifying customer behaviors associated with premium transactions.

The dataset used in this project consists of completed car sales transactions along with customer demographic and sales-related information. Since the data represents post-transaction records and does not include a predefined outcome label, the problem is framed as a sales transaction classification task rather than a predictive forecasting problem.

The objective is to classify historical sales transactions into Premium and Standard categories and analyze the factors that contribute to high-value sales.

Objective

Create a meaningful target variable using business logic

Perform exploratory data analysis to identify important patterns

Engineer relevant features to capture customer and transaction behavior

Build and evaluate classification models

Interpret results to derive actionable business insights

Approach and Methodology
Target Variable Creation

The dataset does not contain an explicit label indicating the type of sale. A sale is classified as Premium if its sale price lies within the top 25 percent of all transactions; otherwise, it is classified as Standard. A percentile-based threshold was chosen to ensure robustness against outliers and maintain a relative definition of high-value sales.

Data Preprocessing

Removed identifiers and personal information such as customer ID, name, phone number, and email

Converted date columns to datetime format for temporal analysis

Excluded sale price from input features to prevent data leakage

Encoded categorical variables using One-Hot Encoding with unknown category handling

Scaled numerical features using StandardScaler

Feature Engineering

Temporal features such as sale month and weekday

Behavioral indicators including bulk purchase flag and senior customer flag

Customer demographics such as age, gender, and city

Transaction attributes including quantity, payment method, and salesperson

Exploratory Data Analysis

Analyzed the distribution of premium and standard sales

Studied relationships between age, payment method, salesperson, and sale type

Identified patterns and trends influencing premium transactions

Model Building

Two classification models were implemented and compared:

Logistic Regression for interpretability and baseline comparison

Random Forest Classifier to capture non-linear relationships and feature interactions

Model Evaluation

Models were evaluated using precision, recall, F1-score, ROC-AUC score, and confusion matrix. Accuracy alone was avoided to ensure a balanced evaluation of premium sale identification.

Tools and Technologies Used

Programming Language: Python

Libraries: pandas, numpy, matplotlib, seaborn, scikit-learn, joblib

Development Environment: Jupyter Notebook / Python environment

Version Control: Git and GitHub

Challenges Faced

Absence of a predefined target variable

Ensuring logical problem formulation for post-transaction data

Preventing data leakage during target creation and feature selection

Handling unseen categorical values during model evaluation

Balancing model interpretability and performance

Design and Creative Decisions

Framed the task as a transaction classification problem instead of future outcome prediction

Used percentile-based labeling to define premium sales

Implemented preprocessing and modeling using pipelines for clean and reusable code

Selected Random Forest for robustness and Logistic Regression for interpretability

Focused on insights and reasoning rather than optimizing accuracy alone

Key Insights

Premium sales are more frequent among older customers

Certain payment methods are strongly associated with high-value transactions

Salesperson performance varies in closing premium sales

Bulk purchases are strong indicators of premium transactions

Conclusion

This project demonstrates the application of machine learning to sales transaction analysis through careful problem framing, exploratory data analysis, and explainable classification models. The emphasis on business reasoning, feature engineering, and evaluation methodology ensures that the insights derived are meaningful and actionable.