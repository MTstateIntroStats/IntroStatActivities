## Activity 7A:  Helper-Hinderer --- Simulation-based Confidence Interval

\setstretch{1}

### Learning outcomes

* Use bootstrapping to find a confidence interval for a single proportion.

* Interpret a confidence interval for a single proportion.

### Terminology review

In today's activity, we will introduce simulation-based confidence intervals for a single proportion. Some terms covered in this activity are:

* Parameter of interest

* Bootstrapping

* Confidence interval

To review these concepts, see Chapters 10 & 14 in your textbook.

### Helper-Hinderer

In the last class, we found very strong evidence that the true proportion of infants who will choose the helper character is greater than 0.5. But what *is* the true proportion of infants who will choose the helper character? We will use this same study to estimate this parameter of interest by creating a confidence interval. 

As a reminder: A study by Hamblin, Wynn, and Bloom reported in Nature [@hamblin2007] was intended to check young kids' feelings about helpful and non-helpful behavior. Non-verbal infants ages 6 to 10 months were shown short videos with different shapes either helping or hindering the climber. Researchers were hoping to assess: Are infants more likely to preferentially choose the helper toy over the hinderer toy? In the study, of the 16 infants age 6 to 10 months, 14 chose the *helper* toy and 2 chose the *hinderer* toy.

A **point estimate** (our observed statistic) provides a single plausible value for a parameter. However, a point estimate is rarely perfect; usually there is some error in the estimate. In addition to supplying a point estimate of a parameter, a next logical step would be to provide a plausible *range* of values for the parameter. This plausible range of values for the population parameter is called an **interval estimate** or **confidence interval**. 

#### Activity intro {-}

1.  What is the value of the point estimate?

\vspace{0.3in}

2.  If we took another random sample of 16 infants, would we get the exact same point estimate?  Explain why or why not.

\vspace{0.5in}

In today's activity, we will use bootstrapping, sampling with replacement from the original sample, to find a 95\% confidence interval for $\pi$, the parameter of interest.  

#### Use statistical analysis methods to draw inferences from the data {-}

To use the computer simulation to create a bootstrap distribution, we will need to enter the 

* "sample size" (the number of observational units or cases in the sample),
* "number of successes" (the number of cases that choose the helper character), 
* "number of repetitions" (the number of samples to be generated), and 
* the "confidence level" (which level of confidence are we using to create the confidence interval).

3.  What values should be entered for each of the following into the simulation to create the bootstrap distribution of sample proportions to find a 95\% confidence interval?
\vspace{1mm}

* Sample size:

\vspace{.1in}
 
* Number of successes:
    
\vspace{.1in}
* Number of repetitions:
    
\vspace{.1in}
* Confidence level (as a decimal):
    
\vspace{.1in}

We will use the `one_proportion_bootstrap_CI()` function in R (in the `catstats` package) to simulate the bootstrap distribution of sample proportions and calculate a confidence interval. Using the provided R script file, fill in the values/words for each `xx` with your answers from question 3 in the one proportion bootstrap confidence interval (CI) code to create a bootstrap distribution with 1000 simulations. Then highlight and run lines 1--9.


```r
one_proportion_bootstrap_CI(sample_size = xx, # Sample size
                    number_successes = xx, # Observed number of successes
                    number_repetitions = 1000, # Number of bootstrap samples to use
                    confidence_level = 0.95) # Confidence level as a decimal
```

4.  Sketch the bootstrap distribution created below.

\vspace{1.8in}

5. What is the value at the center of this bootstrap distribution?  Why does this make sense?
\vspace{.8in}

6. Explain why the two vertical lines are at the 2.5th percentile and the 97.5th percentile.

\vspace{.7in}

7. Report the 95\% bootstrapped confidence interval for $\pi$.  Use interval notation: (lower value, upper value).

\vspace{0.2in}

8.  Interpret the 95\% confidence interval in context.

\vspace{.7in}

#### Communicate the results and answer the research question {-}

9.  Is the value 0.5 (the null value) in the 95\% confidence interval?

\vspace{.2in}

\rgi Explain how this indicates that the p-value will provide similar evidence against the null hypothesis.

\vspace{0.5in}

