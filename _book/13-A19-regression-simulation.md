## Activity 13A:  Prediction of Crocodylian Body Size

\setstretch{1}

### Learning outcomes

* Given a research question involving two quantitative variables, construct the null and alternative hypotheses
  in words and using appropriate statistical symbols.
  
* Describe and perform a simulation-based hypothesis test for slope or correlation.

* Interpret and evaluate a p-value for a simulation-based hypothesis test for a slope or correlation.

* Use bootstrapping to find a confidence interval for the slope or correlation.

* Interpret a confidence interval for a slope or correlation.

### Terminology review
In today's activity, we will use simulation-based methods for hypothesis tests and confidence intervals for a linear regression slope or correlation. Some terms covered in this activity are:

* Correlation

* Slope 

* Regression line

To review these concepts, see Chapter 21 in the textbook.


### Crocodylian Body Size

Much research surrounds using measurements of animals to estimate body-size of extinct animals.  Many challenges exist in making accurate estimates for extinct crocodylians.  The term crocodylians refers to all members of the family Crocodylidae (“true” crocodiles), family Alligatoridae (alligators and caimans) and family Gavialidae (gharial, Tomistoma). The researchers in this study [@obrien2019] state, "Among extinct crocodylians and their precursors (e.g., suchians), several methods have been developed to predict body size from suites of hard-tissue proxies. Nevertheless, many have limited applications due to the disparity of some major suchian groups and biases in the fossil record. Here, we test the utility of head width (HW) as a broadly applicable body-size estimator in living and fossil suchians."  Is there evidence that head width is a good predictor of body size for crocodylians? 



```r
# Read in data set
croc <- read.csv("https://math.montana.edu/courses/s216/data/Crocodylian_headwidth.csv")
croc <- croc %>%
    na.omit()
```

#### Vocabulary review {-}

1. Explain why regression methods are appropriate to use to address the researchers' question. Make sure you clearly define the variables of interest in your explanation and their roles.

\vspace{.5in}


Use the provided R script file to create a scatterplot to examine the relationship between head width and total body length by filling in the variable names (`HW_cm` and `TL_cm`) for `explanatory` and `response` in line 14.  Highlight and run lines 1--20. 
 

```r
croc %>% # Pipe data set into...
ggplot(aes(x = explanatory, y = response))+  # Specify variables
  geom_point() +  # Add scatterplot of points
  labs(x = "head width (cm)",  # Label x-axis
       y = "total length (cm)",  # Label y-axis
       title = "Scatterplot of Crocodylian Head Width vs. Total Length") + 
               # Be sure to title your plots
  geom_smooth(method = "lm", se = FALSE)  # Add regression line

```

2. Sketch the plot created below. Based on your plot, does it appear that there is a relationship between head width and total length? Note: head width should be on the $x$-axis.

\vspace{2in}

3. Describe the features of the plot above, addressing all four characteristics of a scatterplot.  

\vspace{1in}

|        If you indicated there are potential outliers, which points are they?

\vspace{0.5in}

#### Ask a research question {-}

4. Write out the null hypothesis in words to test slope.

\vspace{0.8in}

5. Using the research question, write the alternative hypothesis in notation using slope as the summary measure.

\vspace{0.5in}

#### Summarize and visualize the data {-}

Using the provided R script file, enter the response variable name, `TL_cm`, into the `lm()` (linear model) function for `response` and the explanatory variable name, `HW_cm`, for `explanatory` in line 21 to get the linear model output and value for the correlation coefficient.  Highlight and run lines 25--27.


```r
lm.croc <- lm(response~explanatory, data=croc) # lm(response~explanatory)
round(summary(lm.croc)$coefficients, 5)
cor(croc$HW_cm, croc$TL_cm)
```

6.  Using the output from the evaluated R code above, write the equation of the regression line in the context of the problem using appropriate statistical notation.
\vspace{1in}

7.  Interpret the estimated slope in context of the problem.

\vspace{1in}

8.  Report the value of correlation between head width and total body length. 

\vspace{0.3in}

#### Use statistical inferential methods to draw inferences from the data {-}

In this activity, we will focus on using simulation-based methods for inference in regression.  

#### Simulation-based hypothesis test {-}

