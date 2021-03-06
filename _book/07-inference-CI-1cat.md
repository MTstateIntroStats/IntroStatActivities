# Estimate the Proportion of Left-Handed Male Boxers

## Learning objectives

* Use bootstrapping to find a confidence interval for a single proportion

* Interpret a confidence interval

## Terminology review

In this week's in-class activity, we will introduce simulation confidence intervals for a single categorical variable. Some terms covered in this activity are:

* Parameter of interest

* Bootstrapping

* Confidence interval

To review these concepts, see Chapter 5 in your textbook, focusing on Sections 5.1 through 5.3.

## Handedness of male boxers

Last week, we found very strong evidence that the true proportion of male boxers who are left-handed is greater than the general population, 0.1.  We will use this same study to estimate the parameter of interest.  As a reminder: left-handedness is a trait that is found in about 10% of the population. Past studies have shown that left-handed men are over-represented among professional boxers. The fighting claim states that left-handed men have an advantage in competition.  Using the data from this random sample of 500 male boxers we want to estimate the true proportion of male boxers who are left-handed.  Recall from the last activity in the sample of 500 male boxers, 81 were left-handed.

A **point estimate** provides a single plausible value for a parameter. However, a point estimate is rarely perfect; usually there is some error in the estimate. In addition to supplying a point estimate of a parameter, a next logical step would be to provide a plausible range of values for the parameter. This plausible range of values for the population parameter is called a confidence interval. 


### Activity Intro. Complete Q1 - 4 before class. {-}

1.  What is the value of the point estimate?

\vspace{0.5in}

2.  If we took another random sample of 500 male boxers, would you get the exact same point estimate?  Explain why or why not.

\vspace{0.5in}

In this week's activity, we will use bootstrapping to find the 95\% confidence interval. See Section 5.3.2 for more information on bootstrapping.

3.  In your own words, explain the bootstrapping process.
\vspace{0.5in}

4.  Write the conclusion to your test from activity 6.

\vspace{0.5in}

### Use statistical analysis methods to draw inferences from the data {-}

5.  Write out the parameter of interest for this study.

\vspace{0.5in}

To use the computer simulation to create a bootstrap distribution, we will need to enter the "sample size" (the number of observational units or cases in the sample), "number of successes" (the number of cases that are left-handed), "number of repetitions" (the number of samples to be generated), and the "confidence level" (which level of confidence are we using to create the confidence interval).

6.  What values should be entered for each of the following into the simulation to create the bootstrap distribution to find a 95\% confidence interval?
\vspace{1mm}

* Sample size:

\vspace{.1in}
 
* Number of successes:
    
\vspace{.1in}
* Number of repetitions:
    
\vspace{.1in}
* Confidence level (as a decimal):
    
\vspace{.1in}

Using the provided `RScript` file, fill in the values/words for xx with your answers from question 6 in the one proportion bootstrap CI code to create a bootstrap distribution with 1000 simulations, highlight and run lines 1 - 11.


```r
one_proportion_bootstrap_CI(sample_size = xx, #Sample size
                    number_successes = xx, #Observed number of successes
                    number_repetitions = 1000, #Number of bootstrap samples to use
                    confidence_level = 0.95) #Confidence level as a decimal
```
7.  Sketch the bootstrap distribution created below.

\vspace{1.8in}

8. What is the value at the center of this bootstrap distribution?  Why does this make sense?
\vspace{.8in}

9. Explain why the two vertical lines are at the 2.5th percentile and the 97.5th percentile.

\vspace{.8in}

10. Report the 95\% bootstrapped confidence interval for $\pi$.  Use interval notation: (lower value, upper value).

\vspace{0.3in}
11.  Interpret the 95\% confidence interval in context.

\vspace{.8in}

### Communicate the results and answer the research question {-}

12.  Does the confidence interval confirm your conclusion from activity 6?  Explain your answer.

\vspace{1in}

\newpage

### Effect of confidence level

13.  Suppose instead of finding a 95\% confidence interval, we found a 90\% confidence interval.  Would you expect the 90\% confidence interval to be narrower or wider?  Explain your answer.

\vspace{0.5in}

14.  The following `R` code produced the bootstrap distribution with 1000 simulations that follows.  What value changed in the code? 


