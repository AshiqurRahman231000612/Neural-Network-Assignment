# Bank Term Deposit Prediction using Logistic Regression
# Overview
This model is trained on historical banking data containing customer demographics and financial information. It aims to predict whether a bank customer will subscribe to a term deposit using Logistic Regression.
# Dataset
The dataset used is the Bank Marketing Dataset, which contains:

• 17 attributes

• Customer demographic details

• Campaign-related information

• Target variable: subscription (yes or no)
# Methodology
### Step 1: Data Collection
The dataset was downloaded and loaded into a Pandas DataFrame.
### Step 2: Data Exploration
• Checked data types and missing values

• Analyzed class distribution of the target variable
### Step 3: Data Preprocessing
• Converted target variable (yes/no) into binary (1/0)

• Applied one-hot encoding to categorical variables

• Removed redundant columns
### Step 4: Feature Selection
Input features (X) separated from target variable (y)
### Step 5: Train-Test Split
Dataset split into:

• 80% training

• 20% testing
### Step 6: Feature Scaling
Standardized numerical features using StandardScaler
### Step 7: Model Training
• Logistic Regression model trained on training data

• Maximum iterations increased for convergence
### Step 8: Prediction
Model used to predict outcomes on test dataset
### Step 9: Model Evaluation
• Accuracy score calculated

• Confusion matrix generated

• Precision, Recall, and F1-score evaluated
### Results
• Model performs well in identifying non-subscribers

• Some imbalance may affect recall for “yes” class
### Observations
• Logistic Regression provides interpretable results

• Categorical variables significantly impact predictions

• Dataset imbalance may bias predictions
### Conclusion

Logistic Regression is effective for binary classification problems like customer subscription prediction. The model provides a simple yet powerful approach for decision-making in banking systems.
