## Activity 6:  Helperer-Hinderer --- Simulation-based Hypothesis Test

\setstretch{1}

### Learning outcomes

* Identify the two possible explanations (one assuming the null hypothesis and one assuming the alternative hypothesis) for a relationship seen in sample data.

* Given a research question involving a single categorical variable, construct the null and alternative hypotheses
  in words and using appropriate statistical symbols.
  
* Describe and perform a simulation-based hypothesis test for a single proportion.

### Terminology review

In today's activity, we will introduce simulation-based hypothesis testing for a single categorical variable. Some terms covered in this activity are:

* Parameter of interest

* Null hypothesis

* Alternative hypothesis

* Simulation

To review these concepts, see Chapter 5 in your textbook, focusing on Sections 5.1 through 5.3.

### Steps of the statistical investigation process

We will work through a five-step process to complete a hypothesis test for a single proportion, first introduced in the Martian Alphabet Activity in week 1.

* **Ask a research question** that can be addressed by collecting data. What are the researchers trying to show?

* **Design a study and collect data**. This step involves selecting the people or objects to be studied and how to gather relevant data on them.

* **Summarize and visualize the data**. Calculate summary statistics and create graphical plots that best represent the research question.

* **Use statistical analysis methods to draw inferences from the data**. Choose a statistical inference method appropriate for the data and identify the p-value and/or confidence interval after checking assumptions. In this study, we will focus on using randomization to generate a simulated p-value.

* **Communicate the results and answer the research question**. Using the p-value and confidence interval from the analysis, determine whether the data provide statistical evidence against the null hypothesis. Write a conclusion that addresses the research question.

\newpage

### Helper-Hinderer

Do young children know the difference between helpful and unhelpful behavior? A study by Hamblin, Wynn, and Bloom reported in Nature [@hamblin2007] was intended to check young kids' feelings about helpful and non-helpful behavior. Non-verbal infants ages 6 to 10 months were shown short videos with different shapes either helping or hindering the climber. As a class we will watch this short video to see how the experiment was run: https://youtu.be/anCaGBsBOxM. Researchers were hoping to assess: Are infants more likely to preferentially choose the helper toy over the hinderer toy?  In the study, of the 16 infants age 6 to 10 months, 14 chose the *helper* toy and 2 chose the *hinderer* toy.


In this study, the observational units are the infants ages 6 to 10 months.  The variable measured on each observational unit (infant) is whether they chose the helper or the hinderer toy.  This is a categorical variable so we will be assessing the proportion of infants ages 6 to 10 months that choose the helper toy.  Choosing the helper toy in this study will be considered a success.

#### Ask a research question {-}

1. Identify the research question for this study.  What are the researchers hoping to show?

\vspace{0.6in}

#### Design a study and collect data {-}

Before using statistical inference methods, we must check that the cases are independent.  The sample observations are independent if the outcome of one observation does not influence the outcome of another. One way this condition is met is if data come from a simple random sample of the target population.

2.  Are the cases independent? Justify your answer.

\vspace{0.8in}

#### Summarize and visualize the data {-}


```r
 # Read in data set
infants <- read.csv("https://math.montana.edu/courses/s216/data/infantchoice.csv")
infants %>% count(choice)  # Count number in each choice category
```

```
#>     choice  n
#> 1   helper 14
#> 2 hinderer  2
```

$$\hat{p} = \frac{\mbox{number of successes}}{\mbox{total number of observational units}}$$
\newpage

3.  Using the `R` output, calculate the summary statistic (sample proportion) to represent the research question.  Recall that `choosing the helper toy` is a considered a success.  Use appropriate notation.

\vspace{0.5in}

4.  What type of plot should be used to represent these data? Sketch this plot.

\vspace{1.5in}

We cannot assess whether infants are more likely to choose the helper toy based on the statistic and plot alone.  The next step is to analyze the data by using a hypothesis test to discover if there is evidence against the null hypothesis.

#### Use statistical analysis methods to draw inferences from the data {-}

When performing a hypothesis test, we must first identify the null hypothesis.  The null hypothesis is written about the parameter of interest, or the value that summarizes the variable in the population.  *For example, in the Martian Alphabet Activity, the parameter of interest is the true proportion of statistic students who would correctly identify Bumba.*

5.  Write out the parameter of interest for this study. 

