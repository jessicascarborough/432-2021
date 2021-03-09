432 Lab 04 for Spring 2021
================

Version: 2021-03-08 09:03:23

# General Instructions

Submit your work via [Canvas](https://canvas.case.edu/). The deadline is
specified on [the Course
Calendar](https://thomaselove.github.io/432/calendar.html).

Your response should include an R Markdown file and an HTML document
that responds to all questions. that is the result of applying your R
Markdown file to the `oh_counties_2020.csv` data.

Start a separate R Project for Lab 04, as your first step, and place the
data in that project’s directory or (if you want to match what I did) in
a data sub-directory under that project’s directory.

We encourage you to make use of one of the templates we’ve provided for
a previous Lab, or use an approach that works well for you.

# Question 1 (20 points)

I have provided three essay prompts below. Select **one** of the three
available prompts and answer it. Start the essay by clearly identifying
the prompt you are using. We are looking for well-written, clear and
thoughtful responses. Going a little over the suggested length is OK.
Under is not OK.

## Prompt A

In the section on scientific blogging in Jeff Leek’s *How to Be A Modern
Scientist*, he remarks that “Everyone is an internet scientist now.” In
5-10 complete English sentences, I want you to specify, using your own
words and complete English sentences, one or two different ways in which
you anticipate your work changing in light of this remark. What might
you do differently, if you thought of yourself as an internet scientist?
Do you, already, feel this way? Does this make being a scientist seem
more or less appealing to you, and why? Please feel encouraged to
provide an example from your own experiences that helps you explain your
reactions to this idea.

## Prompt B

In 5-10 complete English sentences, I want you to specify, using your
own words and complete English sentences, the least helpful piece of
advice you took away from reading Jeff Leek’s *How To Be A Modern
Scientist*. Please provide a reference to the section of the book that
provides this problematic advice. Please avoid selecting something
because it does not apply to your current situation, but instead
identify something that might be relevant to you, but that you are
actually unwilling to do, and explain why. Please feel encouraged to
provide an example from your own experiences that helps you explain why
you are unwilling to take this piece of advice.

## Prompt C

Reread the section of Jeff Leek’s *How To Be A Modern Scientist* on data
sharing, where, among other things, he states that “the reproducibility
debate is over.” In 5-10 complete English sentences, I want you to
specify how the “debate” over reproducibility has affected your field,
and what changes you have made (or intend to make) in light of what
you’ve learned in this course, from Leek’s book, and from your
experiences over the last year to make your work more reproducible. How
important is building reproducible science in your field? In your view,
what does “reproducible science” mean to you, and to the people you will
be working with as you complete your degree program? Please feel
encouraged to provide an example from your own experiences that helps
you explain your reactions to the notion of reproducible science.

# Data Set Description for Questions 2-4 (repeated from Lab 02)

The `oh_counties_2020.csv` data set I have provided describes a series
of variables, pulled from the data for the 88 counties of the the State
of Ohio from the [County Health
Rankings](http://www.countyhealthrankings.org/rankings/data/oh) report
for 2020.

-   We used these data back in Lab 02, also.
-   Several detailed County Health Rankings files augment these 2020
    Ohio Rankings Data. Find [those items
    here](https://www.countyhealthrankings.org/app/ohio/2020/downloads)
    if you’re interested.

The available variables are listed below. Each variable describes data
at the **COUNTY** level.

|        Variable        | Description                                                                                                                        |
|:----------------------:|------------------------------------------------------------------------------------------------------------------------------------|
|         `fips`         | Federal Information Processing Standard code                                                                                       |
|        `county`        | name of County                                                                                                                     |
|   `years_lost_rate`    | age-adjusted years of potential life lost rate (per 100,000 population)                                                            |
|    `sroh_fairpoor`     | % of adults reporting fair or poor health (via BRFSS)                                                                              |
|      `phys_days`       | mean number of reported physically unhealthy days per month                                                                        |
|      `ment_days`       | mean number of reported mentally unhealthy days per mo                                                                             |
|       `lbw_pct`        | % of births with low birth weight (&lt; 2500 grams)                                                                                |
|      `smoker_pct`      | % of adults that report currently smoking                                                                                          |
|      `obese_pct`       | % of adults that report body mass index of 30 or higher                                                                            |
|       `food_env`       | indicator of access to healthy foods, in points (0 is worst, 10 is best)                                                           |
|     `inactive_pct`     | % of adults that report no leisure-time physical activity                                                                          |
|     `exer_access`      | % of the population with access to places for physical activity                                                                    |
|      `exc_drink`       | % of adults that report excessive drinking                                                                                         |
|      `alc_drive`       | % of driving deaths with alcohol involvement                                                                                       |
|       `sti_rate`       | Chlamydia cases / Population x 100,000                                                                                             |
|     `teen_births`      | Teen births / females ages 15-19 x 1,000                                                                                           |
|      `uninsured`       | % of people under age 65 without insurance                                                                                         |
|      `pcp_ratio`       | Population to Primary Care Physicians ratio                                                                                        |
|      `prev_hosp`       | Discharges for Ambulatory Care Sensitive Conditions/Medicare Enrollees x 1,000                                                     |
|       `hsgrads`        | High School graduation rate                                                                                                        |
|      `unemployed`      | % of population age 16+ who are unemployed and looking for work                                                                    |
|      `poor_kids`       | % of children (under age 18) living in poverty                                                                                     |
|     `income_ratio`     | Ratio of household income at the 80th percentile to income at the 20th percentile                                                  |
|     `associations`     | \# of social associations / population x 10,000                                                                                    |
|        `pm2.5`         | Average daily amount of fine particulate matter in micrograms per cubic meter                                                      |
|       `h2oviol`        | Presence of a water violation: Yes or No                                                                                           |
|     `sev_housing`      | % of households with at least 1 of 4 housing problems: overcrowding, high housing costs, or lack of kitchen or plumbing facilities |
|     `drive_alone`      | % of workers who drive alone to work                                                                                               |
|  `age.adj.mortality`   | premature age-adjusted mortality                                                                                                   |
|       `dm_prev`        | % with a diabetes diagnosis                                                                                                        |
|  `freq_phys_distress`  | % in frequent physical distress                                                                                                    |
| `freq_mental_distress` | % in frequent mental distress                                                                                                      |
|    `food_insecure`     | % who are food insecure                                                                                                            |
|     `insuff_sleep`     | % who get insufficient sleep                                                                                                       |
|    `median_income`     | estimated median income                                                                                                            |
|      `population`      | population size                                                                                                                    |
|      `age65plus`       | % of population who are 65 and over                                                                                                |
|      `african-am`      | % of population who are African-American                                                                                           |
|       `hispanic`       | % of population who are of Hispanic/Latino ethnicity                                                                               |
|        `white`         | % of population who are White                                                                                                      |
|        `female`        | % of population who are Female                                                                                                     |
|        `rural`         | % of people in the county who live in rural areas                                                                                  |

## Loading the Data

Here’s a listing of the resulting tibble.

``` r
library(here)
library(janitor)
library(tidyverse)

oh20 <- read_csv(here("data", "oh_counties_2020.csv")) 

oh20 <- oh20 %>%
    clean_names() %>%
    type.convert() %>%
    mutate(fips = as.character(fips))

oh20
```

    # A tibble: 88 x 43
       fips  state county  years_lost_rate sroh_fairpoor phys_days ment_days lbw_pct
       <chr> <fct> <fct>             <int>         <dbl>     <dbl>     <dbl>   <dbl>
     1 39001 Ohio  Adams             12223          22.3      4.94      4.83    9.05
     2 39003 Ohio  Allen              9037          16.5      4.12      4.4     9.35
     3 39005 Ohio  Ashland            7483          16.8      4.09      4.47    5.96
     4 39007 Ohio  Ashtab~           10013          16.8      4.18      4.57    8.16
     5 39009 Ohio  Athens             7014          20.6      4.66      4.92    8.55
     6 39011 Ohio  Auglai~            6454          14.6      3.73      4.27    7.32
     7 39013 Ohio  Belmont            8289          18.0      3.87      4.46    8.34
     8 39015 Ohio  Brown             10748          17.3      4.19      4.58    7.39
     9 39017 Ohio  Butler             9429          16.5      4         4.14    7.99
    10 39019 Ohio  Carroll            8073          16.2      4.08      4.39    7.61
    # ... with 78 more rows, and 35 more variables: smoker_pct <dbl>,
    #   obese_pct <dbl>, food_env <dbl>, inactive_pct <dbl>, exer_access <dbl>,
    #   exc_drink <dbl>, alc_drive <dbl>, sti_rate <dbl>, teen_births <dbl>,
    #   uninsured <dbl>, pcp_ratio <int>, prev_hosp <dbl>, hsgrads <dbl>,
    #   unemployed <dbl>, poor_kids <dbl>, income_ratio <dbl>, associations <dbl>,
    #   pm2_5 <dbl>, h2oviol <fct>, sev_housing <int>, drive_alone <int>,
    #   age_adj_mortality <dbl>, dm_prev <dbl>, freq_phys_distress <dbl>,
    #   freq_mental_distress <dbl>, food_insecure <dbl>, insuff_sleep <dbl>,
    #   median_income <int>, population <int>, age65plus <dbl>, african_am <dbl>,
    #   hispanic <dbl>, white <dbl>, female <dbl>, rural <dbl>

**Note**: We’ll remind you that there was a Hint for Lab 02 on Piazza
(note @89 there) having to do with ingesting these data and the
importance of cleaning the names which is available in both the `lab02`
and `lab04` Piazza folders.

## Important Note for Questions 2-4

For Questions 2-4, you’re going to develop a series of models using
**86** of the counties (every county other than Cuyahoga County and
Monroe County). In each case, you will fit and select a model using that
sample of 86 counties, and then be asked to use that model to make
predictions of the outcome of interest for Cuyahoga County and for
Monroe County and to assess the quality of those predictions.

# Question 2 (20 points)

Build a reasonable linear or generalized linear model in your
development sample (86 counties) to predict one of the outcomes in the
`oh_counties_2020.csv` data set that describes a percentage (that must
fall between 0 and 100) effectively using at least three and no more
than 6 other variables from the list above. Demonstrate how well the
model fits as well as the conclusions you draw from the model carefully.
Be sure to discuss model assumptions. Then use the model to predict
Cuyahoga County and Monroe County results, and assess the quality of
those predictions. Note well that the goal here is to fit and evaluate a
single model. There’s no reason to be using an automated variable
selection procedure in this setting.

# Question 3 (30 points)

Divide the 86 counties in your development sample into three groups
(low, middle and high) in a rational way in terms of the
`years_lost_rate` outcome. Make that new grouping your outcome for an
ordinal logistic regression model. Fit a model (using a carefully
selected group of no more than 5 predictor variables) and assess its
performance carefully. Do not include the `age65plus` variable as a
predictor, as the `years_lost_rate` data are age-adjusted already.
Demonstrate how well the model fits as well as the conclusions you draw
from the model carefully. Then use the model to predict Cuyahoga County
and Monroe County results, and assess the quality of those predictions.

## A Hint (for Questions 3 and 4, in particular)

`polr` and several of the other modeling approaches we’ve worked on
recently are finicky, at least in comparison to OLS. Sometimes, you’ll
get to the point where it seems like the model won’t run, or won’t
summarize properly, or you have some extremely large or extremely small
coefficient estimates or standard errors. Should this happen to you, the
first thing I would do is try to identify which of your predictors is
causing this problem, by running the model first with one predictor,
then two, etc. until you figure out which predictors cause problems.
Reasons why you could be having a problem include:

1.  a predictor has values that completely identify the category of your
    outcome variable, perfectly (e.g., one category’s predictor values
    are inevitably lower than all of another category’s predictor
    values, with no overlap)
2.  the scales of the predictors are wildly different, for instance one
    predictor has extremely large or extremely small values, causing the
    estimated standard errors to explode, which should cause you to
    think about reducing the impact of that, perhaps by changing the
    units, say from $s to $1000s or by normalizing the predictors
3.  intense collinearity between two or more of your predictors
4.  coding issues in setting up one or more of the variables.

For example, some people in the past have tried to use `median_income`
in their models along with other variables that have much smaller scales
(ranges). I would try rescaling those predictors with large ranges to
have similar magnitudes to the other predictors, perhaps simply by
expressing the median income in thousands of dollars (by dividing the
raw data by 1000) rather than on its original scale, or perhaps by
normalizing all of the coefficients by subtracting their means and
dividing by their standard deviations.

As another example, some people in the past tried using age-adjusted
mortality to predict years lost rate, but if you divide the years lost
rate into several ordinal categories, it’s not hard to wind up in a
situation where age-adjusted mortality is perfectly separated, so that
if you know the mortality, it automatically specifies the years lost
rate category in these data.

# Question 4 (30 points)

Build a new outcome variable that is a count (possible values = 0-4) of
whether the county meets each of the following standards:

-   the county has a `sroh_fairpoor` value **below** the Ohio-wide mean
    of 17.15
-   the county has an `obese_pct` value **below** the Ohio-wide average
    of 34.32
-   the county has an `exer_access` value **above** the Ohio-wide
    average of 67.76
-   the county has **NOT** had a water violation in the past year (as
    shown by `h2oviol` = No)

Among the 86 counties (excluding Cuyahoga and Monroe) you should find 5
counties which meet 0 of these standards, 16 which meet 1, 31 which meet
2, 19 which meet 3 and 15 which meet all 4.

To illustrate, consider these five counties:

|     County | `sroh_fairpoor` | `obese_pct` | `exer_access` | `h2oviol` | Standards Met |
|-----------:|----------------:|------------:|--------------:|----------:|--------------:|
| *Standard* |      &lt; 17.15 |  &lt; 34.32 |    &gt; 67.76 |        No |             – |
|   Guernsey |           18.66 |        36.4 |          50.7 |       Yes |             0 |
|    Belmont |           18.02 |          35 |          47.4 |    **No** |             1 |
|      Adams |            22.3 |    **32.2** |          41.7 |    **No** |             2 |
|    Ashland |       **16.79** |    **33.3** |            60 |    **No** |             3 |
|      Allen |        **16.5** |      **34** |      **75.8** |    **No** |             4 |

Your job is to fit **two** possible regression models in your
development sample to predict this count, using the same predictors (at
least 3 and no more than 6 of those not used in the calculation of
standards) available in the data set. Demonstrate how well each model
fits the counts by developing a rootogram and other summaries that you
deem useful, then select the model you prefer, specifying your reasons.
Next, use your preferred model to predict Cuyahoga County and Monroe
County results, and assess the quality of those predictions.

### Please add the session information.

Finally, at the end of this homework and all subsequent assignments
(including the projects), please add the session information. You can
either use the usual `sessioninfo::session_info()` approach, or else
use…

``` r
xfun::session_info()
```

### This is the end of Lab 04.
