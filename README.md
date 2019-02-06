## Loan Status Prediction

### Introduction

Personal loan sector is a very competitive and growing sector. Lot&#39;s of people are applying for loans due to a high cost of living that keeps rising on day to day bases, but the loan providers have limited assets which they can grant to limited number of people only.  For that purpose, they use machine learning tools in order to predict in advance, based on historical data, who is the ideal customer and what are his best qualities. By doing so, they won&#39;t waste recourses and money on customers that stand no chance of being approved for a loan.

### Objectives

The main objective of this project is to find the ideal customer and choose the best machine learning model that will predict whether the new applicant will be approved for a loan or not.

### The Dataset

The dataset consists of two merged files, train.csv (614, 14) and test.csv (367, 13).

### Data Manipulations

New Features

total\_income, min\_payment, percent\_of\_income

Missing data that was replaced by Mode in the next specified variables

Dependents, Gender, Married, Self Employed, Loan Amount Term

Missing data that was replaced by Mean

Loan Amount

The most important predictor (Credit History) of Loan Status was treated as follows

Replacement of missing values in the Credit History variable was as follows

1. 1)If Loan Status==Yes, then Credit History gets 1
2. 2)If Loan Status==No, then Credit History gets 0

### Preparations for model testing

- Conversion of all data types to integer
- Dummies - (Dependents, Property Area)
- Scaling - StandardScaler()

## Results

| The Ideal Applicant |   |
| --- | --- |
| Credit History | 1 |
| Dependents | 0 |
| Gender | Male |
| Education | Graduate |
| Loan Amount Term | 360 months |
| Married | Yes |
| Property Area | Any |
| Self Employed | No |
| Loan Amount | 80,000 – 180,000 $ |
| Minimal monthly payment amount | 300 – 500 $ |
| Percent of income spent on the loan | 5-10% / month |







|   | **Model** | **5-Fold**** Cross Validation **|** Grid Search **|** Average Accuracy Score** |
| --- | --- | --- | --- | --- |
| **Logistic Regression** | **86.4** | **83.6** | **82.4** | **84.1** |
| **K neighbors Classifier** | **77.9** | **62.5** | **77.4** | **72.6** |
| **Random Forest Classifier** | **77.3** | **79.5** | **82.8** | **79.9** |
| **Support Vector Classifier** | **85.7** | **69.1** | **82.4** | **79.1** |
| **Decision Tree Classifier** | **82.5** | **81.0** | **82.4** | **82.0** |

## Conclusions

- Logistic regression was found to be the best model (86.4) in the prediction of Loan\_ Status.
- Support Vector Classifier also yielded a good result (85.7), but the Cross-Validation score was found to be very low (69.1) in comparison to other models.
- K neighbor classifier had the lowest performance in all the tested methods.
- Grid Search results were almost identical in 4 out of 5 models (82.4, 82.4, 82.4, 82.8), despite the fact that different hyper-parameters were used for each Grid Search model.
- K=5 Fold Cross Validation yielded the lowest results in all models. K=[3,4,6,7,8] did not improved the results for all models.
- Loan\_Status was found to be correlated only to Credit\_History variable (0.6).
- Removal of low correlated variables had very low or no impact on the scores of the models.
