## Activity 7B:  Handedness of Male Boxers --- Theory-based Methods

\setstretch{1}

### Learning outcomes

* Describe and perform a theory-based hypothesis test for a single proportion.

* Check the appropriate conditions to use a theory-based hypothesis test.

* Calculate and interpret the standardized sample proportion.

* Interpret and evaluate a p-value for a theory-based hypothesis test for a single proportion.

* Use the normal distribution to find the p-value.


### Terminology review

In today's activity, we will introduce theory-based confidence intervals for a single categorical variable. Some terms covered in this activity are:

* Parameter of interest

* Standardized Statistic

* Normal distribution

* p-value

To review these concepts, see Chapter 5 in your textbook, focusing on Sections 5.1 through 5.3.

Activity 6 and the Week 6 Lab covered simulation-based methods for hypothesis tests involving a single categorical variable. This activity covers theory-based methods for testing a single categorical variable.  

### Handedness of male boxers

Left-handedness is a trait that is found in about 10\% of the general population. Past studies have shown that left-handed men are over-represented among professional boxers [@richardson2019]. The fighting claim states that left-handed men have an advantage in competition.  In this random sample of 500 male professional boxers, we want to see if there is an over-prevalence of left-handed fighters.  In the sample of 500 male boxers, 81 were left-handed.



```r
 # Read in data set
boxers <- read.csv("https://math.montana.edu/courses/s216/data/Male_boxers_sample.csv")
boxers %>% count(Stance)  # Count number in each Stance category
```

```
#>         Stance   n
#> 1  left-handed  81
#> 2 right-handed 419
```

### Review of summary statistics {-}

1.  Write out the parameter of interest for this study.  

\vspace{0.8in}

2.  Write out the null hypothesis in words.
\vspace{0.8in}

3. Write out the alternative hypothesis in notation.
\vspace{0.3in}

4. Give the value of the summary statistic (sample proportion) for this study.  Use proper notation.

\vspace{0.3in}

### Theory-based methods {-}

The sampling distribution of a single proportion --- how that proportion varies from sample to sample --- can be mathematically modeled using the normal distribution if certain conditions are met.

Conditions for the sampling distribution of $\hat{p}$ to follow an approximate normal distribution:

* **Independence**: The sample’s observations are independent, e.g., are from a simple random sample. (*Remember*: This also must be true to use simulation methods!)

* **Success-failure condition**: We *expect* to see at least 10 successes and 10 failures in the sample, $n\pi≥10$  and $n(1-\pi)≥10$.

5. Verify that the independence condition is satisfied.

\vspace{0.5in}

6. Is the success-failure condition met to model the data with the normal distribution?  Show your work to support your answer. Hint: We don't know the true value of the parameter, $\pi$, so we use the null value, $\pi_0$, to check the success-failure condition.

\vspace{1in}
\newpage

To calculate the standardized statistic we use the general formula 

$$
Z = \frac{\text{point estimate} - \text{null value}}{SE_0(\text{point estimate})}.
$$
For a single categorical variable the standardized sample proportion is calculated using

$$
Z = \frac{\hat{p} - \pi_0}{SE_0(\hat{p})},
$$
where the standard error is calculated using the null value:

$$SE_0(\hat{p})=\sqrt{\frac{\pi_0(1-\pi_0)}{n}}$$.

7.  Calculate the null standard error of the sample proportion.

\vspace{0.6in}

8.  Calculate the standardized sample proportion.  

\vspace{0.6in}

The standardized statistic is used as a ruler to measure how far the sample statistic is from the null value.  Essentially, we are converting the sample proportion into a measure of standard errors to compare to the standard normal distribution.  

9.  Using the 68-95-99.7 rule in Section 5.2.5 to guide you, fill in the percentages on the standard normal distribution displayed in Figure \@ref(fig:simpleNormalcurve), and also mark the value of the standardized statistic calculated in question 8.

\begin{figure}

{\centering \includegraphics[width=0.5\linewidth]{07-A10-inference-1cat_theory_files/figure-latex/simpleNormalcurve-1} 

}

