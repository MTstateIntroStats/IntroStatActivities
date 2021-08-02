## Week 10b:  Winter Sports Helmet Use and Head Injuries --- Estimation using Theory-based methods

\setstretch{1}

### Learning objectives

* Assess the conditions to use the normal distribution model for a difference in proportions.

* Create and interpret a theory-based confidence interval for a difference in proportions.

### Terminology review
In this week's activity, we will use theory-based methods to estimate the difference in two proportions. Some terms covered in this activity are:

* Standard normal distribution

* Independence and success-failure conditions

To review these concepts, see Chapter 5 in your textbook.

In this activity we will focus on theory-based methods to calculate a confidence interval.  Like with a single proportion, the sampling distribution of a difference in proportions can be mathematically modeled using the normal distribution if certain conditions are met.

Conditions for the sampling distribution of $\hat{p}_1-\hat{p}_2$ to follow an approximate normal distribution:

* **Independence**: The data are independent within and between the two groups. (*Remember*: This also must be true to use simulation methods!)

* **Success-failure condition**: The success-failure condition holds for each group. Since we are not assuming a null hypothesis, we do not use the pooled sample proportion to check this condition as we did in Activity 8. Instead, we use the individual sample proportions $\hat{p}_1$ and $\hat{p}_2$. Equivalently, we check that all cells in the table have at least 10 observations.

1.  Explain why a theory-based confidence interval for the data set in Activity 22 would not be similar to the bootstrap interval created.

\vspace{1in}

For this activity we will use a new data set. Researchers compared the efficacy of two treatment regimens to achieve durable glycemic control in children and adolescents with recent-onset type 2 diabetes.  A convenience sample of patients 10 to 17 years of age with recent-onset type 2 diabetes were randomly assigned to either a medication (rosiglitazone) or a lifestyle-intervention program focusing on weight loss through eating and activity.  Researchers measured whether the patient still needs insulin (failure) or had glycemic control (success).  Of the 233 children who received the Rosiglitazone treatment,143 had glycemic control, while of the 234 who went through the lifestyle-intervention program, 125 had glycemic control. Is there evidence that there is difference in proportion of patients that achieve durable glycemic control between the two treatments?  Use Rosiglitazone – Lifestyle as the order of subtraction.

2. Complete the following two-way table using the data above.

|                         |     Rosiglitazone    |     Lifestyle    |     Total    |
|-------------------------|----------------------|------------------|--------------|
|     Glycemic Control    |                      |                  |              |
|     Insulin Required    |                      |                  |              |
|     Total               |                      |                  |              |

3. Is the independence condition met for this study? Explain your answer.

\vspace{0.8in}

4.  Is the success-failure condition to find the theory-based confidence interval met for each group?  Explain your answer.

\vspace{1in}

5.  Write the parameter of interest for this study in context of the problem.

\vspace{0.8in}

To find a confidence interval for the difference in proportions we will add and subtract the margin of error from the point estimate to find the two endpoints.

 $$\hat{p}_1-\hat{p}_2\pm z^*SE(\hat{p}_1-\hat{p}_2), \hspace{.2cm} \text{where}$$
 $$SE(\hat{p}_1-\hat{p}_2) = \sqrt{\frac{\hat{p}_1 (1-\hat{p}_1)}{n_1}+\frac{\hat{p}_2 (1-\hat{p}_2)}{n_2}}$$
 
Note that the formula changes when calculating the variability around the statistic in order to calculate a confidence interval from the formula used in Activity 19!  Here, we use the sample proportions for each group to calculate the standard error for the difference in proportions since we are not assuming that the true difference is zero.


6. Calculate the standard error for a difference in proportions to create a 95\% confidence interval.  

\vspace{1in}

7. Interpret the value calculated in question 5 in context of the problem.

\vspace{1in}

\newpage
The $z^*$ multiplier is the percentile of a standard normal distribution that corresponds to our confidence level. If our confidence level is 90\%, we find the Z values that encompass the middle 90\% of the standard normal distribution. If 90\% of the standard normal distribution should be in the middle, that leaves 10\% in the tails, or 5\% in each tail.  The `qnorm()` function in `R` will tell us the $z^*$ value for the desired percentile (in this case, 90\% + 5\% = 95\% percentile). 


```r
qnorm(0.95) # Multiplier for 90% confidence interval
```

```
#> [1] 1.644854
```

8. Sketch a graph of the standard normal distribution and use the graph to explain how the `R` code above is used to find the $z^*$ multiplier.  

\vspace{1.5in}

9. Using the multiplier of $z^*$ = 1.645 and the standard error found in question 5, calculate the margin of error for a 90\% confidence interval.

\vspace{0.5in}

10. Calculate the 90\% confidence interval for the difference in true proportion of . 

\vspace{1in}

11. Interpret the confidence interval found in question 10 in context of the problem.

\vspace{1in}

### Effect of sample size 

Suppose in another sample of children and adolescents we saw these results:

|                         |     Rosiglitazone    |     Lifestyle    |     Total    |
|-------------------------|----------------------|------------------|--------------|
|     Glycemic Control    |          72          |        62        |      134     |
|     Insulin Required    |          45          |        55        |      100     |
|     Total               |          117         |        117       |      234     |

12.  Calculate the margin of error for a 95\% confidence interval using a multiplier of $z^*$ = 1.96 for this new sample.  Is the margin of error larger or smaller than the margin of error for the original study?

\vspace{.8in}

13.  Calculate the 95\% confidence interval for this new study using the margin of error from question 12.  

\vspace{.8in}

15.  Is the confidence interval calculated in question 13 with the smaller sample size wider or smaller than the confidence interval in question 10? Why?

\vspace{.8in}

### Take-home messages

1. Simulation-based methods and theory-based methods should give the same results for a study *if the validity conditions are met*.  For both methods, observational units need to be independent. To use theory-based methods, additionally, the success-failure condition must be met. Check the validity conditions for each type of test to determine if theory-based methods can be used.

2. When calculating the standard error for the difference in sample proportions when doing a hypothesis test, we use the pooled proportion of successes, the best estimate for calculating the variability *under the assumption the null hypothesis is true*.  For a confidence interval, we are not assuming a null hypothesis, so we use the values of the two conditional proportions to calculate the standard error.  Make note of the difference in these two formulas. 

3.  In addition to estimating the difference in proportions for two categorical variables we can also find the relative risk, the ratio of conditional proportions.  

4.  Increasing sample size will result in less sample-to-sample variability in statistics, which will result in a smaller standard error, and thus a narrower confidence interval.  

5. To create one simulated sample on the bootstrap distribution for a difference in sample proportions, label $n_1 + n_2$ cards with the outcomes for the original responses.  Keep groups separate and randomly draw with replacement $n_1$  times from group 1 and $n_2$ times from group 2.  Calculate and plot the resampled difference in the proportion of successes. 


### Additional notes

Use this space to summarize your thoughts and take additional notes on this week's activity and material covered.

\newpage