\vspace{0.8in}

6.  If the children are just randomly choosing the toy, what proportion of infants would choose the helper toy?  This is the null value for our study.

\vspace{0.3in}

7.  Using the parameter of interest in question 5, write out the null hypothesis in words.  That is, what do we assume to be true about the parameter of interest when we perform our simulation? 

\vspace{0.8in}

The notation used for a population proportion (or probability, or true proportion) is $\pi$.  Since this summarizes a population, it is a parameter. When writing the **null hypothesis** in notation, we set the parameter equal to the null value, $H_0: \pi = \pi_0$.

\newpage 

8. Write the null hypothesis in notation using the null value of 0.5 in place of $\pi_0$ in the equation given on the previous page.

\vspace{0.5in}

The **alternative hypothesis** is the claim to be tested and the direction of the claim (less than, greater than, or not equal to) is based on the research question.  

9.  Based on the research question from question 1, are we testing that the parameter is greater than 0.5, less than 0.5 or different than 0.5? 

\vspace{0.4in}

10. Write out the alternative hypothesis in words.

\vspace{1in}

11.  Write out the alternative hypothesis in notation.

\vspace{0.5in}

Remember that when utilizing a hypothesis test, we are evaluating two competing possibilities. For this study the **two possibilities** are either...

* The true proportion of infants who choose the helper is 0.5 and our results just occurred by random chance; or,
  
* The true proportion of infants who choose the helper is greater than 0.5 and our results reflect this.
  
Notice that these two competing possibilities represent the null and alternative hypotheses.
  
We will now simulate a **null distribution** of sample proportions. The null distribution is created under the assumption the null hypothesis is true.  In this case, we assume the true proportion of infants who choose the helper is 0.5, so we will create 1000 (or more) different simulations of 16 infants under this assumption.

Let's think about how to use cards to create one simulation of 16 infants under the assumption the null hypothesis is true.  We will write the response variable outcomes on each card to represent the null hypothesis.

12.  How many cards total do we need?  On how many cards will we write **helper**?  On how many cards will we write **hinderer**?

\vspace{0.5in}

13.  Next, we would mix the cards together and draw 1 card, write down if the card says helper or hinderer, and replace the card.  How many times would we need to repeat this process to simulate one sample?

\vspace{0.3in}

14.  Once we have one simulated sample, what would we calculate and plot on the null distribution?  *Hint*: What statistic are we calculating from the data?

\vspace{0.5in}

15.  Create one simulation using the cards provided.  Write down your simulated sample proportion.  This is one simulation created under the assumption the null hypothesis is true.  Is this value closer to 0.5 the null value or closer to the sample proportion (0.875)?  Compare your simulated value to the other group's at your table.

\vspace{0.8in}

16.  Report your simulated sample proportion to your instructor.  Sketch the distribution created by your class below.

\vspace{1.5in}

17. Circle the observed statistic (value from question 3) on the distribution you drew in question 16.  Where does this statistic fall in this distribution: Is it near the center of the distribution (near 0.5) or in one of the tails of the distribution?  

\vspace{1in}

18. Is the observed statistic likely to happen or unlikely to happen if the true proportion of infants who choose the helper is 0.5?  Explain your answer using the plot.

\vspace{0.8in}

In the next class, we will continue to assess the strength of evidence against the null hypothesis by using a computer to simulate 1000 samples when we assume the null hypothesis is true.


### Take-home messages

1.	In a hypothesis test we have two competing hypotheses, the null hypothesis and the alternative hypothesis.  The null hypothesis represents either a skeptical perspective or a perspective of no difference or no effect. The alternative hypothesis represents a new perspective such as the possibility that there has been a change or that there is a treatment effect in an experiment.  

2.  In a simulation-based test, we create a distribution of possible simulated statistics for our sample if the null hypothesis is true.  Then we see if the calculated observed statistic from the data is likely or unlikely to occur when compared to the null distribution.  

3.  To create one simulated sample on the null distribution for a sample proportion, spin a spinner with probability equal to $\pi_0$ (the null value), $n$ times or draw with replacement $n$ times from a deck of cards created to reflect $\pi_0$ as the probability of success. Calculate and plot the proportion of successes from the simulated sample. 

### Additional notes

Use this space to summarize your thoughts and take additional notes on today's activity and material covered.

\newpage
