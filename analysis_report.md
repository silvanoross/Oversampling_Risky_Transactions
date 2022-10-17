# Module 12 Report Template

## Overview of the Analysis

In this section, describe the analysis you completed for the machine learning models used in this Challenge. This might include:

The purpose of this analysis was to see how resampling a minority class can affect the accuracy, precision and f1 score of a machine learning model. 

The machine learning model used loan size, interest rate, borrower income, debt-to-income ratio, number of accounts, derogatory marks and total debt to determine
whether or not a loan is high or low risk. Essentially, it used credit information to determine loan risk. 

The two predictable outcomes were either 'high-risk' or 'low-risk' loans. There were total of ~75000 loans that qualified as healthy or 'low-risk' as the majority class
and 2500 loans that qualified as 'high-risk' as the minority class.

To develop the machine learning model first the data was split into a 'features' dataframe labeled 'X' and the target varable dataframe labeled 'y'. 

I then tried the analysis on both scaled and unscaled data using the StandardScaler class from sklearn. To make the assignment more consistent I ended up sticking with just the unscaled data. 

Next, the training data was used to fit a logist regression model for predicting the classification of a 'high-risk' or 'low-risk' loan. Finally, the testing data that had been split was used to make predictions and then the accuracy, precision, specificity and f1 score were analyzed in a confusion matrix. 

Next, to account for the imbalance in data points the minority class numbers were brought up to match that of the majority by using the oversampling technique, which randomly duplicates datapoints until both classes have the same number of values. This resampled data was then used to train a logistic regression model and predict the testing target variables. 




## Results

* Machine Learning Model 1 - Imbalanced:
  * Description of Model 1 Accuracy, Precision, and Recall scores.
  * Imbalanced Data Accuracy: 95% 
  * Imbalanced Data Precision low-risk: 100% high-risk: 85%
  * Imbalanced Data Recall Score low-risk: 99% high-risk: 91%
  * Imbalanced Data Specificity low-risk: 91% high-risk: 99%
  * Imbalanced Data F1 Score low-risk: 100 high-risk: 88



* Machine Learning Model 2 - Resampled:
  * Description of Model 2 Accuracy, Precision, and Recall scores.
  * Resampled Data Accuracy: 99% 84
  * Resampled Data Precision low-risk: 100% high-risk: 84%
  * Resampled Data Recall Score low-risk: 99% high-risk: 99%
  * Resampled Data Specificity low-risk: 99% high-risk: 99%
  * Resampled Data F1 Score low-risk: 100 high-risk: 91

## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:
Both models perform at a relatively high level with all scores falling above 80% or higher. The model that uses resampling performs slightly better than the model that does not. This is evident by the f1 score which takes into account both precision and recall. The resampled model lost a 1% point on precision compared to the imbalanced model, meaning it is more aggressive at predicting high-risk loans than what actually there, but that is not necessarily a bad thing. It did get better by 8% with its recall score meaning it called less false negative values. With respect to predicting risky loans the resampled model performed better. 
Obviously, it would be better to have more data to continue to train this model, but overall there seems to be a enough data points to give the model a good base of predicting. It does seem to be slightly overfitted to the training and testing data as the scores are a all on the higher end. 
