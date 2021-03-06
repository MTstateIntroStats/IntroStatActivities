---
title: "15-inference-1cat_test"
output: pdf_document
---

Among all comic book characters produced by the comic book publisher Marvel, 25% are female. The comic book publisher DC Comics has taken note of this disparity in the number of female versus male characters, and is trying to diversify their offerings. In a random sample of recently published DC Comics books, 52 characters were included in the comics, of which 15 are female.

1. What type of plot would be appropriate to display this data?

\vspace{0.3in}

2. Calculate the summary statistic.  Use appropriate notation.

\vspace{0.3in}

3. Write the parameter of interest in context of the problem.

\vspace{0.8in}

4.  Write the null hypothesis in notation.

\vspace{0.3in}

5. Write the alternative hypothesis in words. 

\vspace{0.8in}

6. Is the independence condition met?  Explain.

\vspace{0.6in}

7. What values should be entered for each of the following into the one proportion test to create 1000 simulations?

\vspace{1mm}

* Probability of success:

\vspace{.2in}
* Sample size:
    
\vspace{.2in}
* Number of repetitions:
    
\vspace{.2in}
* As extreme as:
    
\vspace{.2in}
* Direction (`"greater"`, `"less"`, or `"two-sided"`):

\vspace{.2in}

We will use the `one_proportion_test()` function in `R` (in the `catstats` package) to simulate the null distribution of sample proportions and compute a p-value. Using the provided `R` script file, fill in the values/words for each `xx` with your answers from question 18 in the one proportion test to create a null distribution with 1000 simulations. Then highlight and run lines 1--14.


```r
one_proportion_test(probability_success = 0.25, # Null hypothesis value
          sample_size = 52, # Enter sample size
          number_repetitions = 1000, # Enter number of simulations
          as_extreme_as = 0.288, # Observed statistic
          direction = "greater", # Specify direction of alternative hypothesis
          report_value = "proportion") # Reporting proportion or number of successes?
```

7.  Interpret the p-value in context of the study.

\vspace{1in}

8. Write a conclusion in context of the study.

\vspace{1in}

9. Is the validity condition met to use theory-based methods to analyze?  Explain.

\vspace{0.8in}

10. Calculate the standardized statistic.

\vspace{0.8in}

11. Interpret the standardized statistic.

\vspace{0.8in}


12.  Sketch a graph of the normal distribution and how to find the p-value for the theory-based test.

\vspace{1.4in}

Use the following code to find the theory-based p-value.


```r
pnorm(xx, # Enter value of standardized statistic
      m=0, s=1 # Using the standard normal mean = 0, sd = 1
      lower.tail=FALSE) # Gives a p-value greater than the standardized statistic
```

13. Why did you expect that the value of the p-value is similar between theory and simulation methods?
