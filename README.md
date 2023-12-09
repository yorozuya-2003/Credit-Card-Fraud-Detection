# Credit-Card-Fraud-Detection


## Project Overview
This repository contains the implementation and documentation of the "Credit Card Fraud Detection" project, which aims to predict whether a given credit card transaction is real or fraudulent.


## Directory Structure
| File                                 | Description                                                                                   |
|--------------------------------------|-----------------------------------------------------------------------------------------------|
| `notebook_credit_card_fraud_detection.ipynb` | Jupyter notebook containing the project implementation.                                      |
| `project_report_credit_card_fraud_detection.pdf` | PDF report detailing the project, methodology, and results.                                   |


## Problem Statement
Credit risk is associated with the possibility of a client failing to meet contractual obligations, such as mortgages, credit card debts, and other types of loans. The goal of this project is to predict whether a given credit card transaction is real or fraudulent. The [dataset](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud?select=creditcard.csv) used contains transactions made by credit cards in September 2013 by European cardholders. It is highly unbalanced, with only 0.172% of transactions labeled as frauds.


## Data Analysis, Preprocessing & Visualization
- The dataset had no NULL entries or NaN values.
- Positive class (frauds) accounted for 0.172% of all transactions.
- Correlation heatmap and histogram plots were generated to understand feature relationships.
- The "Time" column was dropped, and the "Amount" column was standardized for better pattern recognition.
- Data was split into training and testing sets in an 80:20 ratio.


## Outlier Detection
- Isolation Forest technique was used to detect outliers, with 2849 anomalies identified.
- No fraudulent data entries were detected among the outliers.


## Handling Imbalanced Dataset
### Under-sampling Technique
Implemented from scratch to balance the dataset, keeping all minority class points.

### Over-sampling Technique
Implemented from scratch to balance the dataset by increasing the size of the minority class.

## Classification Techniques
### Linear Discriminant Analysis
Employed due to the high dimensionality of the dataset.

### Random Forest Classifier
Used for dealing with high-dimensional feature spaces and complex relationships.

### Bagging Classifier
Chosen to improve performance by reducing overfitting.

### XGBoost Classifier
Iteratively trains weak learners and handles missing data and imbalanced datasets.


## Manual Ensemble Methods
### Approach-1
Non-fraudulent cases split into batches, with fraudulent cases added to each batch.

### Approach-2
Non-fraudulent and fraudulent cases split into batches, randomly concatenated to create multiple datasets.


## F1-scores for Various Classification Techniques
| Classifier                    | Original Standardized Data | Under-sampled Data | Over-sampled Data |
|-------------------------------|---------------|-------------------|--------------------|
| Linear Discriminant Analysis  | 0.8022        | 0.1886            | 0.3004             |
| RandomForest Classifier       | 0.8636        | 0.0946            | 0.8636             |
| Bagging Classifier            | 0.8457        | 0.0764            | 0.8280             |
| XGBoost Classifier            | 0.8681        | 0.0695            | 0.4737             |
| Ensemble Method - 1           | 0.8205        | 0.0255            | 0.8449             |
| Ensemble Method - 2           | 0.7811        | 0.1670            | 0.8646             |


## Final Pipeline Creation
Based on testing, the XGBoost classifier was chosen for the final pipeline. The model was trained on the complete dataset after standardizing the "Amount" column and dropping the "Time" column. The final pipeline includes a preprocessing step for input datasets, involving dropping the "Time" column and standardizing the "Amount" column, followed by model prediction.


## Team Members
- [Ashudeep Dubey](dubey.6@iitj.ac.in)
- [Tanish Pagaria](pagaria.2@iitj.ac.in)
- [Vinay Vaishnav](vaishnav.3@iitj.ac.in)  

(IIT Jodhpur Undergraduates)