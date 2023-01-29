# Credit Risk Analysis

## Overview of Analysis

We were asked to utilize several different supervised machine learning models in order to determine which, if any, is best at predicting high credit risks in order to determine who should or shouldn't get loans.  The challenge with this data set is that there is a severe imbalance in the number of data points for the low-risk and high-risk categories.  Because high-risk is the minority group and is what we are attempting to predict, we need to see if oversampling, undersampling, or ensemble learning can help overcome this imbalance and improve prediction scores.  

## Results

We were asked to run six different models and compare their results.  The first four models were logistic regressions with various methods of oversampling and undersampling the data in order to balance the two target classes before modeling.  The last two were ensemble learning methods.  Below is a summary table of the results:

![Summary table](/Resources/summary.png)
