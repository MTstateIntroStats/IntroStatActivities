## Activity 8b:  Male Boxers --- Estimation using Theory-based Methods

\setstretch{1}

### Learning objectives

* Use bootstrapping to find a confidence interval for a single proportion.

* Interpret a confidence interval for a single proportion.

### Terminology review

In this activity, we will introduce simulation-based confidence intervals for a single proportion. Some terms covered in this activity are:

* Parameter of interest

* Bootstrapping

* Confidence interval

To review these concepts, see Chapter 5 in your textbook, focusing on Sections 5.1 through 5.3.

### Male Boxers

Last class we found very strong evidence that the true proportion of male boxers that are left-handed is greater than 0.1.  In this activity we will use the same data set to find the theory-based 95\% confidence interval.

Remember from the last activity: Left-handedness is a trait that is found in about 10\% of the general population. Past studies have shown that left-handed men are over-represented among professional boxers. The fighting claim states that left-handed men have an advantage in competition.  In this random sample of 500 male professional boxers, we want to see if there is an over-prevalence of left-handed fighters.  In the sample of 500 male boxers, 81 were left-handed.

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

\begin{figure}

{\centering \includegraphics[width=0.6\linewidth]{08-A12-inference-1cat_CI-theory_files/figure-latex/simpleNormal-1} 

}

\caption{A standard normal curve.}(\#fig:simpleNormal)
\end{figure}

3. Fill in the normal distribution above to show how `R` found the $z^*$ multiplier.

\vspace{0.1in}

4.  What is the value of the multiplier needed to calculate the 95\% confidence interval for the true proportion of male boxers that are left-handed?

\vspace{1in}

5.  Calculate the margin of error for the 95\% confidence interval.

\vspace{1in}

6.  Calculate the 95\% confidence interval for the parameter of interest.

\vspace{0.5in}

7.  Interpret the 95\% confidence interval in the context of the problem.

\vspace{1in}

8. Is the null value, 0.1, contained in the 95\% confidence interval?  Explain, based on the p-value from the last activity, why you expected this to be true.

### Effect of Sample Size

Suppose in another sample of 230 male boxers we saw that 37 were left-handed.

9.  Calculate the margin of error for a 95\% confidence interval using a multiplier $z^* = 1.96$ for this sample.  Is the margin of error larger or smaller than the margin of error for the original study?

\vspace{0.5in}

10.  Calculate the 95\% confidence interval for this new study using the margin of error from question 9.  

\vspace{0.5in}

11.  Is the confidence interval calculated in question 10 with the smaller sample size wider or smaller than the confidence interval in question 6?  Why?


### Take-home messages

1.  In theory-based methods, we add and subtract a margin of error to the sample statistic.  The margin of error is calculated using a multiplier that corresponds to the level of confidence times the variability (standard error) of the statistic.

2. The confidence interval calculated using theory-based methods should be similar to the confidence interval found using simulation methods provided the success-failure condition is met.

3.  A smaller sample size will increase the margin of error which results in a wided confidence interval. 


\newpage