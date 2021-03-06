## Activity:  Movie Profits

\setstretch{1}

### Learning objectives

* Identify and create appropriate summary statistics and plots
  given a data set with two quantitative variables.
  
* Find the estimated line of regression using summary statistics and `R` linear model (`lm()`) output.

* Interpret the slope coefficient in context of the problem.

### Terminology review

In this week's activity, we will review summary measures and plots for two quantitative variables.  Some terms covered in this activity are:

* Least-squares line of regression

* Slope and $y$-intercept

* Residuals

To review these concepts, see Chapter 3 in the textbook.  

### Movies released in 2016

We will revisit the movie data set collected on Movies released in 2016 to further explore the relationship between budget and revenue. Here is a reminder of the variables collected on these movies.

| **Variable** 	| **Description** |
|----	|-------------	|
| `budget_mil` | Amount of money (in US $ millions) budgeted for the production of the movie |
| `revenue_mil` | Amount of money (in US $ millions) the movie made after release|
| `duration` | Length of the movie (in minutes)|
| `content_rating` | Rating of the movie (`G`, `PG`, `PG-13`, `R`, `Not Rated`)|
| `imdb_score` | IMDb user rating score from 1 to 10 |
| `genres` | Categories the movie falls into (e.g., Action, Drama, etc.) |
| `movie_facebook_likes` | Number of likes a movie receives on Facebook |




```r
movies %>% # Data set pipes into...
ggplot(aes(x = budget_mil, y = revenue_mil))+  # Specify variables
  geom_point() +  # Add scatterplot of points
  labs(x = "Budget in Millions ($)",  # Label x-axis
       y = "Revenue in Millions ($)",  # Label y-axis
       title = "Revenue vs. Budget") + # Be sure to tile your plots
  geom_smooth(method = "lm", se = FALSE)  # Add regression line
```

#### Slope {-}

The linear model function in `R` (`lm()`) gives us the summary for the least squares regression line.  The estimate for `(Intercept)` is the $y$-intercept for the line of least squares, and the estimate for `budget_mil` (the $x$-variable name) is the value of $b_1$, the slope.


```r
# Fit linear model: y ~ x
revenueLM <- lm(revenue_mil ~ budget_mil, data=movies)
summary(revenueLM)$coefficients # Display coefficient summary
```

```
#>              Estimate Std. Error  t value     Pr(>|t|)
#> (Intercept) 9.1693054  9.0175499 1.016829 3.119606e-01
#> budget_mil  0.9460001  0.1056786 8.951670 4.339561e-14
```

1.  Write out the least squares line using the summary statistics provided above in context of the problem.

\vspace{.5in}

You may remember from middle and high school that slope $=\frac{\mbox{rise}}{\mbox{run}}$.  

Using $b_1$ to represent slope, we can write that as the fraction $\frac{b_1}{1}$. 

Therefore, the slope predicts how much the line will *rise* for each *run* of +1. In other words, as the $x$ variable increases by 1 unit, the $y$ variable is predicted to change (increase/decrease) by the value of slope.


2. Interpret the value of slope in context of the problem.

\vspace{.8in}

3. Using the least squares line from question 1, predict the revenue for a movie with a budget of 165 $MM.

\vspace{.6in}

4.  Predict the revenue for a movie with a budget of 500 $MM.  

\vspace{0.8in}

5. The prediction in Q4 is an example of what?

\vspace{0.3in}

#### Residuals {-}

The model we are using assumes the relationship between the two variables follows a straight line. The residuals are the errors, or the variability in the response that hasn't been modeled by the line (model).

\begin{center}
Data = Model + Residual

$\implies$ Residual = Data $-$ Model

$e_i=y_i-\hat{y}_i$
\end{center}

6.  The movie *Independence Day: Resurgence* had a budget of 165 \$MM and revenue of 102.315 \$MM.  Find the residual for this movie.

\vspace{.8in}

7.  Did the line of regression overestimate or underestimate the revenue for this movie? 

\vspace{.2in}

#### Multivariable plots {-}
What if we wanted to see if the relationship between movie budget and revenue differs if we add another variable into the picture?  The following plot visualizes three variables, creating a **multivariable** plot. 


```r
movies %>% # Data set pipes into...
  filter(content_rating != "Not Rated") %>% # Remove Not Rated movies
  ggplot(aes(x = budget_mil, y = revenue_mil, color = content_rating)) +  # Specify variables
  geom_point(aes(shape = content_rating), size = 3) +  # Add scatterplot of points
  labs(x = "Budget in Millions ($)",  # Label x-axis
       y = "Revenue in Millions ($)",  # Label y-axis
       color = "Content Rating",  # Label legend
       title = "Revenue vs. Budget") + # Be sure to tile your plots
  geom_smooth(method = "lm", se = FALSE, lwd = 2) + # Add regression lines
  scale_color_grey() # Make black and white
```



\begin{center}\includegraphics[width=0.7\linewidth]{11-EDA-two-quantitative-PartB_files/figure-latex/unnamed-chunk-4-1} \end{center}

8.  Identify the three variables plotted in this graph.

\vspace{0.5in}

9. Does the *relationship* between movie budget and revenue differ among the different content ratings?  Explain.

\vspace{1in}

In order to see what other variables may have an impact on revenue for Movies released in 2016 we created a multivariate model.  The following `R` code gives the estimates for the regression model with `budget_mil` and `duration` included.


```r
# Fit linear model: y ~ x
revenueLM <- lm(revenue_mil ~ budget_mil+duration, data=movies)
summary(revenueLM)$coefficients # Display coefficient summary
```

```
#>               Estimate Std. Error   t value     Pr(>|t|)
#> (Intercept) 72.0861616 47.6716927  1.512138 1.340417e-01
#> budget_mil   1.0198102  0.1186827  8.592744 2.613611e-13
#> duration    -0.6054657  0.4505494 -1.343839 1.824165e-01
```

10. Use the provided `R` output to write the linear regression model including both variables.  *Hint*: The estimated line of regression is of the form:

$$\widehat{\text{revenue}} = b_0 + b_1\times budget + b_2\times duration.$$

\vspace{1in}

11. Using the fitted regression model above, predict the revenue for a movie in 2016 with a budget of 180 $MM and duration of 100 minutes.


### Take-home messages

1.	Two quantitative variables are graphically displayed in a scatterplot.  The explanatory variable is on the $x$-axis and the response variable is on the $y$-axis.  When describing the relationship between two quantitative variables we look at the form (linear or non-linear), direction (positive or negative), strength, and for the presence of outliers. 

2.  There are three summary statistics used to summarize the relationship between two quantitative variables: correlation ($r$), slope of the regression line ($b_1$), and the coefficient of determination ($r^2$).  

3.  We can use the line of regression to predict values of the response variable for values of the explanatory variable. Do not use values of the explanatory variable that are outside of the range of values in the data set to predict values of the response variable (reflect on why this is true.).  This is called **extrapolation**. 

### Additional notes

Use this space to summarize your thoughts and take additional notes on today's activity and material covered.
