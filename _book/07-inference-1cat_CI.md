# Inference for a Single Categorical Variable: Confidence Intervals

## Reading Guide: Categorical Inference

### Section 5.1.4 (Foundations of inference: Confidence intervals) {-}

**Videos**  

* 5.1

\setstretch{1.25}

#### Vocabulary {-}

Confidence interval: 
\rgs

Margin of error: 
\rgs

#### Formulas {-}

General form of a theory-based confidence interval: 
\rgs

Margin of error: 
\rgs

#### Example: Martian Alphabet {-} 
1. What is the sample statistic presented in this example?  What notation would be used to represent this value?
\rgs

2. Interpret the 95% confidence interval provided in the textbook.
\rgs
\rgs

3. The formula for the interval is 34/38 $\pm$ (2$\times$0.08) = 0.89 $\pm$ 0.16.  Calculating that, you should get (0.73, 1.05).  Why was the interval shown in the textbook (0.73, 1) instead of (0.73, 1.05)?
\rgs

### Sections 5.3.2 and 5.3.3 (One proportion: Bootstrap confidence intervals and Theory-based inferential methods) {-}

\setstretch{1}

In Section 5.3.3, read only the sub-section on "Confidence interval for $\pi$". The other sections were covered last week.

\newpage

**Videos**  

* 5.3
* OnePropTheory

\setstretch{1.25}

#### Reminders from previous sections {-}

$n$ = sample size

$\hat{p}$ = sample proportion

$\pi$ = population proportion

Confidence interval: a process to determine how large an effect is; a range of plausible values for the parameter; also called 'estimation'.

Margin of error: the value that is added to and subtracted from the sample statistic to create a confidence interval; half the width of a confidence interval.

Parameter: a value summarizing a variable(s) for a population.

Statistic: a value summarizing a variable(s) for a sample.

Sampling distribution: plot of statistics from 1000s of samples of the same size taken from the same population.

Standard deviation of a statistic: the variability of statistics from 1000s of samples; how far, on average, each statistic is from the true value of the parameter.

Standard error of a statistic: estimated standard deviation of a statistic.

Central Limit Theorem: For large sample sizes, the sampling distribution of a sample proportion (or mean) will be approximately normal (bell-shaped and symmetric).


#### Vocabulary {-}

Point estimate: 
\rgs

Test statistic:
\rgs

Bootstrapping: 
\rgs

Bootstrapped resample: 
\rgs

Bootstrapped statistic: 
\rgs

Confidence level: 
\rgs
		
#### Notes {-} 

Purpose of bootstrapping: 
\rgs

How is bootstrapping used?  
\rgs

If we want to find a 90% confidence interval, what percentiles of the bootstrap distribution would we need?  
\rgs

Conditions for the Central Limit Theorem to apply (for the sampling distribution of $\hat{p}$ to be approximately normal)

\rgi Independence: 
\rgs

\rgi \rgi Checked by: 
\rgs

\rgi Success-failure condition: 
\rgs

\rgi \rgi Checked by: 
\rgs

How can we determine the value of $z^⋆$ to use as the multiplier in a confidence interval?
\rgs

\rgi In `R`, use `qnorm(mean = __, sd = __, p = __)`.

Select one answer in each set of parentheses: The higher the confidence level, the (larger/smaller) the multiplier, meaning the confidence interval will be (wider/narrower).

#### Formulas {-}

$SD(\hat{p})$ =
\rgs

Standard error of the sample proportion when we do not assume the null hypothesis is true:

$SE(\hat{p})$ = 
\rgs
	
Theory-based confidence interval for a sample proportion: 
\rgs

Margin of error of a confidence interval for a sample proportion: 
\rgs

#### Example: Organ donations {-}

1. What is the sample statistic presented in this example?  What notation would be used to represent this value?
\rgs

2. What is the parameter representing in the context of this problem?  What notation would be used to represent this parameter?
\rgs
\rgs

