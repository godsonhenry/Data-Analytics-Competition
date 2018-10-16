# Data-Analytics-Competition
Code Sample for Data Analytics Competition (1st Team)

**Objective:**
The Data includes simplified info of insurance policy (7000 obervations with 18 feauters). The project is to predict whether the policy holders would like to cancel their policy (binary, 1/0)
AUC score was seelcted as evaluation metric.

**Process**
1. Exploratroy Data Analysis:
    * identify data type
    * check distribution of variable, (Outlier detection)
    * treat missing values
    
2. Feature Process:
    * transform data (Numeric and Categorical features)
    * Stanardardization
    
3. Feature Enginnering
    * find mathmatic relation between variables
    * geo coding to transform Zipcode

4. Feature Selection
    * backward step-wise process 
    * fit data into logistic regression with lasso penalty
    * fit data into XGBoost
    * review performance metrics and feature importance to select initial feature candidates
    * evaluate feature candidates in Monte Carlo Cross-Validation with Logistic Regression
    * The process keeps running untill the final feature candidates are fixed

5. Model Selection
    * Prepare initial model pool
    * fit data to model with 10-folder cross validation and tune parameters 
    * select model with good performances
    
6. Model Ensemble
    * code model ensemble structure using 'Stacking' Ensemble Format
    * use XGBoost as second level model in ensemble model
    * overall model performance is enhanced

**Results**
AUC score was improved 10%, from 0.67 to 0.73

**Discussion**
1. Merely judged by AUC, and logisic regression produced best AUC score. And GBM, SVM, XGBoost suffered from overfitting. Even though 'stacking' ensemble reduce ovefitting problem, modeling on holdout data still show decreasing in AUC score.
2. The data set was modified by competition commitee for competition purpose. So the data didn't present true scenario of insurance.
3. Model ensemble indeed is a good way to enhance prediction performance.

**Business Value**
1. Conducted customer segmentation based on selected features.
2. Provided recommendations how to prevent policyhollder from cancelling policy.
