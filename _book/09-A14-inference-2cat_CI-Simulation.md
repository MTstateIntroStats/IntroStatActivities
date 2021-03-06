## Activity 9b:  The Good Samaritan --- Estimation

\setstretch{1}

### Learning objectives

* Identify the parameter of interest for a difference in proportions.

* Create and interpret a simulation-based confidence interval for a difference in proportions.

* 

### Terminology review
In this week's activity, we will use theory-based methods to estimate the difference in two proportions. Some terms covered in this activity are:

* Standard normal distribution

* Independence and success-failure conditions

To review these concepts, see Chapter 5 in your textbook.

### The Good Samaritan

In the last activity, we found a small p-value for the hypothesis test for a difference in proportions.  There was very strong evidence that those in a hurry will be less likely to help people in need.  In today's activity, we will estimate the true difference in proportion of people who will help others for those in the hurry condition and those not in the hurry condition by finding a confidence interval.  

Researchers at the Princeton University wanted to investigate influences on behavior.  The researchers randomly select 67 students from the Princeton Theological Seminary to participate in a study.  Only 47 students chose to participate in the study, and the data below includes 40 of those students (7 students were removed from the study for various reasons).  As all participants were theology majors planning a career as a preacher, the expectation was that all would have a similar disposition when it comes to helping behavior.  Each student was then shown a 5-minute presentation on the Good Samaritan, a parable in the Bible which emphasizes the importance of helping others.  After the presentation, the students were told they needed to give a talk on the Good Samaritan parable at a building across campus.  Half the students were told they were late for the presentation; the other half told they could take their time getting across campus (the condition was randomly assigned).  On the way between buildings, an actor pretending to be a homeless person in distress asked the student for help.  The researchers recorded whether the student helped the actor or not.  The results of the study are shown in the table below.  Do these data provide evidence that those in a hurry will be less likely to help people in need in this situation?  Use the order of subtraction hurry – no hurry.

|                    | Hurry Condition | No Hurry Condition | Total |
|--------------------|-----------------|--------------------|-------|
| Helped Actor       |        2        |         11         |   13  |
| Did Not Help Actor |        18       |          9         |   27  |
| Total              |        20       |         20         |   40  |

#### Vocabulary review. {-}

1.  Report the point estimate for this study.  

\vspace{0.4in}


Use the following code to create a segmented bar plot of those who helped others for those in the hurry condition and those in the no hurry condition.


\begin{center}\includegraphics[width=0.7\linewidth]{09-A14-inference-2cat_CI-Simulation_files/figure-latex/unnamed-chunk-1-1} \end{center}

2.  Sketch the segmented bar plot created here.  

\vspace{1.5in}

3. Based on the segmented bar plot, does there appear to be an association between the condition assigned and the behavior?  Explain.

\vspace{1in}

4.  Write out the conclusion you made in Activity 14.

\vspace{0.8in}

5.  Do you expect the null value to be in the 99\% confidence interval?  Explain your answer.

\vspace{0.8in}

#### Use statistical analysis methods to draw inferences from the data {-}

6.  Write the parameter of interest in context of the study. Use proper notation.

\vspace{1in}

We will use the `two_proportion_bootstrap_CI()` function in `R` (in the `catstats` package) to simulate the bootstrap distribution of differences in sample proportions and calculate a confidence interval. We will need to enter the response variable name and the explanatory variable name for the formula, the data set name (identified above as `samaritan`), the outcome for the explanatory variable that is first in subtraction, number of repetitions, the outcome for the response variable that is a success (what the numerator counts when calculating a sample proportion), and the confidence level as a decimal.

The response variable name is `Behavior` and the explanatory variable name is `Condition`.

7. What values should be entered for each of the following into the simulation to create a 99\% confidence interval?

\vspace{.5mm}
* First in subtraction (What is the outcome for the explanatory variable that is used as first in the order of subtraction? `"Hurry"` or `"No hurry"`):

\vspace{.2in}
* Response value numerator (What is the outcome for the response variable that is considered a success? `"Help"` or `"No help"`):

\vspace{.2in}
* Number of repetitions:

\vspace{.2in}
* Confidence level (entered as a decimal):