3. How could we use cards to simulate **one** bootstrapped resample?  How many blue cards --- to represent what?  How many red cards --- to represent what?  How many times would we draw a card and replace it back in the deck?  What would you record once you completed the draw-with-replacement process?
\rgs
\rgs
\rgs

4.	Interpret the 95\% confidence interval provided in the textbook.
\rgs
\rgs

5.	Are the results in this example statistically significant?  Justify your answer.
\rgs

6.	Are the conditions met to use theoretical methods to analyze these data?
\rgs
\rgs

#### Example: Payday loans {-}

1. What is the parameter representing in the context of this problem?  What notation would be used to represent this parameter?
\rgs
\rgs

2. Are the conditions met to use theoretical methods to analyze these data?
\rgs
\rgs

3. What is the sample statistic presented in this example?  What notation would be used to represent this value?
\rgs

4. Calculate the standard error of the sample proportion when we do not assume the null hypothesis is true.
\rgs
\rgs

5. Calculate the margin of error for a 95\% confidence interval for $\pi$ using 1.96 as the multiplier.
\rgs
\rgs

6. Calculate a 95\% confidence interval for $\pi$ using your margin of error calculated above.
\rgs
\rgs

7. Interpret the 95\% confidence interval provided in the textbook.
\rgs
\rgs

8. Are the results in this example statistically significant?  Justify your answer.
\rgs

\newpage

## Activity:  Handedness of Male Boxers --- Estimation

\setstretch{1}

### Learning objectives

* Use bootstrapping to find a confidence interval for a single proportion.

* Interpret a confidence interval for a single proportion.

### Terminology review

In this week's in-class activity, we will introduce simulation-based confidence intervals for a single proportion. Some terms covered in this activity are:

* Parameter of interest

* Bootstrapping

* Confidence interval

To review these concepts, see Chapter 5 in your textbook, focusing on Sections 5.1 through 5.3.

### Handedness of male boxers

Last week, we found very strong evidence that the true proportion of male boxers who are left-handed is greater than the general population, 0.1.  But what *is* the true proportion of male boxers who are left-handed? We will use this same study to estimate this parameter of interest.  

A **point estimate** (our observed statistic) provides a single plausible value for a parameter. However, a point estimate is rarely perfect; usually there is some error in the estimate. In addition to supplying a point estimate of a parameter, a next logical step would be to provide a plausible *range* of values for the parameter. This plausible range of values for the population parameter is called an **interval estimate** or **confidence interval**. 

As a reminder: left-handedness is a trait that is found in about 10\% of the general population. Past studies have shown that left-handed men are over-represented among professional boxers. The fighting claim states that left-handed men have an advantage in competition.  Using the data from this random sample of 500 male boxers, we want to estimate, with a given level of confidence, the true proportion of male boxers who are left-handed. 

Recall from the last activity that in the sample of 500 male boxers, 81 were left-handed.



#### Activity intro. Complete Q1--Q4 before class. {-}

1.  What is the value of the point estimate?

\vspace{0.5in}

2.  If we took another random sample of 500 male boxers, would you get the exact same point estimate?  Explain why or why not.

\vspace{0.5in}

In this week's activity, we will use bootstrapping to find a 95\% confidence interval for $\pi$, the true proportion of male boxers who are left-handed. See Section 5.3.2 to review bootstrapping.

3.  In your own words, explain the bootstrapping process.
\vspace{0.5in}

4.  Write the conclusion to your test from question 26 in Activity 6.

\vspace{0.5in}

#### Use statistical analysis methods to draw inferences from the data {-}

5.  Write out the parameter of interest for this study in words.

\vspace{0.5in}

To use the computer simulation to create a bootstrap distribution, we will need to enter the 

* "sample size" (the number of observational units or cases in the sample),
* "number of successes" (the number of cases that are left-handed), 
* "number of repetitions" (the number of samples to be generated), and 
* the "confidence level" (which level of confidence are we using to create the confidence interval).

6.  What values should be entered for each of the following into the simulation to create the bootstrap distribution of sample proportions to find a 95\% confidence interval?
\vspace{1mm}

* Sample size:

