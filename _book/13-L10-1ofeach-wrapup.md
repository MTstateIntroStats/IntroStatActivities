## Week 13 Lab :  The Triple Crown

\setstretch{1}

### Learning objectives

### Terminology review




###The triple crown

The Triple Crown of "Thru" hiking consists of hiking the Appalachian Trail, the Pacific Crest Trail (PCT), and the Continental Divide Trail (CDT). Each year halfwayanywhere.com conducts a survey to better understand the people who hike these trails. One variable which is queried in the survey is the pre-hike "base weight" of a hiker's pack which is the total weight of gear without food, water, and worn gear. The 131 hikers surveyed who completed the CDT had a mean base weight of 15.266 lbs (sd = 5.128 lbs).  The 484 hikers surveyed who completed the PCT had a mean base weight of 17.837 lbs (sd = 7.823 lbs). Is there a difference in average base weight for PCT hikers and CDT hikers?  Use order of subtraction CDT - PCT.

1. Write out the parameter of interest for this study.

\vspace{0.8in}

2.  Write out the null hypothesis in notation for this study.  Be sure to identify the subscripts.

\vspace{0.5in}

3. Write out the alternative hypothesis in words for this study.

\vspace{0.8in}


\begin{center}\includegraphics[width=0.7\linewidth]{13-L10-1ofeach-wrapup_files/figure-latex/unnamed-chunk-1-1} \end{center}


```
#>   Trail min     Q1 median    Q3  max     mean       sd   n missing
#> 1   CDT 5.9 11.600   14.7 18.10 31.4 15.26641 5.127762 131       0
#> 2   PCT 4.0 12.075   16.8 21.95 49.4 17.83657 7.823128 484       0
```
4. Calculate the summary statistic for this study.  Use appropriate notation.

\vspace{1in}

#### Use statistical inferential methods to draw inferences from the data {-}

5.  Using the provided graphs and summary statistics, determine if it would make the most sense to use theory-based methods or simulation methods.  Explain your reasoning.

\vspace{0.8in}


##### Hypothesis test {-}
Remember that the null distribution is created based on the assumption the null hypothesis is true.  In this study, the null hypothesis states that there is no association between the two variables.  This means that the base weight observed in the data set would have been the same regardless of the type of trails.

We will use the `two_mean_test()` function in `R` (in the `catstats` package) to simulate the null distribution of differences in sample means and compute a p-value. 

6.  When using the `two_mean_test()` function, we need to enter the name of the response variable, `Baseweight`, and the name of the explanatory variable, `Trail`, for the formula.  The name of the data set as shown above is `hikes`.  What values should be entered for each of the following to create 1000 simulated samples?

\vspace{.2in}
* First in subtraction (What is the outcome for the explanatory variable that is used as first in the order of subtraction? `"CDT"` or `"PCT"`):

\vspace{.2in}
* Number of repetitions:
    
\vspace{.2in}
* As extreme as:
    
\vspace{.2in}
* Direction (`"greater"`, `"less"`, or `"two-sided"`):

\vspace{.2in}

7.  Simulate a null distribution and compute the p-value. Using the `R` script file for this activity, enter your answers for question 6 in place of the `xx`'s to produce the null distribution with 1000 simulations.  Highlight and run lines 1--29.


```r
two_mean_test(Baseweight~Trail, data = hikes,  # Variables and data
         first_in_subtraction = "xx", # First outcome in order of subtraction
         number_repetitions = 1000,  # Number of simulations
         as_extreme_as = xx,  # Observed statistic
         direction = "xx")  # Direction of alternative: "greater", "less", or "two-sided"
```

|        Sketch the null distribution created using the code above.
\vspace{1.5in}


8.  Report the p-value. Based off of this p-value, write a conclusion to the hypothesis test.


9. Do you expect the 95\% confidence interval to contain the null value of zero?  Explain.

\vspace{0.8in}

##### Confidence interval {-}
We will use the `two_mean_bootstrap_CI()` function in `R` (in the `catstats` package) to simulate the bootstrap distribution of differences in sample means and calculate a confidence interval. 

10. Using bootstrapping find a 95\% confidence interval. Using the provided `R` script file, enter the variable names and data set name as in the `two_mean_test()` function, outcome name for the first in subtraction, number of repetitions, and the confidence level as a decimal.  Highlight and run lines 32--35. Report the 95\% confidence interval in interval notation.

```r
two_mean_bootstrap_CI(RESPONSE ~ EXPLANATORY, data = DATASET,  # Variables and data
                      first_in_subtraction = "xx", # First value in order of subtraction
                      number_repetitions = 1000,  # Number of simulations
                      confidence_level = xx)
```

\vspace{0.3in}

11. Interpret the interval you calculated in question 10. 

\vspace{1in}


13.  Do the results of the CI agree with the p-value??...

\vspace{0.5in}

14. Write a paragraph summarizing the results of the study as if writing a press release.  Be sure to describe:

* Summary statistic and interpretation

* Test statistic and interpretation

* P-value and interpretation

* Confidence interval and interpretation

* Conclusion (written to answer the research question)

* Scope of inference

\vspace{2in}

