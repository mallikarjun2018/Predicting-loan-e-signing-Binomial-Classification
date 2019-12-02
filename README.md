# Predicting-loan-e-signing-Binomial-Classification

I.	Problem Statement: 
A financial company takes the customer data from P2P lending website and asses whether the person will e-sign the Loan
Challenge : Create the classification model to predict the customer will e-sign [1] or will not e-sign [0] based on the various features of the customer like age, income, credit_score etc

II.	Import Data & Review

•	17908 samples, 21 features
•	no null values
•	Numeric	17
•	Categorical	1
•	Boolean	3
•	53.8% e-signed the loan

III.	EDA

•	Histogram results shows good.Most of the features are right skewed. But 'Months_employed'shows that the data cured for it is not accurate as most of data shows towords 0 - 1.
•	No abnormal distribution of data in Bi/Multi nomial categorical data
•	Top 3 postivity correlated feaures with Traget is  ['risk_score', 'amount_requested', 'has_debt']
•	Top 3 Negatively correlated feaures with Traget is  ['home_owner', 'personal_account_m', 'age']
•	 Correlation Matrix helps to identify the most correlated features.If 2 features are highly corelated then we can keep only one and remove other to overcome multicollinearity.
•	 In the above results the scale shows from -0.2 to +0.3 which is not too high. So most of the features are not high correlated.
•	 income is correlated with amount_requested
•	 years_employed is correlated with current_address_year
•	 amount_requested is correlated with risk
•	 risk 2,3,4 are correlated with each other

IV.	Feature  Engineering

1.	Removed the months_employed column as this is not accurate
2.	Combined personal_account_m & personal_account_y to personal_account_months
3.	Convert categorial variables to numerical by pd_dummies(remove_first)
4.	Saved the userid to a new variables for future evaluation
5.	Categorized the independent features and target to X & y variables respectively
6.	Split the data to train & test with stratify on y
7.	Target values were equally distributed in train & test
8.	Apply standard scaling. As this loses rows & columns need to take of it.

V.	Machine Learning model

Logistic Regression, SVM, RandomForest were applied. And below are the results

•	Among them Random Forest Classifier Accuracy of 63% is consistent
•	Precision tells us about the success probability of making a correct positive class classification
•	Recall explains how sensitive the model is towards identifying the positive class
•	Along with Accuracy, Percision and recall scores are important in assesing the model
•	Classification model should have low FP & FN compared to TP
VI.	Improving the model by AutoML TPOT

•	Running the TPOT Classifier for 20 min suggested GradientBoosting Classifier
•	On re-running for 60 min gives XGBClassifier and gives the accuracy of 64%
 
VII.	Summary

•	The accuracy of the Logistic Regression and Random Forest gives 58% & 63% respectively.
•	XGBClassifier was suggested by TPOT AutoML and now the accuracy moved to 64%




