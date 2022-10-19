# Credit_Risk_Analysis


## Overview of the analysis:

  We use machine learning to predict bad loans. Ideally, this could be used at the application stage, to avoid issuing loans that are likely to default. The current analysis relies on repayment data, such as the amount of the most recent payment, so it can only be used to predict loans turning bad in the near future. Column names are too opaque to clealy distinguish between data available at issuance and later, e.g. repayment, data; so we cannot rerun the analysis to obtain the more important predictions.


## Results:

* Logistic Regression with resampling

| Resampling method | balanced accuracy | precision | recall
| --- | --- | --- | --- |
| Random Oversampling | 0.56 | 0.01  |    0.72|
| SMOTE Oversampling | 0.69 |  0.01   |   0.62 |
| Undersampling with Cluster Centroids | 0.40 | 0.01   |   0.69 |
| SMOTEENN (Over and Under)sampling | 0.58 | 0.01    |  0.71|

* Ensemble Learning models

| Resampling method | balanced accuracy | precision | recall
| --- | --- | --- | --- |
| Balanced Random Forest | 0.89 |0.03   |   0.64|
| Easy Ensemble | 0.90 | 0.05  |    0.93|



 Use screenshots of your outputs to support your results.

## Summary: 

 Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. If you do not recommend any of the models, justify your reasoning.


