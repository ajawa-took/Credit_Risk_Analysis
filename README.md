# Credit_Risk_Analysis


## Overview of the analysis

  We use machine learning to predict bad loans. Ideally, this could be used at the application stage, to avoid issuing loans that are likely to default. The current analysis relies on repayment data, such as the amount of the most recent payment, so it can only be used to predict loans turning bad in the near future. Column names are too opaque to clealy distinguish between data available at issuance and later, e.g. repayment, data; so we cannot rerun the analysis to obtain the more important predictions.


## Results

 The data is extremely imbalanced: good loans outnumber bad ones by a factor of ~400. Therefore, simple models like the logistic regression require resampling to balance the training data; but more sophisticated models do not.  We tried four resampling methods with the logistic regression model, and two more sophisticated models. Here are the (balanced) accuracy, and the precision and recall of performance metrics for our models.


* Logistic Regression with resampling

| Resampling method | balanced accuracy | precision | recall
| --- | --- | --- | --- |
| Random Oversampling | 0.56 | 0.01  |    0.72|
| SMOTE Oversampling | 0.69 |  0.01   |   0.62 |
| Undersampling with Cluster Centroids | 0.40 | 0.01   |   0.69 |
| SMOTEENN (Over and Under)sampling | 0.58 | 0.01    |  0.71|

* Ensemble Learning models

| Learning Model | balanced accuracy | precision | recall
| --- | --- | --- | --- |
| Balanced Random Forest | 0.89 |0.03   |   0.64|
| Easy Ensemble | 0.90 | 0.05  |    0.93|


## Summary

 The Easy Ensemble model performed strictly better than all others: it is better on every one of the three metrics. So there is no reason to use any of the other models with this data. Depending on one's goals, one might or might not want to use the Easy Ensemble model. Here is the confusion matrix for it:

| confusion matrix| labeled good	| labeled bad |
| --- | --- | --- |
really good	| 15398		| 1706 |
really bad		| 7			| 94 |


 Pretending for a moment that our model could be used to accept or reject loan applications, it would be good for business, but may be bad for society.  From the business perspective, rejecting application labeled bad by the model would have a cost of losing 10% of the business (1,800 out of 17,000 applications) and a benefit of reducing bad loans tenfold, from 0.6% to 0.05% of all loans.  From the societal perspective, it's a problem if 10% of the population cannot access credit. This could be mitigated by different loan institutions using different models, with different people getting unjustly denied credit. This is one of the many problems with a few huge banks dominating the market.

## Other considerations

 Rescaling the data with MinMaxRescaler had surprizingly little effect on the results. As expected, varying the random state had little effect on the results.

 I am not sure why the loan status "In Grace Period" was included in the "bad loan" catergory for this analysis. Dropping it from the data, along with the "Issued" loan status, improved the performance of the model.

### Easy Ensemble Model with loans "In Grace Period" excluded

| balanced accuracy | precision | recall |
| --- | --- | --- |
| 0.96 | 0.05| 0.93 |


| confusion matrix| labeled good	| labeled bad |
| --- | --- | --- |
|really good	| 16384		| 736 |
|really bad		| 3			| 939 |








