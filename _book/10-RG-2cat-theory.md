# Inference for Two Categorical Variables: Hypothesis Testing

## Week 10 - Reading Guide: Hypothesis Testing for a Difference in Proportions

### Section 5.4.4 (Theory-based methods for a difference in proportions)  {-}

You may skip the sub-section on "Confidence Interval for $\pi_1 - \pi_2$". This section will be covered next week.

\setstretch{1}

**Videos**  

* 5.4

\setstretch{1.25}

#### Reminders from previous sections {-}

Sample size of group 1: $n_1$

Sample size of group 2: $n_2$

Sample proportion of group 1:  $\hat{p_1}$

Sample proportion of group 2: $\hat{p_2}$

Population proportion of group 1: $\pi_1$

Population proportion of group 2: $\pi_2$

Test statistic/Point estimate: other names for a statistic from a sample; the point estimate is our best guess for the parameter of interest.

Central Limit Theorem: For large sample sizes, the sampling distribution of a sample proportion (or mean) will be approximately normal (bell-shaped and symmetric).

#### Notes {-}

Conditions for the CLT to apply for a difference in proportions

\rgi Independence: 
\rgs

\rgi \rgi Checked by: 
\rgs

\rgi Success-failure condition: 
\rgs

\rgi \rgi Checked by: 
\rgs

#### Formulas {-}

$SD(\hat{p_1} - \hat{p_2})=$
\rgs

Null standard error of the difference in sample proportions:
$SE_0(\hat{p_1} - \hat{p_2})=$
\rgs

Standardized statistic/standardized difference in sample proportions:
$Z=$
\rgs

#### Notation {-}
Overall (pooled) proportion of successes:
\rgs

#### Example: CPR and blood thinner {-}

1. What are the observational units?
\rgs

2. What type of study design was used?  Justify your answer.
\rgs

3. What is the appropriate scope of inference for these data?
\rgs

4. What is the sample difference in proportions presented in this example?  What notation would be used to represent this value?
\rgs

5. What is the parameter (using a difference in proportion) representing in the context of this problem?  What notation would be used to represent this parameter?
\rgs

6. Write the null and the alternative hypotheses in words.
\rgs
\rgs

7. Write the null and the alternative hypotheses in notation.
\rgs

8. Is it valid to use theory-based methods to analyze these data?
\rgs
\rgs

9. Calculate the pooled or overall proportion of successes. What notation would be used to represent this value?
\rgs
\rgs

10. Calculate the null standard error of the difference in sample proportions.
\rgs
\rgs

11.	Calculate the standardized statistic
\rgs
\rgs

12. Interpret the standardized statistic in the context of the problem.
\rgs
\rgs

*Note: a p-value, p-value interpretation, decision, and conclusion for this example can be found in the Reading Guide solutions for Sections 5.4.1--5.4.3.*

### Section 5.5 (Errors, power, and practical importance) {-}

\setstretch{1}

**Videos**  

* 5.5
* Errors_Power

\setstretch{1.25}

#### Reminders from previous sections {-}

Decision: a determination of whether to reject or fail to reject a null hypothesis based on a p-value and a pre-set level of significance.

* If p-value $\leq \alpha$, then reject $H_0$.

* If p-value $> \alpha$, then fail to reject $H_0$.

Significance level ($\alpha$): a threshold used to determine if a p-value provides enough evidence to reject the null hypothesis or not.

\rgi Common levels of $\alpha$ include 0.01, 0.05, and 0.10.

Statistically significant: results are considered statistically significant if the p-value is below the significance level.

#### Vocabulary {-}

Type 1 error: 
\rgs

Type 2 error: 
\rgs

Confirmation bias: 
\rgs

Power: 
\rgs
		
Practical importance: 
\rgs

#### Notes {-}

Fill in the following table with whether the decision was correct or not, and if not, what type of error was made.
\begin{center}
\begin{tabular}{|p{2in}|p{2in}|p{2in}|}
\hline
 & \multicolumn{2}{|c|}{\textbf{Test conclusion (based on data)}} \\ \hline
 \textbf{Truth (unknown)} & Reject null hyp. & Fail to reject null hyp. \\ \hline
 $H_0$ is true && \\ 
   & & \\ 
   & & \\ \hline
 $H_A$ is true ($H_0$ is false)  && \\ 
   & & \\ 
   & & \\ \hline
