## Activity 8A:  The Good Samaritan --- Simulation-based Hypothesis Test

\setstretch{1}

### Learning outcomes

* Given a research question involving two categorical variables, construct the null and alternative hypotheses
  in words and using appropriate statistical symbols.
  
* Describe and perform a simulation-based hypothesis test for a difference in proportions.

* Interpret and evaluate a p-value for a simulation-based hypothesis test for a difference in proportions.

### Terminology review
In today's activity, we will use simulation-based methods to analyze two categorical variables. Some terms covered in this activity are:

* Conditional proportion

* Null hypothesis

* Alternative hypothesis

To review these concepts, see Chapter 15 in your textbook.


### The Good Samaritan

Researchers at the Princeton University wanted to investigate influences on behavior [@darley1973].  The researchers randomly selected 67 students from the Princeton Theological Seminary to participate in a study.  Only 47 students chose to participate in the study, and the data below includes 40 of those students (7 students were removed from the study for various reasons).  As all participants were theology majors planning a career as a preacher, the expectation was that all would have a similar disposition when it comes to helping behavior.  Each student was then shown a 5-minute presentation on the Good Samaritan, a parable in the Bible which emphasizes the importance of helping others.  After the presentation, the students were told they needed to give a talk on the Good Samaritan parable at a building across campus.  Half the students were told they were late for the presentation; the other half told they could take their time getting across campus (the condition was randomly assigned).  On the way between buildings, an actor pretending to be a homeless person in distress asked the student for help.  The researchers recorded whether the student helped the actor or not.  The results of the study are shown in the table below.  Do these data provide evidence that those in a hurry will be less likely to help people in need in this situation?  Use the order of subtraction hurry – no hurry.

|                    | Hurry Condition | No Hurry Condition | Total |
|--------------------|-----------------|--------------------|-------|
| Helped Actor       |        2        |         11         |   13  |
| Did Not Help Actor |        18       |          9         |   27  |
| Total              |        20       |         20         |   40  |


\newpage

These counts can be found in R by using the `count()` function:

```r
# Read data set in
good <- read.csv("https://math.montana.edu/courses/s216/data/goodsam.csv") 
good %>% group_by(Condition) %>% count(Behavior)
```

```
#> # A tibble: 4 x 3
#> # Groups:   Condition [2]
#>   Condition Behavior     n
#>   <chr>     <chr>    <int>
#> 1 Hurry     Help         2
#> 2 Hurry     No help     18
#> 3 No hurry  Help        11
#> 4 No hurry  No help      9
```

#### Vocabulary review {-}

1.  What is the name of the explanatory variable as it is written in the R output? What are its categories?

\vspace{0.2in}

2. What is the response variable in the R output? What are its categories?

\vspace{0.2in}

\setstretch{1.5}
3. Fill in the blanks with one answer from each set of parentheses: This is an  
________________ (experiment/observational study) because  
______________ (hurry or no hurry/help or no help) _______ (was/was not)  
randomly ____________ (assigned/selected).

\vspace{0.1in}

4.  Put an X in the box that represents the appropriate scope of inference for this study.

\begin{center}
\begin{tabular}{|c|c|c|c|}\hline
& & Study Type & \\ \hline
& & Randomized Experiment & Observational Study \\ \hline
Selection of Cases & Random Sample &  &  \\ \hline
& No Random Sample & & \\ \hline
\end{tabular}
\end{center}

\setstretch{1}


#### Ask a research question {-}

The research question as stated above is: Do these data provide evidence that those in a hurry will be less likely to help people in need in this situation? In order to set up our hypotheses, we need to express this research question in terms of parameters. 

Remember, we define the parameter for a single categorical variable as the true proportion of observational units that are labeled as a "success" in the response variable.  

\newpage

5. Write the two parameters of interest for this study.  

\vspace{1mm}

\rgi $\pi_{\text{hurry}}$ --- 
\vspace{0.5in}

\rgi $\pi_{\text{no hurry}}$ ---
\vspace{0.5in}

When comparing two groups, we assume the two parameters are equal in the null hypothesis---there is no association between the variables.

6.  Write the null hypothesis out in words using your answers to question 5.

\vspace{0.8in}


7. Based on the research question, fill in the appropriate sign for the alternative hypothesis ($<$, $>$, or $\neq$):
\vspace{0.1in}

|           $H_A: \pi_{\text{hurry}} -\pi_{\text{no hurry}}$ __________ 0


 
#### Summarize and visualize the data {-}

8. Using the two-way table given in the introduction, calculate the conditional proportion of students in the hurry condition who helped the actor.

