Credit Risk Classification

Purpose of the Analysis: 
The purpose of this analysis was to build and evaluate machine learning models to predict credit risk. Specifically, we aimed to predict whether a loan is "high-risk" (1) or "healthy" (0) based on a set of financial features. The ultimate goal is to provide a reliable model that financial institutions can use to assess the risk associated with issuing loans.

Financial Information of the Data: The data consists of financial information from loan applicants, including variables such as income, loan amount, loan history, and other related factors that can help predict the likelihood of a loan default.

Variables to Predict: The primary variable we aim to predict is the credit risk:
0: Healthy loan (low risk of default)
1: High-risk loan (high risk of default)

To give a basic overview of the distribution, we did the value_counts for the target variable of original data and it showed 

Training data distribution:
loan_status
0    56277
1     1875

Test data distribution:
loan_status
0    18759
1      625

Stages of the Machine Learning Process
Data Preprocessing:
Loaded the lending_data.csv into a Pandas DataFrame. Separated the loan_status column (target variable) into y and the remaining columns into X (features). Split the data into training and testing sets. 

Model Selection:
Logistic Regression was chosen as the first model due to its simplicity and suitability for binary classification tasks.

Model Training:
Trained the Logistic Regression model on the training data (X_train and y_train).

Addressed the class imbalance in the dataset by applying RandomUnderSampler to reduce the overrepresentation of the majority class (healthy loans).

Model Evaluation:
Evaluated the model's performance on the test data using accuracy, confusion matrix, and classification report.
Compared the performance before and after applying undersampling.

Results
Machine Learning Model 1: Logistic Regression (Without Undersampling)
Accuracy: 99.39%
Precision:
Class 0 (Healthy Loan): 1.00
Class 1 (High-Risk Loan): 0.87
Recall:
Class 0: 1.00
Class 1: 0.95

Machine Learning Model 2: Logistic Regression (With Undersampling)
Accuracy: 99.52%
Precision:
Class 0: 1.00
Class 1: 0.87
Recall:
Class 0: 1.00
Class 1: 1.00

Summary
Best Performing Model: The Logistic Regression model with undersampling performed slightly better, with an accuracy of 99.52% compared to 99.39% for the original model. More importantly, it improved the recall for high-risk loans (class 1) to 1.00, meaning all high-risk loans were correctly identified. In terms of precision, before undersampling, the precision for high-risk loans (class 1) was 0.87. After applying undersampling, the precision for high-risk loans remained at 0.87. This indicates that while undersampling improved recall, it did not increase the precision for high-risk loans.

The performance depends heavily on the importance of correctly identifying high-risk loans (class 1). If it’s more critical to ensure all high-risk loans are identified (even at the cost of some false positives), the undersampled Logistic Regression model is preferred due to its perfect recall for high-risk loans.

In conclusion, the Logistic Regression with undersampling is recommended, especially if accurately predicting high-risk loans is a top priority.

