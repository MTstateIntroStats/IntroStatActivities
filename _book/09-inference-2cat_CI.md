# Activity 9:  Winter Sports Helmet Use and Head Injuries - Estimation

## Learning objectives

* Assess the conditions to use the standard normal distribution for a difference in proportions

* Create and interpret a confidence interval for the difference in proportions

## Terminology review
In this week's activity, we will use theory-based methods to estimate the difference in two proportions. Some terms covered in this activity are:

* Standard normal distribution

* Independence and success-failure conditions

To review these concepts, see Chapter 5 in your textbook.

## Helmet use and head injuries

In activity 8, we found very strong evidence that helmet use is associated with a reduction in head injury for skiers and snowboarders.  In this in-class activity we will estimate the parameter of interest, the difference in true proportion of skiers and snowboarders with head injuries for those who wore helmets and those that did not, using theory-based methods.


The summary results from a random sample of 3562 skiers and snowboarders involved in accidents is displayed in the two-way table below. Estimate the difference in true proportion of skiers and snowboarders with head injuries for those who wore helmets and those that did not. 

|                | Helmet Use | No Helmet Use | Total |
|:--------------:|:----------:|:-------------:|:-----:|
| Head Injury    |     96     |      480      |  576  |
| No Head Injury |     656    |      2330     |  2986 |
| Total          |     752    |      2810     |  3562 |

### Vocabulary review. Complete Q1 - 3 before class. {-}

1.  Report the point estimate for this study.  Use helmet use minus no helmet use as the order of subtraction.

\vspace{0.4in}

2. Write the conclusion for the study from activity 8.

\vspace{1in}

3. Based on the results from activity 8, do you expect the 95\% confidence interval to contain the null value of zero?  Explain your answer.

\vspace{1in}


### Use statistical analysis methods to draw inferences from the data {-}

In this activity we will focus on theory-based methods to calculate a confidence interval.  Like with a single proportion, the difference in proportions can be mathematically modeled using the normal distribution if certain conditions are met.

Conditions for the sample distribution of $\hat{p}_1-\hat{p}_2$:

* Independence: The data are independent within and between the two groups.

* Success-Failure Condition: For a confidence interval, the success-failure condition holds for each group.  All cells in the table have at least 10 observations.


4. In activity 8, we saw that the independence condition was met since the study used a random sample.  Is the success-failure condition to find the confidence interval met for each group?  Explain your answer.

\vspace{1in}

To find a confidence interval for the difference in proportions we will add and subtract the margin of error from the point estimate to find the two endpoints.

 $$\hat{p}_1-\hat{p}_2\pm z^*SE(\hat{p}_1-\hat{p}_2), \text{where}$$
 
 $$SE(\hat{p}_1-\hat{p}_2) = \sqrt{\left(\frac{\hat{p}_1 (1-\hat{p}_1)}{n_1}+\frac{\hat{p}_2 (1-\hat{p}_2)}{n_2}\right)}$$
 
Note that the formula changes when calculating the variability around the statistic in order to calculate a confidence interval from the formula used in activity 8!  Here, use the sample proportions for each group to calculate the standard error for the difference in proportions.


5. Calculate the standard error for a difference in proportions to create a 95\% confidence interval.  

\vspace{1in}

6. Interpret the value calculated in question 5 in context of the problem.

\vspace{1in}

The $z^*$ multiplier is found under the standard normal distribution. We find the values that encompass the middle 95% of the distribution.  If 95\% of the standard normal distribution should be in the middle, that leaves 5\% in the tails, or 2.5\% in each tail.  The qnorm function in `R` will tell us the $z^*$ value for the desired percentile (in this case, 95\% + 2.5\% = 97.5\% percentile). 


```r
qnorm(0.975) # Multiplier for 95% confidence interval
```

```
#> [1] 1.959964
```

7. Sketch a graph to explain how the `R` code above is used to find the $z^*$ multiplier.  

