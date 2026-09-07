Getting Started: Diamonds
================
Emily Boyd
2020-

- [Grading Rubric](#grading-rubric)
  - [Individual](#individual)
  - [Submission](#submission)
- [Data Exploration](#data-exploration)
  - [**q1** Create a plot of `price` vs `carat` of the `diamonds`
    dataset below. Document your observations from the
    visual.](#q1-create-a-plot-of-price-vs-carat-of-the-diamonds-dataset-below-document-your-observations-from-the-visual)
  - [**q2** Create a visualization showing variables `carat`, `price`,
    and `cut` simultaneously. Experiment with which variable you assign
    to which aesthetic (`x`, `y`, etc.) to find an effective
    visual.](#q2-create-a-visualization-showing-variables-carat-price-and-cut-simultaneously-experiment-with-which-variable-you-assign-to-which-aesthetic-x-y-etc-to-find-an-effective-visual)
- [Communication](#communication)
  - [**q3** *Knit* your document in order to create a
    report.](#q3-knit-your-document-in-order-to-create-a-report)
  - [**q4** *Push* your knitted document to
    GitHub.](#q4-push-your-knitted-document-to-github)
  - [**q5** *Submit* your work to
    Canvas](#q5-submit-your-work-to-canvas)
  - [**q6** *Prepare* to present your team’s
    findings!](#q6-prepare-to-present-your-teams-findings)

*Purpose*: Throughout this course, you’ll complete a large number of
*exercises* and *challenges*. Exercises are meant to introduce content
with easy-to-solve problems, while challenges are meant to make you
think more deeply about and apply the content. The challenges will start
out highly-scaffolded, and become progressively open-ended.

In this challenge, you will go through the process of exploring,
documenting, and sharing an analysis of a dataset. We will use these
skills again and again in each challenge. *Note*: You will have seen all
of these steps in `e-vis00-basics`. This challenge is *primarily* a
practice run of the submission system. The Data Exploration part should
be very simple.

<!-- include-rubric -->

# Grading Rubric

<!-- -------------------------------------------------- -->

Unlike exercises, **challenges will be graded**. The following rubrics
define how you will be graded, both on an individual and team basis.

## Individual

<!-- ------------------------- -->

| Category | Needs Improvement | Satisfactory |
|----|----|----|
| Effort | Some task **q**’s left unattempted | All task **q**’s attempted |
| Observed | Did not document observations, or observations incorrect | Documented correct observations based on analysis |
| Supported | Some observations not clearly supported by analysis | All observations clearly supported by analysis (table, graph, etc.) |
| Assessed | Observations include claims not supported by the data, or reflect a level of certainty not warranted by the data | Observations are appropriately qualified by the quality & relevance of the data and (in)conclusiveness of the support |
| Specified | Uses the phrase “more data are necessary” without clarification | Any statement that “more data are necessary” specifies which *specific* data are needed to answer what *specific* question |
| Code Styled | Violations of the [style guide](https://style.tidyverse.org/) hinder readability | Code sufficiently close to the [style guide](https://style.tidyverse.org/) |

## Submission

<!-- ------------------------- -->

Make sure to commit both the challenge report (`report.md` file) and
supporting files (`report_files/` folder) when you are done! Then submit
a link to Canvas. **Your Challenge submission is not complete without
all files uploaded to GitHub.**

``` r
library(tidyverse)
```

    ## ── Attaching core tidyverse packages ──────────────────────── tidyverse 2.0.0 ──
    ## ✔ dplyr     1.2.1     ✔ readr     2.2.0
    ## ✔ forcats   1.0.1     ✔ stringr   1.6.0
    ## ✔ ggplot2   4.0.3     ✔ tibble    3.3.1
    ## ✔ lubridate 1.9.5     ✔ tidyr     1.3.2
    ## ✔ purrr     1.2.2     
    ## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()
    ## ℹ Use the conflicted package (<http://conflicted.r-lib.org/>) to force all conflicts to become errors

# Data Exploration

<!-- -------------------------------------------------- -->

In this first stage, you will explore the `diamonds` dataset and
document your observations.

### **q1** Create a plot of `price` vs `carat` of the `diamonds` dataset below. Document your observations from the visual.

*Hint*: We learned how to do this in `e-vis00-basics`!

``` r
## TASK: Plot `price` vs `carat` below
## Your code here!
?diamonds 
```

    ## starting httpd help server ... done

``` r
glimpse(diamonds)
```

    ## Rows: 53,940
    ## Columns: 10
    ## $ carat   <dbl> 0.23, 0.21, 0.23, 0.29, 0.31, 0.24, 0.24, 0.26, 0.22, 0.23, 0.…
    ## $ cut     <ord> Ideal, Premium, Good, Premium, Good, Very Good, Very Good, Ver…
    ## $ color   <ord> E, E, E, I, J, J, I, H, E, H, J, J, F, J, E, E, I, J, J, J, I,…
    ## $ clarity <ord> SI2, SI1, VS1, VS2, SI2, VVS2, VVS1, SI1, VS2, VS1, SI1, VS1, …
    ## $ depth   <dbl> 61.5, 59.8, 56.9, 62.4, 63.3, 62.8, 62.3, 61.9, 65.1, 59.4, 64…
    ## $ table   <dbl> 55, 61, 65, 58, 58, 57, 57, 55, 61, 61, 55, 56, 61, 54, 62, 58…
    ## $ price   <int> 326, 326, 327, 334, 335, 336, 336, 337, 337, 338, 339, 340, 34…
    ## $ x       <dbl> 3.95, 3.89, 4.05, 4.20, 4.34, 3.94, 3.95, 4.07, 3.87, 4.00, 4.…
    ## $ y       <dbl> 3.98, 3.84, 4.07, 4.23, 4.35, 3.96, 3.98, 4.11, 3.78, 4.05, 4.…
    ## $ z       <dbl> 2.43, 2.31, 2.31, 2.63, 2.75, 2.48, 2.47, 2.53, 2.49, 2.39, 2.…

``` r
diamonds %>%
  ggplot(
    mapping = aes(
      x = carat,
      y = price
  )) +
  geom_point()
```

![](c00-diamonds-assignment_files/figure-gfm/q1-task-1.png)<!-- -->

**Observations**:

- In general, the higher the carat the higher the price.
- There are more diamonds at a lower carat and lower price than higher
  carat and higher price.

### **q2** Create a visualization showing variables `carat`, `price`, and `cut` simultaneously. Experiment with which variable you assign to which aesthetic (`x`, `y`, etc.) to find an effective visual.

``` r
## TASK: Plot `price`, `carat`, and `cut` below
diamonds %>%
  ggplot(
    mapping = aes(
      x = carat, 
      y = price, 
      colour = cut)
    ) + 
  geom_point()
```

![](c00-diamonds-assignment_files/figure-gfm/q2-task-1.png)<!-- -->

**Observations**:

- In general for diamonds of the same carat, a higher quality cut will
  lead to a higher price.
- Diamonds of carats over 3 have high prices with varied cut quality.
- There are more diamonds at a lower carat and lower price than higher
  carat and higher price.
- 

# Communication

<!-- -------------------------------------------------- -->

In this next stage, you will render your data exploration, push it to
GitHub to share with others, and link your observations within our [Data
Science
Wiki](https://olin-data-science.fandom.com/wiki/Olin_Data_Science_Wiki).

### **q3** *Knit* your document in order to create a report.

You can do this by clicking the “Knit” button at the top of your
document in RStudio.

<figure>
<img src="./images/c00-knit.png" alt="Terminal" />
<figcaption aria-hidden="true">Terminal</figcaption>
</figure>

This will create a local `.md` file, and RStudio will automatically open
a preview window so you can view your knitted document.

### **q4** *Push* your knitted document to GitHub.

<figure>
<img src="./images/c00-unstaged.png" alt="Terminal" />
<figcaption aria-hidden="true">Terminal</figcaption>
</figure>

You will need to stage both the `.md` file, as well as the `_files`
folder. Note that the `_files` folder, when staged, will expand to
include all the files under that directory.

<figure>
<img src="./images/c00-staged.png" alt="Terminal" />
<figcaption aria-hidden="true">Terminal</figcaption>
</figure>

### **q5** *Submit* your work to Canvas

Navigate to your GitHub repository’s website and find the URL that
corresponds to your report. Submit this to Canvas to complete the
assignment.

### **q6** *Prepare* to present your team’s findings!

If your team is on-deck, you are responsible for putting together a
discussion of the challenge. I’ll demonstrate how to do this by leading
the discussion of Challenge 0.
