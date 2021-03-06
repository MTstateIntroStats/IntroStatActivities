# Inference for Two Categorical Variables: Hypothesis Testing

## Reading Guide: Hypothesis Testing for a Difference in Proportions

### Sections 5.4.1 and 5.4.2 (Simulation tests for a difference in proportions; Two-sided hypotheses)  {-}

**Videos**  

* 5.4
* TwoPropSim

\setstretch{1.25}

#### Reminders from previous sections {-}

$n$ = sample size

$\hat{p}$ = sample proportion

$\pi$ = population proportion

General steps of a hypothesis test:

1. Frame the research question in terms of hypotheses.

2. Collect and summarize data using a test statistic.
	
3. Assume the null hypothesis is true, and simulate or mathematically model a null distribution for the test statistic.

4. Compare the observed test (standardized) statistic to the null distribution to calculate a p-value.

5. Make a conclusion based on the p-value and write the conclusion in context.

Parameter: a value summarizing a variable(s) for a population.

Statistic: a value summarizing a variable(s) for a sample.

Sampling distribution: plot of statistics from 1000s of samples of the same size taken from the same population.

Standard deviation of a statistic: the variability of statistics from 1000s of samples; how far, on average, each statistic is from the true value of the parameter.

Standard error of a statistic: estimated standard deviation of a statistic.

Hypothesis test: a process to determine how strong the evidence of an effect is.
		
\rgi Also called a ‘significance test’.

Simulation-based method: Simulate lots of samples of size $n$ under assumption of the null hypothesis, then find the proportion of the simulations that are at least as extreme as the observed sample statistic.

Theory-based method: Develop a mathematical model for the sampling distribution of the statistic under the null hypothesis and use the model to calculate the probability of the observed sample statistic (or one more extreme) occurring.

Null hypothesis ($H_0$): the skeptical perspective; no difference; no change; no effect; random chance; what the researcher hopes to prove is **wrong**.

Alternative hypothesis ($H_A$): the new perspective; a difference/increase/decrease; an effect; not random chance; what the researcher hopes to prove is **correct**.

Null value: the value of the parameter when we assume the null hypothesis is true (labeled as $parameter_0$).

Null distribution:  the simulated or modeled distribution of statistics (sampling distribution) we would expect to occur if the null hypothesis is true.

P-value: probability of seeing the observed sample data, or something more extreme, assuming the null hypothesis is true.

$\implies$ Lower the p-value the stronger the evidence AGAINST the null hypothesis and FOR the alternative hypothesis.

Decision: a determination of whether to 'reject' or 'fail to reject' a null hypothesis based on a p-value and a pre-set level of significance.

Significance level ($\alpha$): a threshold used to determine if a p-value provides enough evidence to reject the null hypothesis or not.

\rgi Common levels of $\alpha$ include 0.01, 0.05, and 0.10.

Statistically significant: results are considered statistically significant if the p-value is below the significance level.


#### Vocabulary {-}

Randomization test: 
\rgs

Relative risk: 
\rgs

One-sided hypothesis test: 
\rgs

Two-sided hypothesis test: 
\rgs

#### Notes {-}

In a randomization test involving two categorical variables, how many cards will you need and how will the cards be labeled?
\rgs

Why, in the randomization test, are the cards all shuffled together and randomly dealt into two new groups?
\rgs

After shuffling, how many cards are dealt into each pile?
\rgs

Interpreting relative risk ($RR = \frac{\hat{p_1}}{\hat{p_2}}$)

\rgi The proportion of success in group 1 is ______ times the proportion of success in group 2.

\rgi The proportion of success in group 1 is ______ % higher/lower than in group 2.

Write the null hypothesis in notation for a test of relative risk.
\rgs

How does the p-value in a two-sided test compare to the p-value in a one-sided test?
\rgs

#### Formulas {-}

Relative risk = 
\rgs

#### Notation {-}
Sample size of group 1: 
\rgs

Sample size of group 2: 
\rgs

Sample proportion of group 1: 
\rgs

Sample proportion of group 2: 
\rgs

Population proportion of group 1: 
\rgs

Population proportion of group 2: 
\rgs

#### Example: Gender discrimination {-}
1. What is the research question?
\rgs

2. What are the observational units?
\rgs

3. What type of study design was used?  Justify your answer.
\rgs

4. What is the appropriate scope of inference for these data?
\rgs

5. What is the sample statistic presented in this example?  What notation would be used to represent this value?
\rgs

6. What is the parameter representing in the context of this problem?  What notation would be used to represent this parameter?
\rgs
\rgs

7. Write the null and the alternative hypotheses in words.
\rgs
\rgs

8. Write the null and the alternative hypotheses in notation.
\rgs

