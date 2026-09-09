# Bank Marketing Customer Subscription Prediction

## Overview
This project focuses on predicting whether a client will subscribe to a term deposit based on bank marketing campaign data.  
The goal is not only to build a predictive model, but also to structure the analysis as a complete data science workflow: from exploratory data analysis and preprocessing to model evaluation and business interpretation.

## Problem Statement
Banks often run outbound marketing campaigns to promote term deposits, but contacting every customer is costly and inefficient.  
This project aims to identify the customers who are most likely to respond positively, so marketing efforts can be directed more effectively.

## Dataset
The dataset contains demographic, economic, and campaign-related attributes collected from prior marketing interactions.  
It includes both customer-level features and macroeconomic indicators, making it suitable for predictive modeling and business insight generation.

## Data Science Workflow

### 1. Exploratory Data Analysis
- Inspected feature distributions, outliers, and class imbalance
- Analyzed categorical and numerical variables separately
- Explored relationships between features and the target variable
- Visualized key patterns using histograms, boxplots, count plots, and correlation heatmaps

### 2. Data Cleaning and Preprocessing
- Handled missing values and data type consistency
- Encoded categorical variables into numerical format
- Prepared feature sets for machine learning models
- Ensured reproducible preprocessing steps across experiments

### 3. Leakage-Aware Modeling
A critical part of this project was identifying the predictive bias introduced by the `duration` feature.  
Since `duration` is only known after the call ends, it can artificially inflate model performance if used in a real-world pre-call prediction setting.

To address this, two modeling scenarios were evaluated:
- **Full-feature model**: Includes all available variables
- **Business-realistic model**: Excludes `duration` to reduce leakage risk and better reflect operational use

### 4. Model Training and Evaluation
Two classification models were trained and compared:
- Logistic Regression
- Random Forest Classifier

Models were evaluated using:
- Accuracy
- Precision
- Recall
- F1-score
- Confusion Matrix

Because this is a classification problem with potential class imbalance, emphasis was placed on precision/recall trade-offs rather than accuracy alone.

### 5. Feature Importance Analysis
Feature importance was used to identify the variables with the strongest influence on customer subscription behavior.  
This helped move the project beyond prediction and into interpretation, which is essential in applied data science.

## Key Findings
- Random Forest generally outperformed Logistic Regression in capturing non-linear relationships
- The `duration` feature had a strong effect on performance, confirming the importance of leakage-aware modeling
- Customer history and campaign-related variables played a major role in predicting conversion
- The realistic model without `duration` provided a more trustworthy estimate for practical deployment

## Business Impact
This analysis can help banks design more efficient marketing strategies by:
- targeting high-potential clients more effectively
- reducing wasted outreach on low-probability contacts
- improving conversion rates
- supporting data-driven campaign planning

## Project Structure
```text
project-root/
├── data/               # Raw dataset files
├── src/                # Jupyter notebooks and analysis code
├── dist/               # Generated plots and output logs
└── README.md

## Conclusion
This project demonstrates a complete applied data science workflow, from exploratory analysis and preprocessing to leakage-aware modeling and business interpretation.

Rather than focusing only on predictive performance, the analysis also considers real-world usability by evaluating a business-realistic scenario without the `duration` feature.

The final outcome is a practical framework for identifying high-potential customers, improving marketing efficiency, and supporting more informed decision-making in banking campaigns.
