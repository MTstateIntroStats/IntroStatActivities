## Week 9 Lab:  COVID Infection and Vaccination Rates

\setstretch{1}

### Learning objectives

* Given a research question involving two categorical variables, construct the null and alternative hypotheses
  in words and using appropriate statistical symbols.
  
* Describe and perform a simulation-based hypothesis test for a difference in proportions.

* Interpret and evaluate a p-value for a simulation-based hypothesis test for a difference in proportions.

### COVID Infection and Vaccination Rates

According to the *Washington Post* "States with higher vaccination rates now have markedly fewer coronavirus cases, as infections are dropping in places where most residents have been immunized and are rising in many places people have not."  In this article they found that there are differences in infection rates for different counties within a specific state.  To check this claim, a random sample of 125 counties from different states was assessed.  Vaccination rates were found for each county and broken up into groups, high and low, based on a vaccination rate of 40\%.  Those counties with a vaccination rate of greater than 40\% was considered a high vaccination rate.  The 2nd variable measured on these counties was whether the number of cases per 100,000 residents was less than or greater than 4.25, the national rate at that time.  Researchers want to assess if counties with a high vaccination rate are more likely to have lower coronavirus cases


```r
# Read data set in
covid <- read.csv("data/covid_vaccinations.csv") 
covid %>% group_by(vaccination_rate) %>% count(cases)
```

```
#> # A tibble: 4 x 3
#> # Groups:   vaccination_rate [2]
#>   vaccination_rate cases      n
#>   <chr>            <chr>  <int>
#> 1 high             higher    21
#> 2 high             lower     40
#> 3 low              higher    32
#> 4 low              lower     32
```

1. What is the explanatory variable?

\vspace{0.5in}

2. What is the response variable?

\vspace{0.5in}

3. Fill in the following two-way table using the data output above.

...

4. Write the parameter of interest for this study.

\vspace{1in}

5. Calculate the difference in proportion of counties with a lower than the national average of cases for those with a high and low vaccination rate.  Use high - low for the order of subtraction.  Use appropriate notation.

\vspace{0.8in}

Use the following code to create a segmented bar plot of the data.


```r
covid %>% # Data set piped into...
ggplot(aes(x = vaccination_rate, fill = cases)) +   # This specifies the variables
  geom_bar(stat = "count", position = "fill") +  # Tell it to make a stacked bar plot
  labs(title = "Segmented Bar Plot of Coronavirus Cases by Vaccination Rates",  
       # Make sure to title your plot 
       x = "Level of Light",   # Label the x axis
       y = "") +  # Remove y axis label
    scale_fill_grey()  # Make figure black and white
```
6.  Does there appear to be an association between variabes based on the plot?  Explain your answer.

\vspace{1in}

7.  Write the null hypothesis for this study in notation.

\vspace{0.5in}

8.  Using the research question, write the alternative hypothesis in words.

\vspace{1in}

Enter the .... for xx in the catstats function below to create the null distribution and find the p-value for the test.


```r
two_proportion_test(formula = cases~vaccination_rate, # response ~ explanatory
    data= covid, # Name of data set
    first_in_subtraction = "high", # Order of subtraction: enter the name of Group 1
    number_repetitions = 1000, # Always use a minimum of 1000 repetitions
    response_value_numerator = "lower", # Define which outcome is a success 
    as_extreme_as = 0.156, # Calculated observed statistic (difference in sample proportions)
    direction="greater") # Alternative hypothesis direction ("greater","less","two-sided")
```

9.  Interpret the p-value in context of the problem.

\vspace{0.8in}

10.  Do you expect that a 90\% confidence interval would contain the null value of zero?  Explain your answer.

\vspace{0.8in}

Enter .... to create a simulation 90\% confidence interval.


```r
two_proportion_bootstrap_CI(formula = cases~vaccination_rate, 
        data=covid, # Name of data set
        first_in_subtraction = "high", # Order of subtraction: enter the name of Group 1
        response_value_numerator = "lower", # Define which outcome is a success 
        number_repetitions = 1000, # Always use a minimum of 1000 repetitions
        confidence_level = 0.9) # Enter the level of confidence as a decimal
```

11.  Report and interpret the 90\% confidence interval.

\vspace{0.8in}

12.  Write a conclusion to the research question in context of the study.

\vspace{0.8in}

13.  What type of error could have occurred?

\vspace{0.2in}

|    Interpret this error in context of the study.

\vspace{0.8in}

14.  Write a paragraph summarizing the results of the study as if writing a press release.  Be sure to describe:

* Summary statistic and interpretation

* P-value and interpretation

* Confidence interval and interpretation

* Conclusion (written to answer the research question)

* Scope of inference

\vspace{2in}
