# Credit Risk Analysis

## Overview of Analysis

We were asked to utilize several different supervised machine learning models in order to determine which, if any, is best at predicting high credit risks in order to determine who should or shouldn't get loans.  The challenge with this data set is that there is a severe imbalance in the number of data points for the low-risk and high-risk categories.  Because high-risk is the minority group and is what we are attempting to predict, we need to see if oversampling, undersampling, or ensemble learning can help overcome this imbalance and improve prediction scores.  

## Results

We were asked to run six different models and compare their results.  The first four models were logistic regressions with various methods of oversampling and undersampling the data in order to balance the two target classes before modeling.  The last two were ensemble learning methods.  Below is a summary table of the results:

![Summary table](/Resources/summary.png)

Below are the Classification Reports from each of the mdoel types; these will be more important in the Summary section.

**Naive Random Oversampling**

![Model 1](/Resources/lr_naive_random_oversampling.png)

**SMOTE Oversampling**

![Model 2](/Resources/lr_smote_oversampling.png)

**Clustered Centroid Undersampling**

![Model 3](/Resources/lr_cc_undersampling.png)

**SMOTEEN Sampling**

![Model 4](/Resources/lr_smoteen_undersampling.png)

**Random Forest**

![Model 5](/Resources/balancedrandomforest.png)

**Adaboost**

![Model 6](/Resources/adaboost.png)

## Summary

A few observations:
- All of the logistic regression models, regardless of sampling method, performed poorly relative to the two ensemble methods.  Accuracy and recall were lower for all four.  This implies that the decision boundary is non-linear and no linear model would perform well in this situation.
- Of the two ensemble models, adaboost performed slightly better than random forest (when considering accuracy and recall)
