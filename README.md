# Credit_Risk_Analysis

## Overview
---
Credit risk is an inherently unbalanced classification problem, as good loans easily outnumber risky loans. The strategy to deal with this issue is to employ different techniquesto train and evaluate models with unbalanced classes. The dependencies used to tackle this issue are Scikit-Learn and Imbalanced-Learning with the purpose of building, training and evaluating models using resampling.

### Oversampling the data
The tool used to oversample the data was RandomOverSampler and SMOTE algorithms.

### Undersampling the data
On the contrary, the techniques to perform undersampling will be, ClusterCentroids algorithm.

### The Better Option
Finally, we will try to tackle the unbalance of the data by using a combination of both oversampling and undersampling using the SMOTEEN algorithm to comparetwo new machine learning models that reduce bias, BalancedRandomForestClassifier and EasyEnsembleClassifier all of this with the goal to predict credit risk and evaluate the performance of these models to make an informed decision on whether any of them are suited for real life use.

## Results
---

| **Model** | **Accuracy Score**| 
|-----------|----------------|
| Naive Random Oversampling       |64.56%|
| SMOTE Oversapling               |62.34%|
| ClusterCentroids Undersampling  |51.93%|
| SMOTEENN Combination Sampling   |65.31%|
### Naive Random Oversampling
#### Confusion Matrix
|                |**Predicted 0**|**Predicted 1**|
|----------------|---------------|---------------|
|**Actual 0**    |53             |34             |
|**Actual 1**    |5443           |11675          |

#### Classification Report
![classification_report_naive](https://github.com/carloshgalvan95/Credit_Risk_Analysis/blob/main/Resources/classification_report_naive.png)

### SMOTE Oversampling
---
#### Confusion Matrix
|                |**Predicted 0**|**Predicted 1**|
|----------------|---------------|---------------|
|**Actual 0**    |53             |34             |
|**Actual 1**    |6202           |10916          |
#### Classification Report
![classification_report_oversampling](https://github.com/carloshgalvan95/Credit_Risk_Analysis/blob/main/Resources/classification_report_oversampling.png)

### ClusterCentroids Undersampling
---
#### Confusion Matrix
|                |**Predicted 0**|**Predicted 1**|
|----------------|---------------|---------------|
|**Actual 0**    |54             |33             |
|**Actual 1**    |9865           |7253           |
#### Classification Report
![classification_report_undersampling](https://github.com/carloshgalvan95/Credit_Risk_Analysis/blob/main/Resources/classification_report_undersampling.png)
### SMOTEENN Combination Sampling
---
#### Confusion Matrix
|                |**Predicted 0**|**Predicted 1**|
|----------------|---------------|---------------|
|**Actual 0**    |60             |27             |
|**Actual 1**    |6563           |10555          |
#### Classification Report
![classification_report_combined](https://github.com/carloshgalvan95/Credit_Risk_Analysis/blob/main/Resources/classification_report_combined.png)

## Summary
---