9. How could we use cards to simulate **ome** sample *which assumes the null hypothesis is true*?  How many blue cards --- to represent what?  How many red cards --- to represent what?  What would we do with the cards?  What would you record once you have a simulated sample?
\rgs
\rgs
\rgs

10. How can we calculate a p-value from the simulated null distribution for this example?
\rgs
\rgs

11. What was the p-value of the test? 
\rgs

12. At the 5% significance level, what decision would you make?
\rgs

13. What conclusion should the researcher make?
\rgs
\rgs

14. Are the results in this example statistically significant?  Justify your answer.
\rgs


#### Example: Opportunity cost {-}
1. What is the research question?
\rgs

2. What are the observational units?
\rgs

3. What type of study design was used?  Justify your answer.
\rgs

4. What is the appropriate scope of inference for these data?
\rgs

5. What is the sample statistic presented in this example?  What notation would be used to represent this value?
\rgs

6. What is the parameter representing in the context of this problem?  What notation would be used to represent this parameter?
\rgs
\rgs

7. Write the null and the alternative hypotheses in words.
\rgs
\rgs

8. Write the null and the alternative hypotheses in notation.
\rgs

9. How could we use cards to simulate **one** sample *which assumes the null hypothesis is true*? How many blue cards --- to represent what?  How many red cards --- to represent what?  What would we do with the cards?  What would you record once you have a simulated sample?
\rgs
\rgs
\rgs

10. How can we calculate a p-value from the simulated null distribution for this example?
\rgs
\rgs

11. What was the p-value of the test? 
\rgs

12. Interpret the p-value in the context of the problem.
\rgs
\rgs

13. At the 5% significance level, what decision would you make?
\rgs

14. What conclusion should the researcher make?
\rgs

15. Are the results in this example statistically significant?  Justify your answer.
\rgs

#### Example: CPR and blood thinner {-}

1. What is the research question?
\rgs

2. What are the observational units?
\rgs

3. What type of study design was used?  Justify your answer.
\rgs

4. What is the appropriate scope of inference for these data?
\rgs

5. What is the sample difference in proportions presented in this example?  What notation would be used to represent this value?
\rgs

6. What is the sample relative risk?  Interpret the value in the context of the study.
\rgs
\rgs

7. What is the parameter (using a difference in proportion) representing in the context of this problem?  What notation would be used to represent this parameter?
\rgs
\rgs

8. Write the null and the alternative hypotheses in words.
\rgs
\rgs

9. Write the null and the alternative hypotheses in notation.
\rgs

10. How could we use cards to simulate **one** sample *which assumes the null hypothesis is true*?  How many blue cards --- to represent what?  How many red cards --- to represent what?  What would we do with the cards?  What would you record once you have a simulated sample?
\rgs
\rgs
\rgs

11. How can we calculate a p-value from the simulated null distribution for this example?
\rgs
\rgs

12. What was the p-value of the test? 
\rgs

13. Interpret the p-value in the context of the problem.
\rgs
\rgs

14. At the 5% significance level, what decision would you make?
\rgs

15. What conclusion should the researcher make?
\rgs
\rgs

16. Are the results in this example statistically significant?  Justify your answer.
\rgs


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


\newpage

## Activity:  Winter Sports Helmet Use and Head Injuries --- Testing

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
In "Helmet Use and Risk of Head Injuries in Alpine Skiers and Snowboarders" by Sullheim et. al., in the *Journal of the American Medical Association*, Vol. 295, No. 8 (2006), we can see the summary results from a random sample of 3562 skiers and snowboarders involved in accidents in the two-way table below. Is there evidence that safety helmet use is associated with a reduced risk of head injury for skiers and snowboarders? 

|                | Helmet Use | No Helmet Use | Total |
|:--------------:|:----------:|:-------------:|:-----:|
| Head Injury    |     96     |      480      |  576  |
| No Head Injury |     656    |      2330     |  2986 |
| Total          |     752    |      2810     |  3562 |

\newpage

These counts can be found in `R` by using the `count()` function:

```r
# Read data set in
injury <- read.csv("https://math.montana.edu/courses/s216/data/HeadInjuries.csv") 
injury <- # Write over original data with the following
  injury %>% # Pipe data set into
  mutate(Helmet <- factor(Helmet),
         Outcome <- factor(Outcome)) # Convert to factors

injury %>% group_by(Helmet) %>% count(Outcome)
```

```
#> # A tibble: 4 x 3
#> # Groups:   Helmet [2]
#>   Helmet Outcome            n
#>   <chr>  <chr>          <int>
#> 1 No     Head Injury      480
#> 2 No     No Head Injury  2330
#> 3 Yes    Head Injury       96
#> 4 Yes    No Head Injury   656
```

