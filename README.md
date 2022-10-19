# Credit_Risk_Analysis


## Overview of the analysis:

  We use machine learning to predict bad loans. Ideally, this could be used at the application stage, to avoid issuing loans that are likely to default. The current analysis relies on repayment data, such as the amount of the most recent payment, so it can only be used to predict loans turning bad in the near future. Column names are too opaque to clealy distinguish between data available at issuance and later, e.g. repayment, data; so we cannot rerun the analysis to obtain the more important predictions.


## Results:

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



 Use screenshots of your outputs to support your results.

## Summary: 

 The Easy Ensemble model performed strictly better than all others: it is better on every one of the three metrics. So there is no reason to use any of the other models with this data. Depending on one's goals, one might or might not want to use the Easy Ensemble model. Here is the confusion matrix for it:

| | | |
| --- | --- | --- |
|			| labeled good	| labeled bad |
really good	| 15398		| 1706 |
really bad		| 7			| 94 |


 Pretending for a moment that our model could be used to accept or reject loan applications, it would be good for business, but may be bad for society. From the business perspective, 



, that's the model to use if you use any of them. 


 Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. If you do not recommend any of the models, justify your reasoning.



It is also worth noting that the ensemble learning models are quite fast




