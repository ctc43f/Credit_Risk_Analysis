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
- Of the two ensemble models, adaboost performed slightly better than random forest (when considering accuracy and recall).

However, **I would not recommend using any of these models** for determining if someone should be allowed to have a loan.  For all six models, the precision when looking at just the high-risk category were all extremely low.  For example, if we look at AdaBoost model, the precision on high-risk individuals was 0.05.  In other words, only 5% of those observations it predicted would be high-risk (those that might default on a loan) were actually high risk.  Using this model, they would turn away a lot of individuals seeking loans that could generate revenue from interest.

The model had 81 true positive high-risk predictions and 1,479 false positive high-risk predictions.  Let's assume a bank would lose $100K for every bad loan and would make $10K in interest on every good loan.  If the Bank would turn down all 1,560 individuals based on the model predictions, it would walk away from $6.7M in profit (it would make $14.8M on the good loans but lose $8.1M on bad loans).  In other words, **we can't determine which model is best until we know the cost to the organization of having a false positive versus a false negative** and can balance the model results accordingly.  The Adaboost had the best performance, but using its results alone without some other decision making mechanism seems unwise.