```r
one_proportion_bootstrap_CI(sample_size = 500, #Sample size
                    number_successes = 81, #Observed number of successes
                    number_repetitions = 1000, #Number of bootstrap samples to use
                    confidence_level = 0.90) #Confidence level as a decimal
```



\begin{center}\includegraphics[width=0.7\linewidth]{07-inference-CI-1cat_files/figure-latex/unnamed-chunk-2-1} \end{center}

\vspace{0.5in}

15.  Report both the 95\% confidence interval (question 10) and the 90\% confidence interval (question 14).  Is the 90\% confidence interval narrower or wider than the 95\% confidence interval?

\vspace{0.5in}

\newpage

### What does *confidence* mean?

In the interpretation of the confidence interval, we say that we are 95\% or 90\% confident that the parameter is within the confidence interval.  Why are we able to make that claim?  What does it mean to say "we are 95\% confident"?

16.  Go to this website, http://www.rossmanchance.com/ISIapplets.html and choose `Simulating Confidence Intervals`.  In the input on the left-hand side of the screen enter 0.1 for $\pi$, 500 for $n$, and 100 for `Intervals`.  Click 'sample`.
\vspace{1mm}

|    In the graph on the bottom right, click on a green dot.  Write down the confidence interval for this sample given on the graph on the left.  Does this confidence interval contain the null value of 0.1?
\vspace{0.5in}


|    Now click on a red dot.  Write down the confidence interval for this sample.  Does this confidence interval contain the null value of 0.1.?
\vspace{0.5in}


|    How many intervals out of 100 contain $\pi$, the null value of 0.1? *Hint*:  This is given to the left of the graph of green and red intervals.
\vspace{0.5in}

17.  Click on `sample` nine more times.  Write down the `Running Total` for the proportion of intervals that contain $\pi$.  

\vspace{0.5in}

18.  Interpret the level of confidence in context of the problem.  *Hint*: What proportion of samples would we expect to give a confidence interval that contains the parameter of interest?

\vspace{1in}

### Revisit and look forward {-}

19. Suggest a new research question that you might investigate, building on what you learned in this study.

\vspace{.6in}

\newpage

## Out of Class Activity

The remaining questions cover theory-based methods for testing a single categorical variable.  Use section 5.3.3 in the textbook and the OnePropTheory video to complete the following questions.

Recall that to use theory-based methods we must check the conditions to approximate the sample distribution with the Normal distribution.  From the previous activity we saw that independence was satisfied as the researchers took a random sample.

For finding a confidence interval we need to be sure we have at least 10 successes and 10 failures in our **sample**.

*  $n\hat{p}≥10$  and $n(1-\hat{p})≥10$

1.  Verify that the success/failure condition is met to use theory based methods to find a 95\% confidence interval.  

\vspace{0.5in}

To calculate the 95\% confidence interval we will find the standard error using the sample proportion.

$$SE(\hat{p}) = \sqrt{\frac{\hat{p}(1-\hat{p})}{n}}$$
To find the confidence interval we will add and subtract the margin of error to the point estimate.

$$\text{point estimate}\pm\text{margin of error}$$
$$\hat{p}\pm z^* SE(\hat{p})$$

2.  Calculate the standard error of the sample proportion to find a 95\% confidence interval.

\vspace{0.5in}

The $z^*$ multiplier is found under the standard normal distribution. We find the values that encompass the middle 95\% of the distribution.  If 95\% of the standard normal distribution should be in the middle, that leaves 5\% in the tails, or 2.5\% in each tail.  The qnorm function in `R` will tell us the $z^*$ value for the desired percentile (in this case, 95\% + 2.5\% = 97.5\% percentile). 


```r
qnorm(0.975) # Multiplier for 95% confidence interval
```

```
#> [1] 1.959964
```

3. Using the multiplier of $z^*$ = 1.96, calculate the 95\% confidence interval for the true proportion of male boxers who are left-handed. 

\vspace{1in}

4.  Verify that the simulation confidence interval found using bootstrapping is similar to the confidence interval calculating using theory-based methods.

\vspace{1in}

## Additional notes

Use this space to summarize your thoughts and take additional notes on this week's activity and material covered.

