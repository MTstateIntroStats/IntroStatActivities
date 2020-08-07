# Statistical Investigations for Paired Data

## Learning Outcomes

* Given a research question, construct the null and alternative hypotheses
  in words and using appropriate statistical symbols
  
* Describe and perform simulation-based hypothesis 

* Interpret and evaluate a p-value

* Construct and interpret a theory-based confidence interval

* Use a confidence interval to determine the conclusion of a hypothesis test

## Mean Difference in Heart Rates for Jumping Jacks and Bicycle Kicks
Which exercise, jumping jacks or bicycle kicks will raise your heart rate more? Students in an introductory statistics class were asked to participate in an experiment to answer this question.  Each student flipped a coin to determine which exercise to complete first.  If the coin landed on heads the student would do jumping jacks for 30 seconds and then measure their heart rate.  After a 2 minute break the student would do bicycle kicks for 30 seconds and then record their heart rate.  If the coin landed on tails the student would complete bicycle kicks first followed by jumping jacks using the same times as above. 

## Review

\begin{center}\includegraphics[width=0.7\linewidth]{08-paired_files/figure-latex/unnamed-chunk-1-1} \end{center}


```
#>  min Q1 median Q3 max     mean       sd  n missing
#>  -16 -4      8 15  57 7.604651 15.91666 43       0
```

1. What is the sample size? 

\vspace{0.5in}

2.  Identify the variables in this study.  What role do each have?

\vspace{1in}

3. Why is this treated as a paired study design and not two independent samples?

\vspace{1in}

4.  What is the purpose of randomizing the order of jumping jacks and bicycle kicks before measuring heart rates?

\vspace{1in}

## Ask a Research Question

5. What are the two competing possibilities to run a hypothesis test?

\vspace{1in}

6. Write the null hypothesis in words.

\vspace{1in}

7. What is the research question?

\vspace{1in}

8. Write the alternative hypothesis in notation.

\vspace{1in}


## Summarize and Visualize the Data 

9. Report the summary statistic for the data.  

\vspace{0.5in}

10. What notation is used for the value in question 9? 

\vspace{0.5in}


## Use statistical inferential methods to draw inferences from the data


To simulate the null distribution we will use a bootstrapping method - sampling with replacement from the data set.  Before bootstrapping we will need to shift the each data point by the difference $\mu_0 - \bar{x}$.  This will ensure that the simulated null distribution will be centered at the null value.  

11. Calculate the difference $\mu_0 - \bar{x}$.  Will we need to shift the data up or down?

\vspace{1in}


**Add simulation here**


12. Explain why the null distribution is centered at zero. 

\vspace{1in}

13. What proportion of samples are beyond the sample mean difference in heart beats for jumping jacks minus bicycle kicks?

\vspace{1in}


## Communicate the results and answer the research question.

14. Write out the parameter of interest in context of the study.

\vspace{1in}

To calculate a confidence interval to estimate the mean difference in heart rates, we will use this equation:

$\bar{x}_d \pm t^*SE(\bar{x}_d)$, where $SE(\bar{x}_d) = \sqrt(\frac{\bar{x}_d}{n_d})$

To find the $t^*$ multiplier for a 95% confidence interval we will find the value in the t-distribution that represents the endpoints for the middle 95% of the data.


```
#> [1] 2.018082
```

15.  Calculate the $SE(\bar{x}_d)$. 

\vspace{1in}

16. Calculate a 95% confidence interval for the parameter of interest.

\vspace{1in}

17. Interpret the 95% confidence interval in context of the problem.

\vspace{1in}

18.  Based off your p-value and confidence interval, write a conclusion.

\vspace{1in}

## Revisit and Look Forward

Suppose we had a sample of 90 students instead of 43 resulting in the same summary statistic.

19. Would this new data provide more or less evidence against the null hypothesis?  Explain your answer.

\vspace{1in}

20. Would this result in a wider or narrower confidence interval?

\vspace{1in}
