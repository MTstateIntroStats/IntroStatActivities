## Activity:  Online Classes --- Estimation using Theory-based Methods

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

### Opinions on Online Classes

Last class we found a simulation 95\% confidence interval for the true proportion of patients with COVID-19 that are vitamin D deficient.  In this activity we will use the same data set to find the theory-based 95\% confidence interval.

A recent study investigated the health characteristics among a random sample of 197 patients who were admitted to a hospital following a positive COVID-19 test result.  Among the variables studied, the researchers tested the Vitamin D level (recorded as deficient or not) of each patient.  The study found that 162 of the patients with COVID-19 were vitamin D deficient.  Is this result evidence that vitamin D deficiency is more common among people hospitalized with COVID-19 than we would expect, given that 42% of the US population is reported to have a vitamin D deficiency?

Before we answer the research question we will create a confidence interval to estimate the the true proportion of patients with COVID-19 that are vitamin D deficient. 

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

3. Draw ...multiplier

4.  What is the value of the multiplier needed to calculate the 95\% confidence interval for the true proportion of patients with COVID-19 that are vitamin D deficient. 

\vspace{1in}

5.  Calculate the margin of error for the 95\% confidence interval.

\vspace{1in}

6.  Calculate the 95\% confidence interval for the parameter of interest.

\vspace{0.5in}



7.  Verify that the simulation-based confidence interval found using bootstrapping from the last activity is similar to the confidence interval calculating using theory-based methods.

\vspace{1in}

### What does *confidence* mean?

In the interpretation of a 95\% confidence interval, we say that we are 95\% confident that the parameter is within the confidence interval.  Why are we able to make that claim?  What does it mean to say "we are 95\% confident"?

8.  Go to this website, [http://www.rossmanchance.com/ISIapplets.html](http://www.rossmanchance.com/ISIapplets.html) and choose 'Simulating Confidence Intervals'.  In the input on the left-hand side of the screen enter 0.42 for $\pi$, 197 for $n$, and 100 for 'Intervals'.  Click 'sample'.
\vspace{1mm}

a) In the graph on the bottom right, click on a green dot.  Write down the confidence interval for this sample given on the graph on the left.  Does this confidence interval contain the null value of 0.42?
\vspace{0.5in}


b) Now click on a red dot.  Write down the confidence interval for this sample.  Does this confidence interval contain the null value of 0.42.?
\vspace{0.5in}


c) How many intervals out of 100 contain $\pi$, the null value of 0.42? *Hint*:  This is given to the left of the graph of green and red intervals.
\vspace{0.5in}

9.  Click on 'sample' nine more times.  Write down the 'Running Total' for the proportion of intervals that contain $\pi$.  

\vspace{0.5in}

10.  Interpret the level of confidence.  *Hint*: What proportion of samples would we expect to give a confidence interval that contains the parameter of interest?

\vspace{1in}



\newpage