\vspace{.2in}

Using the `R` script file for this activity, enter your answers for question 7 in place of the `xx`'s to produce the bootstrap distribution with 1000 simulations; highlight and run lines 1--22.


```r
two_proportion_bootstrap_CI(formula = Behavior ~ Condition, 
        data=samaritan, # Name of data set
        first_in_subtraction = "Hurry", # Order of subtraction: enter the name of Group 1
        response_value_numerator = "Help", # Define which outcome is a success 
        number_repetitions = 1000, # Always use a minimum of 1000 repetitions
        confidence_level = 0.99) # Enter the level of confidence as a decimal
```
8.  Where is the bootstrap distribution centered?  Explain why.

\vspace{0.8in}

9. Report the bootstrap 99\% confidence interval. 

\vspace{0.4in}

10. What percentile of the bootstrap distribution does the upper value of the confidence interval represent?

\vspace{0.3in}

11. Interpret the 99\% confidence interval in context of the problem.

\vspace{1in}

12.  What conclusion to the research question can be made based on the 99\% confidence interval?

\vspace{0.8in}

13.  Is the null value in the 99\% confidence interval? 

\vspace{0.8in}

#### Types of errors {-}

Recall from a previous activity, hypothesis tests are not flawless. In a hypothesis test, there are two competing hypotheses: the null and alternative. We make a decision about which might be true, but we may choose incorrectly.  

<!-- |       |            | Test Conclusion |                     | -->
<!-- |       |            | Reject $H_0$    | Fail to reject $H_0$| -->
<!-- |:-----:|:----------:|-----------------|---------------------| -->
<!-- | Truth | $H_0$ true |  good decision  |  Type 1 Error       | -->
<!-- |       | $H_A$ true |  Type 2 Error   |  good decision      | -->

\begin{table}
\caption{Four different possible scenarios for hypothesis test decisions.}
\centering
\begin{tabular}[h]{ll|cc}
\hline
 & &  \multicolumn{2}{c}{\textbf{Test conclusion}} \\
 &  & \multicolumn{1}{c}{Fail to reject $H_0$} & \multicolumn{1}{c}{Reject $H_0$}\\
\hline
 & $H_0$ true & Good decision & Type 1 Error\\
\hline
\textbf{Truth} & $H_A$ true & Type 2 Error & Good decision\\
\hline
\end{tabular}
\label{tab:errors}
\end{table}

Shown in Table \@ref(tab:errors), a **Type 1 Error** happens when we reject the null hypothesis when $H_0$ is actually true. A **Type 2 Error** happens when we fail to reject the null hypothesis when the alternative is actually true.

14.  Using a significance level of 0.1, based on the question 11, what decision do you make in regards to the null hypothesis?

\vspace{0.3in}

15. What type of error could we have made?

\vspace{0.3in}

16.  Write this error in context of the problem.

**Power questions?**

### Take-home messages

1. Simulation-based methods and theory-based methods should give the same results for a study *if the validity conditions are met*.  For both methods, observational units need to be independent. To use theory-based methods, additionally, the success-failure condition must be met. Check the validity conditions for each type of test to determine if theory-based methods can be used.

2. When calculating the standard error for the difference in sample proportions when doing a hypothesis test, we use the pooled proportion of successes, the best estimate for calculating the variability *under the assumption the null hypothesis is true*.  For a confidence interval, we are not assuming a null hypothesis, so we use the values of the two conditional proportions to calculate the standard error.  Make note of the difference in these two formulas. 

3.  In addition to estimating the difference in proportions for two categorical variables we can also find the relative risk, the ratio of conditional proportions.  

4.  Increasing sample size will result in less sample-to-sample variability in statistics, which will result in a smaller standard error, and thus a narrower confidence interval.  

5. To create one simulated sample on the bootstrap distribution for a difference in sample proportions, label $n_1 + n_2$ cards with the outcomes for the original responses.  Keep groups separate and randomly draw with replacement $n_1$  times from group 1 and $n_2$ times from group 2.  Calculate and plot the resampled difference in the proportion of successes. 


### Additional notes

Use this space to summarize your thoughts and take additional notes on this week's activity and material covered.

\newpage
