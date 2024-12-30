
# | AB Test for New Design 

Table of Contents

+ Project Introduction
    + Executive summary
    + About the Data Set
    + Objective
+ Analysis Outputs
+ Detailed Summary and Recommendations

## Project Introduction

Our client has been using the same design for a long time and is considering switching to a new design. They are looking for insight into whether this new method can deliver a higher return compared to the old one. 

## Executive Summary

It was tested using an independent two-sample test and it was found that there was **no significant difference** between the two separate groups, so there was no need to change the design.

## About the Dataset

| Column Name | Description                                                               |
|------------------|---------------------------------------------------------------------------------|
| Impression   | The total number of times the design was viewed by users.                      |
| Click        | The number of times users interacted with the design by clicking on it.         |
| Purchase     | The number of completed purchases made by users after engaging with the design.|
| Earning      | The total revenue generated from the purchases after interacting with the design.|

## Objective

A/B testing was conducted over a 40-day period and our role was to analyse the results of this testing. The primary metric for judging success in this scenario is 'Purchase'. As a result, statistical analyses should prioritise the evaluation of the 'Purchase' criterion.

[See the notebook](https://github.com/AtilaKzlts/AB-Test/blob/main/assets/A-B_Test.ipynb)

## Analysis Outputs

1. Impression
Control Group: Impressions generally range between 80,000 and 150,000. There are fluctuations, but no clear upward or downward trend.
Test Group: Similar pattern, with values close to the control group. Although there are slight differences, a general parallelism is observed.
2. Click
Control Group and Test Group: Clicks are very low and follow an almost straight line. This shows that compared to the number of impressions, users are clicking very little.
3. Purchase
Both Groups: Purchase values are also very low, even at a similar level to clicks. This may indicate that the conversion rate is quite low.
4. Earning
Control Group and Test Group: Earnings levels are in line with the purchase data. There are irregular fluctuations, but earnings are generally low.

![image](https://github.com/AtilaKzlts/AB-Test/blob/main/assets/graph_1.png)

---
After checking the assumptions, the test was carried out

```python
test_stat, pvalue = ttest_ind(df_control['Purchase'], df_test['Purchase'], equal_var=True)
print('Independent Two Sample T Test: Test Stat = %.4f, p-value = %.4f' % (test_stat, pvalue))
```
Independent Two Sample T Test: Test Stat = **-0.9396, p-value = 0.3503**

+ Since the p-value is greater than 0,05, there is no statistically significant difference between the average purchase between the control and test groups.

+ Therefore, it can be concluded that there is no significant difference between the control group and the test group regarding the exchange of "old" and "new" designs.

## Detailed Summary and Recommendations 

Therefore, we can state that there is no reason for the customer to choose between the two designs at this time.
However, it may be advisable to conduct a more thorough analysis, taking into account the client's long-term performance and other factors.
