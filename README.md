# Module 20 Challenge

## Overview of the Analysis
Purpose of Analysis:
- The purose of the analysis undertaken in the Module 20 Challenge is to build a model that accurately predicts whether a loan will have a high risk of defaulting.

Information about dataset:
- The dataset that was used to develop the model (i.e. train and test the model) includes information on more that 75,000 historical loans that were facilitated through a peer-to-peer lending services company.
- Attributes relating to the borrower in the dataset includes: income, total debt, debt to income, and number of accounts.
- Attributes relating to the loan in the dataset includes: loan size, interest rate, derogatory marks, and loan status.

Prediction of model:
- The model has been developed to predict 'loan status' (the variable) by using all other aforementioned attributes (the features). 'Loan status' is a boolean variable where a value of 0 means the loan is healthy, but a value of 1 means that the loan has a high risk of defaulting.

Machine-learning process:
1. The data was separated into features and variables.
2. An initial portion of the dataset was used to train the model.
3. The remaining portion of the dataset was used to test the accuracy of the model.
4. Both a confusion matrix and a classification report were generated in order to review the accuracy of the model.

Method used:
- The method used was logistic regression analysis, which is effective in situations where the dependent variable is boolean or binary (as it is in this case).

## Results

Logistic Regression:
- Accuracy = 0.99
    - This is a high level of accuracy, but doesn't take into account the fact that the dataset variables were mostly (97%) true positives.
- Precision (0) = 1.00
    - This score shows that for all healthy loans, fewer than 0.5% will be labelled as high-risk by the model.
- Precision (1) = 0.85
    - This score shows that for loans that are high-risk loans, 85% of them will be labelled as high-risk by the model.
- Recall (0) = 0.99
    - This score shows that of all the loans predicted to be healthy, only 1% will not be healthy.
- Recall (1) = 0.91
    - This score shows that of all the loans predicted to be high-risk, 9% will not be high-risk.

## Summary

Overall, the high-level accuracy, precision and recall results seem impressive, but this is somewhat misleading. Given most of the loans (96.5%) remain healthy over the loan cycle, if the model predicted that all loans remained healthy, it would have an accuracy score of 0.965. A model such as this would have no predictive power, so an accuracy score of 0.965 should be seen as a baseline score. On that basis, an accuracy score of 0.99 is not highly meaningful.

If we think about the value of the model in a commercial setting, it is in identifying high-risk loans, as the losses incurred from a single loan default are typically many times greater than the profits incurred from a single healthy loan. In this sense, the model's ability to predict 1's is of higher consequence than its ability to predict 0's.

Under the current credit check procedure the peer-to-peer lender goes through (i.e. taking the dataset provided as evidence of previous loans made), a total of 3.5% of the lender's loans were labelled high-risk (and at risk of default). If a borrower also required approval from this model before lending was approved, then only 0.5% of the lender's loans would be labelled high-risk (and at risk of default). This is a significant decrease in the number of high-risk loans, and therefore a significant decrease in losses incurred by lenders - a very good outcome.

The downside experienced if this model was used as an additional screen for lending approval is that there would be a small proportion of borrowers (0.3%) whose loan applications would be declined, even though these borrowers’ loans would remain healthy throughout the loan period.

Given the above justification, I would recommend the peer-to-peer lender implements the model as a lending criterion.

