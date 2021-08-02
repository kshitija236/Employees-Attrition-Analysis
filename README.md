#  Prediction of Attrition of Employees using Machine Learning 
##  Project Description
The objective of this project is to predict whether an employee will resign or not based on given parameters. Data is analysed, preprocessed and feature engineering was done
before using machine learning algorithms. Different ML algorithms are compared on the basis of accuracy, precision, recall, F1 and ROC scores. Based on these metrics final model 
is selected and its hyperparamaters are tuned using grid search and stratified k-fold cross validation. 

## Data
Data is taken from IBM HR Analytics Employee Attrition & Performance at kaggle https://www.kaggle.com/pavansubhasht/ibm-hr-analytics-attrition-dataset/download
The downloaded file is present in Data folder. 

## Exploratory Data Analysis
1. Graphs of features vs. attrition is plotted to examine effect of features on attrition.
2. Histogram of numerical features is used to examine distribution.
3. Plot of attrition distribution shows **highly imbalanced data**.

## Preprocessing and feature engineering
1. Categorical features are encoded using **one hot encoding scheme**.
2. Numerical features with **skewness** value greater than 0.8 are transformed using **log transformation.**
3. Three **new features** viz. tenure per job, years without change and compensation ratio were **created** using existing features.
4. **Irrelevant attributes** viz. EmployeeNumber, EmployeeCount, Over18 and StandardHours were **dropped**.
5. Sybthetic Minority Oversampling Technique **SMOTE** is used to tackle data imbalance.

## ALgorithm tried
1. Decision Tree
2. SVC
3. Random Forest
4. Gaussian naïve Bayes 
5. Gradient Boosting

Above models are compared on the basis of following metrics.
1. Accuracy
2. Precision
3. Recall
4. F1
5. ROC

Comparison of model on basis of these metrics revealed that random forest can be used as final model for predicting attrition.
After finalising the model, **grid search** over range of hyperparameters is used and models were compared using **stratified k-fold cross validation**.
Feature importance is plotted for the final model.

Observations:
1. From the feature importance it was seen that our engineered features i.e. "TenurePerJob", "CompRatioOverall" and "YearsWithoutChange" have higher importance values compared to many of the other given features. Thus it is concluded that feature engineering was successful.
2. Using SMOTE oversampling helped in improving model's predictions. Earlier models were biased towards predicting majority class only, after using SMOTE this is no longer the case.
3. Hyperparamter tuning using grid search resulted in improved ROC score on validation set from 59% to 69%.
