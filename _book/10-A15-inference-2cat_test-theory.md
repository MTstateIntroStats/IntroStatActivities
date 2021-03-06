## Activity 10a:  Winter Sports Helmet Use and Head Injuries --- Testing using Theory-based Methods

\setstretch{1}

### Learning objectives

* Given a research question involving two categorical variables, construct the null and alternative hypotheses
  in words and using appropriate statistical symbols.
  
* Assess the conditions to use the normal distribution model for a difference in proportions.

* Calculate the Z test statistic for a difference in proportions.

* Find, interpret, and evaluate the p-value for a theory-based hypothesis test for a difference in proportions.

### Terminology review
In this week's in-class activity, we will use theory-based methods to analyze two categorical variables. Some terms covered in this activity are:

* Conditional proportion

* Z test

* $z^*$ multiplier

* Null hypothesis

* Alternative hypothesis

* Test statistic

* Standard normal distribution

* Independence and success-failure conditions

* Type 1 and Type 2 errors

* Decision of a hypothesis test

To review these concepts, see Chapter 5 in your textbook.

### Helmet use and head injuries

For this activity we will again use the data set from the helmet use study.  See the information below.

In "Helmet Use and Risk of Head Injuries in Alpine Skiers and Snowboarders" by Sullheim et. al., in the *Journal of the American Medical Association*, Vol. 295, No. 8 (2006), we can see the summary results from a random sample of 3562 skiers and snowboarders involved in accidents in the two-way table below. Is there evidence that safety helmet use is associated with a reduced risk of head injury for skiers and snowboarders? 

|                | Helmet Use | No Helmet Use | Total |
|:--------------:|:----------:|:-------------:|:-----:|
| Head Injury    |     96     |      480      |  576  |
| No Head Injury |     656    |      2330     |  2986 |
| Total          |     752    |      2810     |  3562 |

1.  Write the null and alternative hypotheses in notation. 

|    Ho: 
\vspace{0.2in}

|    Ha:
\vspace{0.2in}

2.  Calculate the summary statistic for this study.  Use helmet use (`Yes`) minus no helmet use (`No`) as the order of subtraction.

\vspace{0.5in}

`
#### Use statistical analysis methods to draw inferences from the data {-}

To test the null hypothesis, we could use simulation-based methods as we did in Activity 9a. In this activity, we will focus on theory-based methods.  Like with a single proportion, the sampling distribution of a difference in sample proportions can be mathematically modeled using the normal distribution if certain conditions are met.

Conditions for the sampling distribution of $\hat{p}_1-\hat{p}_2$ to follow an approximate normal distribution:

* **Independence**: The data are independent within and between the two groups. (*Remember*: This also must be true to use simulation methods!)

* **Success-failure condition**: The success-failure condition holds for each group.  Under the null hypothesis, the proportions $\pi_1$ and $\pi_2$ are equal, so we check the success-failure condition with our best estimate of these values under $H_0$, the pooled proportion from the two samples,

$$
\hat{p}_{pool} = \frac{\text{number of "successes"}}{\text{number of cases}} = \frac{\hat{p}_1 n_1+\hat{p}_2 n_2}{n_1+n_2}
$$
We then check that all four of the following inequalities hold:

$$\hat{p}_{pool} \times n_1 \ge 10, \hspace{1cm} (1 - \hat{p}_{pool}) \times n_1 \geq 10,$$
$$\hat{p}_{pool} \times n_2 \ge 10, \hspace{1cm} (1 - \hat{p}_{pool}) \times n_2 \geq 10$$

\vspace{.1in}

3.  Is the independence condition met? Explain your answer.

\vspace{0.4in}

4. Is the success-failure condition met for each group?  Show your work to verify your answer.

\vspace{0.8in}

\newpage

To calculate the standardized statistic we use: 

$$
Z = \frac{\text{point estimate} - \text{null value}}{SE},
$$

where the null standard error is calculated using the pooled proportion of successes:

$$
SE_0(\hat{p}_1-\hat{p}_2)=\sqrt{\hat{p}_{pool}(1-\hat{p}_{pool})\left(\frac{1}{n_1}+\frac{1}{n_2}\right)}.
$$


5. Calculate $SE_0(\hat{p}_1-\hat{p}_2)$.

\vspace{1in}

6. Calculate the standardized statistic.

\vspace{1in}

\begin{figure}

{\centering \includegraphics[width=0.6\linewidth]{10-A15-inference-2cat_test-theory_files/figure-latex/simpleNormal-1} 

}

\caption{A standard normal curve.}(\#fig:simpleNormal)
\end{figure}

7. Mark the value of the standardized statistic on the standard normal distribution above and shade the area to find the p-value.

\vspace{0.1in}

We will use the `pnorm()` function in `R` to find the p-value. Use the provided `R` script file and enter the value of the standardized statistic found in question 6 at `xx` in line 27; highlight and run lines 27--29.


```r
pnorm(xx, # Enter value of standardized statistic
      m=0, s=1 # Using the standard normal mean = 0, sd = 1
      lower.tail=TRUE) # Gives a p-value less than the standardized statistic
```
    

8.  Report the p-value from the `R` output.
\vspace{0.2in}


9.  Interpret the p-value in context of the study.

\vspace{0.5in}

10. Write a conclusion to the research question based on the p-value found.

\vspace{1in}

#### Relative Risk

Another summary statistic that can be calculated for two categorical variables is the relative risk.  The relative risk is calculated as the ratio of the conditional proportions:


$$\text{relative risk} = \frac{\hat{p}_1}{\hat{p}_2}.$$

11.  Calculate the relative risk of helping for those who were assigned to the hurry condition compared to those who were not.

\vspace{.8in}

12.  Interpret the relative risk in context of the problem.

\vspace{1in}


### Take-home messages

1.	When comparing two groups, we are looking at the difference between two parameters.  In the null hypothesis, we assume the two parameters are equal, or that there is no difference between the two proportions.  

2.  We use the same guidelines for the strength of evidence as we did in Activity __.  

3.  The standardized statistic when the response variable is categorical is a Z-score and is compared to the standard normal distribution to find the p-value.  To find the standardized statistic, we take the value of the statistic minus the null value, divided by the null standard error of the statistic.  The standardized statistic measures the number of standard errors the statistic is from the null value. 

4.  If we make the decision to reject the null hypothesis (the p-value is less than the significance level), we could have a possible Type 1 error. A Type 1 error occurs when we reject a true null hypothesis (false positive).

5.  If we make the decision to fail to reject the null hypothesis (the p-value is greater than the significance level), we could have a possible Type 2 error. A Type 2 error occurs when we fail to reject a false null hypothesis (false negative).


### Additional notes

Use this space to summarize your thoughts and take additional notes on this week's activity and material covered.

\newpage