\vspace{1.5in}

8. Using the multiplier of $z^*$ = 1.96 and the standard error found in question 5, calculate the margin of error for a 95\% confidence interval.

\vspace{0.5in}

9. Calculate the 95\% confidence interval for the difference in true proportion of head injuries for those that used helmets minus those who did not. 

\vspace{1in}

10. Interpret the confidence interval found in question 9 in context of the problem.

\vspace{1in}

## Effect of Sample Size 

Suppose in another sample of skiers and snowboarders involved in accidents we saw these results:

|                | Helmet Use | No Helmet Use | Total |
|:--------------:|:----------:|:-------------:|:-----:|
|   Head Injury  |     135    |      674      |  809  |
| No Head Injury |     921    |      3270     |  4191 |
|      Total     |    1056    |      3944     |  5000 |


11.  Calculate the margin of error for a 95\% confidence interval using a multiplier of $z^*$ = 1.96 for this new sample.  Is the margin of error larger or smaller than the margin of error for the original study?

\vspace{1in}

12.  Calculate the 95\% confidence interval for this new study using the margin of error from question 11.  

\vspace{1in}

13.  Is the confidence interval calculated in question 12 with the larger sample size, wider or smaller than the confidence interval in question 9?

\vspace{1in}

\newpage

## Relative Risk

Another summary statistic that can be calculated for two categorical variables is the relative risk.  The relative risk is calculated as the ratio of the conditional proportions.


$$\text{relative risk} = \frac{\hat{p}_1}{\hat{p}_2}$$

14.  Calculate the relative risk of head injury for those who wore helmets compared to those who did not.

\vspace{1in}

15.  Interpret the relative risk in context of the problem.

\vspace{1in}


## Out of Class Activity

The remaining questions cover simulation methods for creating the bootstrap distribution to find the confidence interval. Use section 5.4.3 in the textbook and the TwoPropSim video to complete the following questions.

To create the bootstrap distribution, we will use the two proportion bootstrap CI function.  We will need to enter the response variable name and the explanatory variable name for the formula, the data set name identified above as `injury`, the outcome for the explanatory variable to give the order of subtraction for First in Subtraction, number of repetitions, the outcome for the response variable that is a success for Response Value Numerator, and the confidence level as a decimal.

The response variable name is Outcome and the explanatory variable name is Helmet.

\newpage
1. What values should be entered for each of the following into the simulation to create a 95\% confidence interval?

\vspace{.5mm}
* First in Subtraction (What is the outcome for the explanatory variable that is used as first in the order of subtraction? `"Yes"` or `"No"`):

\vspace{.2in}
* Response Value Numerator (What is the outcome for the response variable that is considered a success? `"Head Injury"` or `"No Head Injury"`):

\vspace{.2in}
* Number of repetitions:

\vspace{.2in}
* Confidence Level (entered as a decimal):

\vspace{.2in}

Using the `RScript` file for this activity, enter your answers for question 1 in place of the xx's in the two proportion bootstrap CI function to produce the bootstrap distribution with 1000 simulations, highlight and run lines 1 - 22.


```r
two_proportion_bootstrap_CI(formula = Outcome ~ Helmet, 
                            data=injury, #name of dataset
                            first_in_subtraction = "xx", #order of subtraction: enter the name of Group 1
                            response_value_numerator = "xx", #define which outcome is a success 
                            number_repetitions = 1000, #always use a minimum of 1000 repetitions
                            confidence_level = 0.95) #enter the level of confidence as a decimal

```

2. Report the bootstrap 95\% confidence interval. 

\vspace{0.5in}

3. What percentile does the upper value of the confidence interval represent?

\vspace{0.3in}

4. Is the bootstrap 95\% confidence interval similar to what was found using theory-based methods?  Why did you expect this to be true?

\newpage

## Additional notes

Use this space to summarize your thoughts and take additional notes on today's activity.