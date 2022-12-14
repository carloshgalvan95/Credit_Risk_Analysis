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
---
![oversampling](https://github.com/carloshgalvan95/Credit_Risk_Analysis/blob/main/Resources/oversampling.png)
One form of dealing with imbalanced data is to utilize oversampling. The idea is simple and intuitive: If one class has too few instances in the training set, we choose more instances from that class for training until it's larger.

In random oversampling, instances of the minority class are randomly selected and added to the training set until the majority and minority classes are balanced.

The **Accuracy** of this model is **64.56%** which in itself is low, to truly evaluate the efficiency of the model we are going to further analyze it with a classification report.

#### Confusion Matrix
|                |**Predicted 0**|**Predicted 1**|
|----------------|---------------|---------------|
|**Actual 0**    |53             |34             |
|**Actual 1**    |5443           |11675          |


#### Classification Report
![classification_report_naive](https://github.com/carloshgalvan95/Credit_Risk_Analysis/blob/main/Resources/classification_report_naive.png)

As we can see, the **precision** is quite bad when it comes to high risk, which in the end is our real objective deeming this model useless and dangerous to use, this is enough to discard this model.

### SMOTE Oversampling
---
![smoten](https://github.com/carloshgalvan95/Credit_Risk_Analysis/blob/main/Resources/smoten.png)

The synthetic minority oversampling technique (**SMOTE**) is another oversampling approach to deal with unbalanced datasets. In SMOTE, like random oversampling, the size of the minority is increased. 

The key difference between the two lies in how the minority class is increased in size. As we have seen, in random oversampling, instances from the minority class are randomly selected and added to the minority class. In SMOTE, by contrast, new instances are interpolated.

The **Accuracy** of this model is **62.34%** again, not even close to being good enough, we will probably get even more concerning results when we further analyze it's classification report.

#### Confusion Matrix
|                |**Predicted 0**|**Predicted 1**|
|----------------|---------------|---------------|
|**Actual 0**    |53             |34             |
|**Actual 1**    |6202           |10916          |
#### Classification Report
![classification_report_oversampling](https://github.com/carloshgalvan95/Credit_Risk_Analysis/blob/main/Resources/classification_report_oversampling.png)

More than worrying results for the **precision** when it comes to high risk. Model discarded.

### ClusterCentroids Undersampling
---
![undersampling](https://github.com/carloshgalvan95/Credit_Risk_Analysis/blob/main/Resources/undersampling.png)

Undersampling is another technique to address class imbalance. Undersampling takes the opposite approach of oversampling. Instead of increasing the number of the minority class, the size of the majority class is decreased.

Cluster centroid undersampling is akin to SMOTE. The algorithm identifies clusters of the majority class, then generates synthetic data points, called centroids, that are representative of the clusters. The majority class is then undersampled down to the size of the minority class.

![cluster_centroids](https://github.com/carloshgalvan95/Credit_Risk_Analysis/blob/main/Resources/cluster_centroids.png)

Nevertheless, any strategy for dealing with imbalance has its drawbacks, and it shows here with an **Accuracy** of **51.93%**.

#### Confusion Matrix
|                |**Predicted 0**|**Predicted 1**|
|----------------|---------------|---------------|
|**Actual 0**    |54             |33             |
|**Actual 1**    |9865           |7253           |
#### Classification Report
![classification_report_undersampling](https://github.com/carloshgalvan95/Credit_Risk_Analysis/blob/main/Resources/classification_report_undersampling.png)

Still no changes the **precision** is enough to tell us, that it would be a terrible idea to even consider using the model in real life scenarios.

### SMOTEENN Combination Sampling
---

SMOTEENN combines the SMOTE and Edited Nearest Neighbors (ENN) algorithms. SMOTEENN is a two-step process:

1. Oversample the minority class with SMOTE.
2. Clean the resulting data with an undersampling strategy. If the two nearest neighbors of a data point belong to two different classes, that data point is dropped.

Still, if the starting point is just not good enough, no possible technique will fix it. We have an **Accuracy** of **65.31%**.

#### Confusion Matrix
|                |**Predicted 0**|**Predicted 1**|
|----------------|---------------|---------------|
|**Actual 0**    |60             |27             |
|**Actual 1**    |6563           |10555          |
#### Classification Report
![classification_report_combined](https://github.com/carloshgalvan95/Credit_Risk_Analysis/blob/main/Resources/classification_report_combined.png)

No changes, terrible **precision** yielded.

## Summary
---
After trying to use every tool in our box, it's clear that sometimes the imbalance is going to be just too much to be handled just with balancing techniques.

All of them will have it's drawbacks, and the starting point needs to be good enough to yield results from them, if the imbalance is just not possible to fix any artificial way, and when we have risks at stake and money to lose, sometimes the best strategy is to gather more data, try other methods or be conscious of the risks that involve trusting our evaluation to a model which very bad results in actually predicting what we worry the most about, high risk is not well handled, or handled at all for all that matters.