#### Vocabulary review. Complete Q1--Q4 before class. {-}

1.  What is the name of the explanatory variable in the `R` output? What are its categories?

\vspace{0.2in}

2. What is the response variable in the `R` output? What are its categories?

\vspace{0.2in}

\setstretch{1.5}
3. Fill in the blanks with one answer from each set of parentheses: This is an  
________________ (experiment/observational study) because  
______________ (helmet use/head injury) _______ (was/was not)  
randomly ____________ (assigned/selected).

\vspace{0.1in}

4.  Put an X in the box that represents the appropriate scope of inference for this study.

|                    |                  |       Study Type      |                     |
|:------------------:|:----------------:|:---------------------:|---------------------|
|                    |                  | Randomized Experiment | Observational Study |
| Selection of Cases | Random Sample    |                       |                     |
|                    | No Random Sample |                       |                     |
\setstretch{1}


#### Ask a research question {-}

The research question as stated above is: Is there evidence that safety helmet use is associated with a reduced risk of head injury for skiers and snowboarders? In order to set up our hypotheses, we need to express this research question in terms of parameters. 
Remember, we define the parameter for a single categorical variable as the true proportion of observational units that are labeled as a "success" in the response variable.  

\newpage

5. Write the two parameters of interest for this study.  Let 1 = skier/snowboarder wore helmet, 2 = skier/snowboarder did not wear helmet. 
\vspace{1mm}

   $\pi_1$ --- 
\vspace{0.5in}

   $\pi_2$ ---
\vspace{0.5in}

When comparing two groups, we assume the two parameters are equal in the null hypothesis---there is no association between the variables.

6.  Write the null hypothesis out in words using your answers to question 5.

\vspace{0.8in}


7. Based on the research question, fill in the appropriate sign for the alternative hypothesis ($<$, $>$, or $\neq$):
\vspace{0.1in}

|           $H_A: \pi_1 -\pi_2$ __________ 0


 
#### Summarize and visualize the data {-}

8. Using the two-way table above, calculate the conditional proportion of helmet-wearing skiers/snowboarders that sustained a head injury.

\vspace{.3in}

9. Using the two-way table above, calculate the conditional proportion of non-helmet-wearing skiers/snowboarders that sustained a head injury.

\vspace{.3in}


\begin{center}\includegraphics[width=0.7\linewidth]{08-inference-2cat_test_files/figure-latex/unnamed-chunk-2-1} \end{center}

10.  Fill in the blanks on the segmented bar plot on the previous page with the appropriate variable names and categories to complete the segmented bar plot comparing the proportion of head injuries between those who wear helmets and those who do not wear helmets.  *Hint*: Use the conditional proportions from questions 8 and 9.

\vspace{1mm}

11.  Based on the segmented bar plot, Does there appear to be an association between helmet use and head injury?  Explain using the plot.

\vspace{0.7in}

12.  Calculate the summary statistic for this study.  Use helmet use (`Yes`) minus no helmet use (`No`) as the order of subtraction.

\vspace{0.4in}


13. What is the notation used for the value calculated in question 12?

\vspace{0.1in}


#### Use statistical analysis methods to draw inferences from the data {-}

To test the null hypothesis, we could use simulation-based methods as we did with a single categorical variable in class. In this in-class activity, we will focus on theory-based methods.  Like with a single proportion, the sampling distribution of a difference in sample proportions can be mathematically modeled using the normal distribution if certain conditions are met.

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

14.  Is the independence condition met? Explain your answer.

\vspace{0.4in}

15. Is the success-failure condition met for each group?  Show your work to verify your answer.

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


16. Calculate $SE_0(\hat{p}_1-\hat{p}_2)$.

\vspace{1in}

17. Calculate the standardized statistic.

\vspace{1in}

We will use the `pnorm()` function in `R` to find the p-value. Use the provided `R` script file and enter the value of the standardized statistic found in question 17 at `xx` in line 27; highlight and run lines 27--29.


```r
pnorm(xx, # Enter value of standardized statistic
      m=0, s=1 # Using the standard normal mean = 0, sd = 1
      lower.tail=TRUE) # Gives a p-value less than the standardized statistic
```
    

18.  Report the p-value from the `R` output.
\vspace{0.2in}

19.  Interpret the p-value in context of the study.

\vspace{1in}

20.  How much evidence does the p-value provide against the null hypothesis? *Hint*: Refer to the guidelines given in Activity 6.

\vspace{0.4in}

21.  Write a conclusion to the test. 

\vspace{1in}


#### Types of errors {-}

Hypothesis tests are not flawless. In a hypothesis test, there are two competing hypotheses: the null and alternative. We make a decision about which might be true, but we may choose incorrectly.  

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