Let's start by thinking about how one simulation would be created on the null distribution using cards.  First, we would write the values for the response variable, total length, on each card.  Next, we would shuffle these $y$ values while keeping the $x$ values (explanatory variable) in the same order.  Then, find the line of regression for the shuffled $(x, y)$ pairs and calculate either the slope or correlation of the shuffled sample.  

We will use the `regression_test()` function in R (in the `catstats` package) to simulate the null distribution of shuffled slopes (or shuffled correlations) and compute a p-value.  We will need to enter the response variable name and the explanatory variable name for the formula, the data set name (identified above as `croc`), the summary measure for the test (either slope or correlation), number of repetitions, the sample statistic (value of slope or correlation), and the direction of the alternative hypothesis.

The response variable name is `TL_cm` and the explanatory variable name is `HW_cm` for these data.

9. What inputs should be entered for each of the following to create the simulation to test regression slope?

\vspace{.5 mm}

* Direction (`"greater"`, `"less"`, or `"two-sided"`):

\vspace{.2in}

* Summary measure (choose `"slope"` or `"correlation"`):

\vspace{.2in}
* As extreme as (enter the value for the sample slope):

\vspace{0.2in}

* Number of repetitions:
    
\vspace{.2in}

Using the R script file for this activity, enter your answers for question 9 in place of the `xx`'s to produce the null distribution with 1000 simulations.  Highlight and run lines 32--37.


```r
regression_test(TL_cm~HW_cm, # response ~ explanatory
               data = croc, # Name of data set
               direction = "xx", # Sign in alternative ("greater", "less", "two-sided")
               summary_measure = "xx", # "slope" or "correlation"
               as_extreme_as = xx, # Observed slope or correlation
               number_repetitions = 1000) # Number of simulated samples for null distribution
```

10.  Report the p-value from the R output. 
\vspace{0.5in}

11.  Suppose we wanted to complete the simulation test using correlation as the summary measure, instead of slope.  Which two inputs in #9 would need to be changed to test for correlation?  What inputs should you use instead?
\vspace{0.75in}

12.  Change the inputs in lines 32--37 to test for correlation instead of slope.  Highlight and run those lines, then report the new p-value of the test.
\vspace{0.5in}

13.  The p-values from the test of slope (#10) and the test of correlation (#12) should be similar.  Explain why the two p-values should match. *Hint: think about the relationship between slope and correlation!*
\vspace{1in}

#### Simulation-based confidence interval {-}

We will use the `regression_bootstrap_CI()` function in R (in the `catstats` package) to simulate the bootstrap distribution of sample slopes (or sample correlations) and calculate a confidence interval. Fill in the missing values in the provided R script file to find a 95\% confidence interval for slope. Highlight and run lines 42--46. 


```r
regression_bootstrap_CI(response~explanatory, # response ~ explanatory
   data = croc, # Name of data set
   confidence_level = xx, # Confidence level as decimal
   summary_measure = "xx", # Slope or correlation
   number_repetitions = 1000) # Number of simulated samples for bootstrap distribution
```

14.  Report the bootstrap 95\% confidence interval in interval notation.  
\vspace{0.5in}

15.  Interpret the interval in question 14 in context of the problem.  *Hint: use the interpretation of slope in your confidence interval interpretation.*

\vspace{0.8in}
   
#### Communicate the results and answer the research question {-}

16. Based on the p-value, write a conclusion in context of the problem.

\vspace{.8in}

17. Does the conclusion based on the p-value agree with the results of the 95\% confidence interval?  What does each tell you about the null hypothesis?

\vspace{.6in}
\newpage

### Take-home messages

1.	The p-value for a test for correlation should be approximately the same as the p-value for the test of slope.  In the simulation test, we just change the statistic type from slope to correlation and use the appropriate sample statistic value.  

2. To interpret a confidence interval for the slope, think about how to interpret the sample slope and use that information in the confidence interval interpretation for slope.  

3. To create one simulated sample on the null distribution when testing for a relationship between two quantitative variables, hold the $x$ values constant and shuffle the $y$ values to new $x$ values. Find the regression line for the shuffled data and plot the slope or the correlation for the shuffled data.

4. To create one simulated sample on the bootstrap distribution when assessing two quantitative variables, label $n$ cards with the original (response, explanatory) values.  Randomly draw with replacement $n$ times.  Find the regression line for the resampled data and plot the resampled slope or correlation. 

### Additional notes

Use this space to summarize your thoughts and take additional notes on today's activity and material covered.

\newpage