#### Effect of confidence level {-}

10.  Suppose instead of finding a 95\% confidence interval, we found a 90\% confidence interval.  Would you expect the 90\% confidence interval to be narrower or wider?  Explain your answer.

\vspace{0.4in}

\newpage

11.  The following R code produced the bootstrap distribution with 1000 simulations that follows.  Circle the value that changed in the code. 


```r
one_proportion_bootstrap_CI(sample_size = 16, # Sample size
                    number_successes = 14, # Observed number of successes
                    number_repetitions = 1000, # Number of bootstrap samples to use
                    confidence_level = 0.90) # Confidence level as a decimal
```



\begin{center}\includegraphics[width=0.7\linewidth]{07-A09-inference-1cat_CI-simulation_files/figure-latex/unnamed-chunk-2-1} \end{center}


12.  Report both the 95\% confidence interval (question 7) and the 90\% confidence interval (question 11).  Is the 90\% confidence interval narrower or wider than the 95\% confidence interval?

\vspace{0.5in}

### What does *confidence* mean? {-}

In the interpretation of a 95\% confidence interval, we say that we are 95\% confident that the parameter is within the confidence interval.  Why are we able to make that claim?  What does it mean to say "we are 95\% confident"?

For this part of the activity we will assume that the the true proportion of infants who choose the helper is 0.65. *Note: we are making assumptions about the population here. This is not based on our calculated data, but we will use this applet to better understand what happens when we take many, many samples from this believed population.*

13.  Go to this website, [http://www.rossmanchance.com/ISIapplets.html](http://www.rossmanchance.com/ISIapplets.html) and choose 'Simulating Confidence Intervals'.  In the input on the left-hand side of the screen enter 0.65 for $\pi$ (the true value), 16 for $n$, and 100 for 'Number of intervals'.  Click 'sample'.
\vspace{1mm}

   a. In the graph on the bottom right, click on a green dot.  Write down the confidence interval for this sample given on the graph on the left.  Does this confidence interval contain the true value of 0.65?
\vspace{0.5in}


   b. Now click on a red dot.  Write down the confidence interval for this sample.  Does this confidence interval contain the true value of 0.65?
\vspace{0.5in}

   c. How many intervals out of 100 contain $\pi$, the true value of 0.65? *Hint*:  This is given to the left of the graph of green and red intervals.
\vspace{0.5in}

14.  Click on 'sample' nine more times.  Write down the 'Running Total' for the proportion of intervals that contain $\pi$.

\vspace{0.5in}

15.  Interpret the level of confidence in context of the problem.  *Hint*: What proportion of samples would we expect to give a confidence interval that contains the parameter of interest?

\vspace{0.8in}

### Take-home messages

1.	The goal in a hypothesis test is to assess the strength of evidence for an effect, while the goal in creating a confidence interval is to determine how large the effect is.  A **confidence interval** is a range of *plausible* values for the parameter of interest.  

2. A confidence interval is built around the point estimate or observed calculated statistic from the sample.  This means that the sample statistic is always the center of the confidence interval. A confidence interval includes a measure of sample to sample variability represented by the **margin of error**.   

3. In simulation-based methods (bootstrapping), a simulated distribution of possible sample statistics is created showing the possible sample-to-sample variability.  Then we find the middle $X$ percent of the distribution around the sample statistic using the percentile method to give the range of values for the confidence interval.  This shows us that we are $X$% confident that the parameter is within this range, where $X$ represents the level of confidence.

4.  When the null value is within the confidence interval, it is a plausible value for the parameter of interest; thus, we would find a larger p-value for a hypothesis test of that null value.  Conversely, if the null value is NOT within the confidence interval, we would find a small p-value for the hypothesis test and strong evidence against this null hypothesis. 

5. To create one simulated sample on the bootstrap distribution for a sample proportion, label $n$ cards with the original responses.  Draw with replacement $n$ times.  Calculate and plot the resampled proportion of successes.

6. If repeat samples of the same size are selected from the population, approximately 95\% of samples will create a 95\% confidence interval that contains the parameter of interest.

\newpage

### Additional notes

Use this space to summarize your thoughts and take additional notes on today's activity and material covered.

\newpage

