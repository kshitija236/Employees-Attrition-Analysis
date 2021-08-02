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
2. Numerical features with skewness value greater than 0.8 are transformed using **log transformation.**
