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
6. **Principal Component Analysis** is used for dimensionality reduction of data.

## ALgorithm tried
1. LogisticRegression
2. SVC
3. DecisionTreeClassifier 	    
4. RandomForestClassifier 	    
5. ExtraTreesClassifier 	      
6. GradientBoostingClassifier 	
7. AdaBoostClassifier 	        
8. GaussianNB 	

## Metrics used
Above models are compared on the basis of following metrics.
1. Accuracy
2. Precision
3. Sensitivity
4. F1
5. ROC

## Performance of various models
| Sr.No. |            Model           |  Accuracy | Precision | Sensitivity | Specificity | ROC Score |
|:------:|:--------------------------:|:---------:|:---------:|:-----------:|:-----------:|:---------:|
|    1   |     LogisticRegression     | 78.813559 | 52.777778 |  70.370370  |  81.318681  |  0.758445 |
|    2   |             SVC            | 78.813559 | 53.846154 |  51.851852  |  86.813187  |  0.693325 |
|    3   |   DecisionTreeClassifier   | 76.271186 | 48.148148 |  48.148148  |  84.615385  |  0.663818 |
|    4   |   RandomForestClassifier   | 83.050847 | 65.217391 |  55.555556  |  91.208791  |  0.733822 |
|    5   |    ExtraTreesClassifier    | 77.118644 | 50.000000 |  40.740741  |  87.912088  |  0.643264 |
|    6   | GradientBoostingClassifier | 83.050847 | 62.962963 |  62.962963  |  89.010989  |  0.759870 |
|    7   |     AdaBoostClassifier     | 73.728814 | 43.333333 |  48.148148  |  81.318681  |  0.647334 |
|    8   |         GaussianNB         | 75.423729 | 46.666667 |  51.851852  |  82.417582  |  0.671347 |




Comparison of model on basis of these metrics revealed that random forest can be used as final model for predicting attrition.
After finalising the model, **grid search** over range of hyperparameters is used and models were compared using **stratified k-fold cross validation**.
Feature importance is plotted for the final model.

## Observations
1. From the feature importance it was seen that our engineered features i.e. "TenurePerJob", "CompRatioOverall" and "YearsWithoutChange" have higher importance values compared to many of the other given features. Thus it is concluded that feature engineering was successful.
2. Using SMOTE oversampling helped in improving model's predictions. Earlier models were biased towards predicting majority class only, after using SMOTE this is no longer the case.