\vspace{.1in}
 
* Number of successes:
    
\vspace{.1in}
* Number of repetitions:
    
\vspace{.1in}
* Confidence level (as a decimal):
    
\vspace{.1in}

We will use the `one_proportion_bootstrap_CI()` function in `R` (in the `catstats` package) to simulate the bootstrap distribution of sample proportions and calculate a confidence interval. Using the provided `R` script file, fill in the values/words for each `xx` with your answers from question 6 in the one proportion bootstrap confidence interval (CI) code to create a bootstrap distribution with 1000 simulations. Then highlight and run lines 1--11.


```r
one_proportion_bootstrap_CI(sample_size = xx, # Sample size
                    number_successes = xx, # Observed number of successes
                    number_repetitions = 1000, # Number of bootstrap samples to use
                    confidence_level = 0.95) # Confidence level as a decimal
```
7.  Sketch the bootstrap distribution created below.

\vspace{1.8in}

8. What is the value at the center of this bootstrap distribution?  Why does this make sense?
\vspace{.8in}

9. Explain why the two vertical lines are at the 2.5th percentile and the 97.5th percentile.

\vspace{.7in}

10. Report the 95\% bootstrapped confidence interval for $\pi$.  Use interval notation: (lower value, upper value).

\vspace{0.2in}
11.  Interpret the 95\% confidence interval in context.

\vspace{.7in}

#### Communicate the results and answer the research question {-}

12.  Does the confidence interval confirm your conclusion from activity 6?  Explain your answer.

\vspace{.5in}



#### Effect of confidence level {-}

13.  Suppose instead of finding a 95\% confidence interval, we found a 90\% confidence interval.  Would you expect the 90\% confidence interval to be narrower or wider?  Explain your answer.

\vspace{0.4in}

14.  The following `R` code produced the bootstrap distribution with 1000 simulations that follows.  Circle the value that changed in the code. 


```r
one_proportion_bootstrap_CI(sample_size = 500, # Sample size
                    number_successes = 81, # Observed number of successes
                    number_repetitions = 1000, # Number of bootstrap samples to use
                    confidence_level = 0.90) # Confidence level as a decimal
```



\begin{center}\includegraphics[width=0.7\linewidth]{07-inference-1cat_CI_files/figure-latex/unnamed-chunk-2-1} \end{center}


15.  Report both the 95\% confidence interval (question 10) and the 90\% confidence interval (question 14).  Is the 90\% confidence interval narrower or wider than the 95\% confidence interval?

\vspace{0.5in}



### What does *confidence* mean?

In the interpretation of a 95\% confidence interval, we say that we are 95\% confident that the parameter is within the confidence interval.  Why are we able to make that claim?  What does it mean to say "we are 95\% confident"?

16.  Go to this website, [http://www.rossmanchance.com/ISIapplets.html](http://www.rossmanchance.com/ISIapplets.html) and choose 'Simulating Confidence Intervals'.  In the input on the left-hand side of the screen enter 0.1 for $\pi$, 500 for $n$, and 100 for 'Intervals'.  Click 'sample'.
\vspace{1mm}

a) In the graph on the bottom right, click on a green dot.  Write down the confidence interval for this sample given on the graph on the left.  Does this confidence interval contain the null value of 0.1?
\vspace{0.5in}


b) Now click on a red dot.  Write down the confidence interval for this sample.  Does this confidence interval contain the null value of 0.1.?
\vspace{0.5in}


c) How many intervals out of 100 contain $\pi$, the null value of 0.1? *Hint*:  This is given to the left of the graph of green and red intervals.
\vspace{0.5in}

17.  Click on 'sample' nine more times.  Write down the 'Running Total' for the proportion of intervals that contain $\pi$.  

\vspace{0.5in}

18.  Interpret the level of confidence.  *Hint*: What proportion of samples would we expect to give a confidence interval that contains the parameter of interest?

\vspace{1in}

#### Revisit and look forward {-}

19. Suggest a new research question that you might investigate, building on what you learned in this study.

