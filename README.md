
# ANOVA  - Lab

## Introduction

In this lab, you'll get some brief practice generating an ANOVA table (AOV) and interpreting its output. You'll then also perform some investigations to compare the method to the t-tests you previously employed to conduct hypothesis testing.

## Objectives

You will be able to:
* Use ANOVA for testing multiple pairwise comparisons
* Understand and explain the methodology behind ANOVA tests

## Loading the Data

Start by loading in the data stored in the file **ToothGrowth.csv**.


```python
# Your code here
```

## Generating the ANOVA Table

Now generate an ANOVA table in order to analyze the influence of the medication and dosage 


```python
#Your code here
```

## Reading the Table

Make a brief comment regarding the statistics regarding the effect of supplement and dosage on tooth length.


```python
# Your comment here
```

## Comparing to T-Tests

Now that you've gotten a brief chance to interact with ANOVA, its interesting to compare the results to those from the t-tests you were just working with. With that, start by breaking the data into two samples: those given the OJ supplement, and those given the VC supplement. Afterwards, you'll conduct a t-test to compare the tooth length of these two different samples.


```python
#Your code here
```

Now compare a t-test between these two groups and print the associated two-sided p-value.


```python
#Your code here; calculate the 2-sided p-value for a t-test comparing the two supplement groups.
```

## A 2-Category ANOVA F-Test is Equivalent to a 2-Tailed t-Test!

Now, recalculate an ANOVA F-test with only the supplement variable. An ANOVA F-test between two categories is the same as performing a 2-tailed t-Test! So, the p-value in the table should be identical to your calculation above.

> Note: there may be a small fractional difference (>0.001) between the two values due to a rounding error between implementations. 


```python
#Your code here; conduct an ANOVA F-test of the oj and vc supplement groups.
#Compare the p-value to that of the t-test above. 
#They should match (there may be a tiny fractional difference due to rounding errors in varying implementations)
```

## Generating Multiple T-Tests

While the 2-category ANOVA test is identical to a 2-tailed t-Test, performing multiple t-tests leads to the multiple comparisons problem. To investigate this, look at the various sample groups you could create from the 2 features: 


```python
for group in df.groupby(['supp', 'dose'])['len']:
    group_name = group[0]
    data = group[1]
    print(group_name)
```

    ('OJ', 0.5)
    ('OJ', 1.0)
    ('OJ', 2.0)
    ('VC', 0.5)
    ('VC', 1.0)
    ('VC', 2.0)


While bad practice, examine the effects of calculating multiple t-tests with the various combinations of these. To do this, generate all combinations of the above groups. For each pairwise combination, calculate the p-value of a 2 sided t-test. Print the group combinations and their associated p-value for the two-sided t-test.


```python
#Your code here; reuse your t-test code above to calculate the p-value for a 2-sided t-test
#for all combinations of the supplement-dose groups listed above. 
#(Since there isn't a control group, compare each group to every other group.)
```

## Summary

In this lesson, you examined the ANOVA technique to generalize A/B testing methods to multiple groups and factors.