\end{tabular}
\end{center}

\rgs

How are the significance level and type I error rate related?
\rgs

How are the significance level and type II error rate related?
\rgs


After collecting data, a researcher decides to change from a two-sided test to a one-sided test.  Why is this a bad idea?

1. It ____________ (increases/decreases) the chance of a type I error.

2. This can result in ________________________.
\rgs

How are power and type I error rate related?
\rgs

How are power and type II error rate related?
\rgs

How can we increase the power of a test?

1. ________ (Increase/Decrease) the significance level
\rgs

2. ________ (Increase/Decrease) the sample size
\rgs

3. Change from a ___ (one/two)-sided to a ___ (one/two)-sided test
\rgs

4. Have a ________ (larger/smaller) standard deviation of the statistic
\rgs

5. Have the alternative parameter value _______ (closer/farther) from the null value
\rgs

Results are likely to be statistically significant (but may not be practically important) if the sample size is __________(large/small).
\rgs

Results are unlikely to be statistically significant (but may be practically important) if the sample size is __________(large/small).
\rgs

#### Examples: {-} 

1. In the Gender Discrimination study in the textbook and presented as an example in Reading Guide 5.4.1--5.4.2,

\rgi a. What was the p-value of the test?
\rgs

\rgi b.	At the 5% significance level, what decision would you make?
\rgs

\rgi c. What type of error might have occurred in these data?
\rgs

\rgi d. Interpret that error in the context of the problem.
\rgs
\rgs

2. In the Opportunity Cost study in the textbook and presented as an example in the reading guide for sections 5.4.1--5.4.2,

\rgi a. What was the p-value of the test?
\rgs

\rgi b. At the 5% significance level, what decision would you make?
\rgs

\rgi c. What type of error might have occurred in these data?
\rgs

\rgi d. Interpret that error in the context of the problem.
\rgs
\rgs

3. In the CPR and Blood Thinners study in the textbook and presented as an example in the reading guide for sections 5.4.1--5.4.2,

\rgi a. What was the p-value of the test?
\rgs

\rgi b. At the 5% significance level, what decision would you make?
\rgs

\rgi c. What type of error might have occurred in these data?
\rgs

\rgi d. Interpret that error in the context of the problem.
\rgs
\rgs

### Section 5.4.4 (Theory-based methods for a difference in proportions)  {-}

\setstretch{1}

In section 5.4.4, read only the sub-section on "Confidence interval for $\pi_1 - \pi_2$". The other sections were covered last week.

**Videos**  

* 5.4

\setstretch{1.25}

#### Reminders from previous sections {-}

Central Limit Theorem: For large sample sizes, the sampling distribution of a sample proportion (or mean) will be approximately normal (bell-shaped and symmetric).

#### Notes {-}

Conditions for the CLT to apply for two categorical variables

\rgi Independence: 
\rgs

\rgi \rgi Checked by: 
\rgs

\rgi Success-failure condition: 
\rgs

\rgi \rgi Checked by: 
\rgs

#### Formulas {-}

$SD(\hat{p_1} - \hat{p_2})=$
\rgs

Standard error of the difference in sample proportions when we do not assume the null hypothesis is true:
$SE(\hat{p_1} - \hat{p_2})=$
\rgs

Theory-based confidence interval for a difference in proportions: 
\rgs

Margin of error of a confidence interval for a difference in proportions: 
\rgs


#### Example: CPR and blood thinner {-}

1. What is the sample difference in proportions presented in this example?  What notation would be used to represent this value?
\rgs

2. What is the parameter (using a difference in proportion) representing in the context of this problem?  What notation would be used to represent this parameter?
\rgs
\rgs

3. Calculate the standard error of the difference in sample proportions without assuming a null hypothesis.
\rgs
\rgs

4. Calculate the 90% confidence interval using $z^*=1.65$ as the multiplier.
\rgs
\rgs

*Note: A confidence interval interpretation and confidence level interpretation for this example can be found in the Reading Guide solutions for Sections 5.4.1--5.4.3.*

\newpage