\vspace{.6in}



\newpage

### Out-of-class activity

The in-class activity covered simulation-based methods for confidence intervals involving a single categorical variable. The remaining questions cover theory-based methods for estimating a single proportion.  Use Section 5.3.3 in the textbook and the OnePropTheory video to complete the following questions.

Recall that to use theory-based methods we must check the conditions to approximate the sampling distribution with the normal distribution.  From the previous activity, we saw that independence was satisfied as the researchers took a random sample.

To check the success-failure condition to use theory-based methods for confidence intervals, we use $\hat{p}$ in the calculations since we are not assuming a value for $\pi$. That is, check that we have at least 10 successes and 10 failures in our **sample**:  $n\hat{p} \geq 0$  and $n(1-\hat{p}) \geq 10$.

1.  Verify that the success-failure condition is met to use theory based methods to find a 95\% confidence interval.  

\vspace{0.5in}

To calculate a theory-based 95\% confidence interval for $\pi$, we will first find the **standard error** of $\hat{p}$ by plugging in the value of $\hat{p}$ for $\pi$ in $SD(\hat{p})$:

$$SE(\hat{p}) = \sqrt{\frac{\hat{p}(1-\hat{p})}{n}}.$$
Note that we do not include a "0" subscript, since we are not assuming a null hypothesis. 

2.  Calculate the standard error of the sample proportion to find a 95\% confidence interval.

\vspace{0.5in}


To find the confidence interval, we will add and subtract the **margin of error** to the point estimate:

$$\text{point estimate}\pm\text{margin of error}$$
$$\hat{p}\pm z^* SE(\hat{p})$$

The $z^*$ multiplier is the percentile of a standard normal distribution that corresponds to our confidence level. If our confidence level is 95\%, we find the Z values that encompass the middle 95\% of the standard normal distribution.  If 95\% of the standard normal distribution should be in the middle, that leaves 5\% in the tails, or 2.5\% in each tail.  The `qnorm()` function in `R` will tell us the $z^*$ value for the desired percentile (in this case, 95\% + 2.5\% = 97.5\% percentile). 


```r
qnorm(0.975) # Multiplier for 95% confidence interval
```

```
#> [1] 1.959964
```

3. Using the multiplier of $z^*$ = 1.96, calculate the 95\% confidence interval for the true proportion of male boxers who are left-handed. 

\vspace{1in}

4.  Verify that the simulation-based confidence interval found using bootstrapping is similar to the confidence interval calculating using theory-based methods.

\vspace{1in}

### Take-home messages

1.	The goal in a hypothesis test is to assess the strength of evidence for an effect, while the goal in creating a confidence interval is to determine how large the effect is.  A **confidence interval** is a range of *plausible* values for the parameter of interest.  

2. A confidence interval is built around the point estimate or observed calculated statistic from the sample.  This means that the sample statistic is always the center of the confidence interval. A confidence interval includes a measure of sample to sample variability represented by the **margin of error**.   

3. In simulation-based methods (bootstrapping), a simulated distribution of possible sample statistics is created showing the possible sample to sample variability.  Then we find the middle percent of the distribution around the sample statistic using the percentile method to give the range of values for the confidence interval.  This shows us that we are $X$% confident that the parameter is within these values, where $X$ represents the level of confidence.

4.  In theory-based methods, we add and subtract a margin of error to the sample statistic.  The margin of error is calculated using a multiplier that corresponds to the level of confidence times the variability (standard error) of the statistic.  

5.  When the null value is within the confidence interval, it is a plausible value for the parameter of interest; thus, we would find a larger p-value for a hypothesis test of that null value.  Conversely, if the null value is NOT within the confidence interval, we would find a small p-value for the hypothesis test and strong evidence against this null hypothesis. 

6. To create one simulated sample on the bootstrap distribution for a sample proportion, label $n$ cards with the original responses.  Draw with replacement $n$ times.  Calculate and plot the resampled proportion of successes.

### Additional notes

Use this space to summarize your thoughts and take additional notes on this week's activity and material covered.