22.  Using a significance level of 0.05, based on the p-value found in question 18, what decision do you make in regards to the null hypothesis?

\vspace{0.3in}

23. What type of error could we have made?

\vspace{0.3in}

24.  Write this error in context of the problem.

\vspace{0.8in}

25. Write a paragraph summarizing the results of the study as if writing a press release.  Be sure to describe:

* Summary statistic

* Test statistic and interpretation

* P-value and interpretation

* Conclusion (written to answer the research question)

* Scope of inference

\vspace{2in}



\newpage
### Out-of-class activity

The remaining questions cover simulation-based methods for testing two categorical variables. Use Section 5.4.1 in the textbook and the TwoPropSim video to complete the following questions.  

1.  First, let's think about how one simulation would be created on the null distribution using cards.  

    How many cards would you need?
\vspace{0.1in}

    What would be written on each card?

\vspace{0.5in}

2. Next, we would mix the cards together and shuffle into two piles.  How many cards would be in each pile?  What would each pile represent?

\vspace{0.8in}

3. Once we have one simulated sample, what would we calculate and plot on the null distribution?  *Hint*: What statistic are we calculating from the data?

\vspace{0.8in}

To create the null distribution of differences in sample proportions, we will use the `two_proportion_test()` function in `R` (in the `catstats` package).  We will need to enter the response variable name and the explanatory variable name for the formula, the data set name (identified above as `injury`), the outcome for the explanatory variable that is first in subtraction, number of repetitions, the outcome for the response variable that is a success (what the numerator counts when calculating a sample proportion), and the direction of the alternative hypothesis.

The response variable name is `Outcome` and the explanatory variable name is `Helmet`.

4.  What inputs should be entered for each of the following to create the simulation?

\vspace{.2in}
* First in subtraction (What is the outcome for the explanatory variable that is used as first in the order of subtraction? `"Yes"` or `"No"`):

\vspace{.2in}
* Number of repetitions:
    
\vspace{.2in}
* Response value numerator (What is the outcome for the response variable that is considered a success? `"Head Injury"` or `"No Head Injury"`):

\vspace{.2in}
* As extreme as (enter the value for the sample difference in proportions):
    
\vspace{.2in}
* Direction (`"greater"`, `"less"`, or `"two-sided"`):

\vspace{.2in}

Using the `R` script file for this activity, enter your answers for question 4 in place of the `xx`'s to produce the null distribution with 1000 simulations; highlight and run lines 1--12 and then 33--39.


```r
two_proportion_test(formula = Outcome ~ Helmet, # response ~ explanatory
    data= injury, # Name of data set
    first_in_subtraction = "xx", # Order of subtraction: enter the name of Group 1
    number_repetitions = 1000, # Always use a minimum of 1000 repetitions
    response_value_numerator = "xx", # Define which outcome is a success 
    as_extreme_as = xx, # Calculated observed statistic (difference in sample proportions)
    direction="xx") # Alternative hypothesis direction ("greater","less","two-sided")
```

5.  Sketch the null distribution created here.

\vspace{1.5in}


6. What value is the null distribution centered around?  Explain why this makes sense.

\vspace{.8in}

7.  What is the p-value? *Remember*: This is the value given at the bottom of the null distribution.

\vspace{0.2in}

8.  Is the p-value found in question 7 for the out-of-class activity similar to the p-value found using the theory-based test?  Explain why you would expect this to be true.

\vspace{.8in}

### Take-home messages

1.	When comparing two groups, we are looking at the difference between two parameters.  In the null hypothesis, we assume the two parameters are equal, or that there is no difference between the two proportions.  

2.  We use the same guidelines for the strength of evidence as we did in Activity 6.  

3.  The standardized statistic when the response variable is categorical is a Z-score and is compared to the standard normal distribution to find the p-value.  To find the standardized statistic, we take the value of the statistic minus the null value, divided by the null standard error of the statistic.  The standardized statistic measures the number of standard errors the statistic is from the null value. 

4.  If we make the decision to reject the null hypothesis (the p-value is less than the significance level), we could have a possible Type 1 error. A Type 1 error occurs when we reject a true null hypothesis (false positive).

5.  If we make the decision to fail to reject the null hypothesis (the p-value is greater than the significance level), we could have a possible Type 2 error. A Type 2 error occurs when we fail to reject a false null hypothesis (false negative).

6. To create one simulated sample on the null distribution for a difference in sample proportions, label $n_1 + n_2$ cards with the response variable outcomes from the original data. Mix cards together and shuffle into two new groups of sizes $n_1$ and $n_2$, representing the explanatory variable groups. Calculate and plot the difference in proportion of successes.


### Additional notes

Use this space to summarize your thoughts and take additional notes on this week's activity and material covered.