\caption{A standard normal curve.}(\#fig:simpleNormalcurve)
\end{figure}

\newpage

The standardized statistic measures the *number of standard errors the sample statistic is from the null value*.

10.  Interpret the standardized sample proportion from question 8 in context of the problem.

\vspace{.8in}

We will use the `pnorm()` function in `R` to find the p-value. Use the provided `R` script file and enter the value of the standardized statistic calculated in question 8 at `xx` in line 7; highlight and run lines 7--9.  Notice that in line 9 it says `lower.tail = FALSE`.  `R` will calculate the p-value *greater* than the value of the standardized statistic.  

Notes:

* Use `lower.tail = TRUE` when doing a left-sided test.
* Use `lower.tail = FALSE` when doing a right-sided test.
* To find a two-sided p-value, use a left-sided test for negative Z or a right-sided test for positive Z, then multiply the value found by 2 to get the p-value.


```r
pnorm(xx, # Enter value of standardized statistic
      m=0, s=1, # Using the standard normal mean = 0, sd = 1
      lower.tail=FALSE) # Gives a p-value greater than the standardized statistic
```
  
  
11.  Report the p-value obtained from the `R` output.
\vspace{0.2in}

12.  Write a conclusion based on the value of the p-value.
\vspace{0.8in}


#### Validity conditions for a confidence interval {-}

To check the success-failure condition to use theory-based methods for confidence intervals, we use $\hat{p}$ in the calculations since we are not assuming a value for $\pi$. That is, check that we have at least 10 successes and 10 failures in our **sample**:  $n\hat{p} \geq 10$  and $n(1-\hat{p}) \geq 10$.

13.  Verify that the success-failure condition is met to use theory based methods to find a 95\% confidence interval.  

\vspace{0.5in}
\newpage

To calculate a theory-based 95\% confidence interval for $\pi$, we will first find the **standard error** of $\hat{p}$ by plugging in the value of $\hat{p}$ for $\pi$ in $SD(\hat{p})$:

$$SE(\hat{p}) = \sqrt{\frac{\hat{p}(1-\hat{p})}{n}}.$$

Note that we do not include a "0" subscript, since we are not assuming a null hypothesis. 

14.  Calculate the standard error of the sample proportion to find a 95\% confidence interval.

\vspace{0.5in}

To find the confidence interval, we will add and subtract the **margin of error** to the point estimate:

$$\text{point estimate}\pm\text{margin of error}$$
$$\hat{p}\pm z^* SE(\hat{p})$$
The $z^*$ multiplier is the percentile of a standard normal distribution that corresponds to our confidence level. If our confidence level is 95\%, we find the Z values that encompass the middle 95\% of the standard normal distribution.  If 95\% of the standard normal distribution should be in the middle, that leaves 5\% in the tails, or 2.5\% in each tail.  

15. Fill in the normal distribution shown in figure 7.2 to show how `R` found the $z^*$ multiplier.

\begin{figure}

{\centering \includegraphics[width=0.5\linewidth]{07-A10-inference-1cat_theory_files/figure-latex/simpleNormaldist-1} 

}

\caption{A standard normal curve.}(\#fig:simpleNormaldist)
\end{figure}

The `qnorm()` function in `R` will tell us the $z^*$ value for the desired percentile (in this case, 95\% + 2.5\% = 97.5\% percentile). 


```r
qnorm(0.975) # Multiplier for 95% confidence interval
```

```
#> [1] 1.959964
```

16.  What is the value of the multiplier needed to calculate the 95\% confidence interval for the true proportion of male boxers that are left-handed?

\vspace{0.3in}

17.  Calculate the margin of error for the 95\% confidence interval.
\vspace{1in}

18.  Calculate the 95\% confidence interval for the parameter of interest.
\vspace{0.5in}

19.  Interpret the 95\% confidence interval in the context of the problem.
\vspace{1in}

20. Is the null value, 0.1, contained in the 95\% confidence interval?  Explain, based on your conclusion in question 12, why you expected this to be true.
\vspace{1in}


### Take-home messages

1.	Both simulation and theory-based methods can be used to find a p-value for a hypothesis test.  In order to use theory-based methods we need to check that both the independence and the success-failure conditions are met. 

2.  The standardized statistic measures how many standard errors the statistic is from the null value. The larger the standardized statistic the more evidence there is against the null hypothesis.

### Additional notes

Use this space to summarize your thoughts and take additional notes on today's activity and material covered.

\newpage