\vspace{.3in}

9. Using the two-way table given in the introduction, calculate the conditional proportion of students in the no hurry condition who helped the actor.

\vspace{.3in}

10.  Calculate the summary statistic (difference in sample proportion) for this study.  Use Hurry - No hurry as the order of subtraction.

\vspace{0.4in}


11. What is the notation used for the value calculated in question 10?

\newpage

We will now simulate a **null distribution** of sample differences in proportions. The null distribution is created under the assumption the null hypothesis is true.  

12.  First, let's think about how one simulation would be created on the null distribution using cards.  

\rgi How many cards would you need?
\vspace{0.1in}

\rgi What would be written on each card?

\vspace{0.5in}

13. Next, we would mix the cards together and shuffle into two piles.  

\rgi How many cards would be in each pile?  
\vspace{0.1in}

\rgi What would each pile represent?
\vspace{0.5in}

14. Once we have one simulated sample, what would we calculate and plot on the null distribution?  *Hint*: What statistic are we calculating from the data?

\vspace{0.8in}

15.  Simulate one sample using the cards provided by your instructor.  Write down the value of the simulated statistic.  How does the value of your group's simulated statistic compare to the other groups at your table?  Are the simulated values closer to the null value of zero than the actual calculated difference in proportions?

\vspace{1in}

To create the null distribution of differences in sample proportions, we will use the `two_proportion_test()` function in R (in the `catstats` package).  We will need to enter the response variable name and the explanatory variable name for the formula, the data set name (identified above as `good`), the outcome for the explanatory variable that is first in subtraction, number of repetitions, the outcome for the response variable that is a success (what the numerator counts when calculating a sample proportion), and the direction of the alternative hypothesis.

The response variable name is `Behavior` and the explanatory variable name is `Condition`.

\newpage 

16.  What inputs should be entered for each of the following to create the simulation?
\vspace{1mm}

* First in subtraction (What is the outcome for the explanatory variable that is used as first in the order of subtraction? `"Hurry"` or `"No hurry"`):

\vspace{.15in}
* Number of repetitions:
    
\vspace{.15in}
* Response value numerator (What is the outcome for the response variable that is considered a success? `"Help"` or `"No help"`):

\vspace{.15in}
* As extreme as (enter the value for the sample difference in proportions):
    
\vspace{.15in}
* Direction (`"greater"`, `"less"`, or `"two-sided"`):

\vspace{.15in}

Using the R script file for this activity, enter your answers for question 16 in place of the `xx`'s to produce the null distribution with 1000 simulations; highlight and run lines 1--18.


```r
two_proportion_test(formula = Behavior~Condition, # response ~ explanatory
    data = good, # Name of data set
    first_in_subtraction = "xx", # Order of subtraction: enter the name of Group 1
    number_repetitions = 1000, # Always use a minimum of 1000 repetitions
    response_value_numerator = "xx", # Define which outcome is a success 
    as_extreme_as = xx, # Calculated observed statistic (difference in sample proportions)
    direction="xx") # Alternative hypothesis direction ("greater","less","two-sided")
```

17.  Sketch the null distribution created here.

\vspace{1.5in}


18. What value is the null distribution centered around?  Explain why this makes sense.

\vspace{.8in}

19.  What is the value of the p-value? *Remember*: This is the value given at the bottom of the null distribution.

\vspace{0.2in}
\newpage

20.  Interpret the p-value in context of the study.

\vspace{1in}

21.  How much evidence does the p-value provide against the null hypothesis? *Hint*: Refer to the guidelines given in Activity 6A.

\vspace{0.4in}

22.  Write a conclusion to the test. 

\vspace{0.8in}

23. In the next activity we will find a 99\% confidence interval.  Based on the conclusion, do you expect the confidence interval to contain the null value of zero?  Explain your answer.
\vspace{0.8in}

### Take-home messages

1.	When comparing two groups, we are looking at the difference between two parameters.  In the null hypothesis, we assume the two parameters are equal, or that there is no difference between the two proportions.  

2.  We use the same guidelines for the strength of evidence as we did in Activity 6A.  

3. To create one simulated sample on the null distribution for a difference in sample proportions, label $n_1 + n_2$ cards with the response variable outcomes from the original data. Mix cards together and shuffle into two new groups of sizes $n_1$ and $n_2$, representing the explanatory variable groups. Calculate and plot the difference in proportion of successes.


### Additional notes

Use this space to summarize your thoughts and take additional notes on today's activity and material covered.

\newpage
