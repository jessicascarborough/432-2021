Instructions for 432 Project 1
================

-   [1 Introduction](#introduction)
-   [2 Project 1 involves two tasks](#project-1-involves-two-tasks)
-   [3 What Makes an Acceptable Data
    Set?](#what-makes-an-acceptable-data-set)
-   [4 Submission Information and
    Deadlines](#submission-information-and-deadlines)
-   [5 Can I work with a partner?](#can-i-work-with-a-partner)
-   [6 Getting Help](#getting-help)
-   [7 Detailed Instructions for Task 1 (The
    Proposal)](#detailed-instructions-for-task-1-the-proposal)
    -   [7.1 At the Start](#at-the-start)
        -   [7.1.1 Use one of the templates!](#use-one-of-the-templates)
        -   [7.1.2 Title and Authors](#title-and-authors)
        -   [7.1.3 R Packages, Setup, General
            Tips](#r-packages-setup-general-tips)
    -   [7.2 Proposal Section 1. Data
        Source](#proposal-section-1.-data-source)
    -   [7.3 Proposal Section 2. The
        Subjects](#proposal-section-2.-the-subjects)
    -   [7.4 Proposal Section 3. Loading and Tidying the
        Data](#proposal-section-3.-loading-and-tidying-the-data)
        -   [7.4.1 Proposal Section 3.1. Loading the Raw
            Data](#proposal-section-3.1.-loading-the-raw-data)
        -   [7.4.2 Proposal Sections 3.2. and
            beyond](#proposal-sections-3.2.-and-beyond)
    -   [7.5 Proposal Section 4. The Tidy
        Tibble](#proposal-section-4.-the-tidy-tibble)
        -   [7.5.1 Proposal Section 4.1 Listing the
            Tibble](#proposal-section-4.1-listing-the-tibble)
        -   [7.5.2 Proposal Section 4.2 Size and
            Identifiers](#proposal-section-4.2-size-and-identifiers)
        -   [7.5.3 Proposal Section 4.3 Save the tidied tibble as an
            .Rds
            file](#proposal-section-4.3-save-the-tidied-tibble-as-an-.rds-file)
    -   [7.6 Proposal Section 5. The Code
        Book](#proposal-section-5.-the-code-book)
        -   [7.6.1 Proposal Section 5.1 Defining the
            Variables](#proposal-section-5.1-defining-the-variables)
        -   [7.6.2 Proposal Section 5.2 Describing the
            Tibble](#proposal-section-5.2-describing-the-tibble)
    -   [7.7 Proposal Section 6. Linear Regression
        Plans](#proposal-section-6.-linear-regression-plans)
        -   [7.7.1 Proposal Section 6.1 The Planned
            Outcome](#proposal-section-6.1-the-planned-outcome)
        -   [7.7.2 Proposal Section 6.2 The Inputs
            (Predictors)](#proposal-section-6.2-the-inputs-predictors)
    -   [7.8 Proposal Section 7. Logistic Regression
        Plans](#proposal-section-7.-logistic-regression-plans)
        -   [7.8.1 Proposal Section 7.1 The Planned
            Outcome](#proposal-section-7.1-the-planned-outcome)
        -   [7.8.2 Proposal Section 7.2 The Inputs
            (Predictors)](#proposal-section-7.2-the-inputs-predictors)
    -   [7.9 Proposal Section 8.
        Affirmation](#proposal-section-8.-affirmation)
    -   [7.10 Proposal Section 9.
        References](#proposal-section-9.-references)
    -   [7.11 Proposal Section 10. Session
        Information](#proposal-section-10.-session-information)
-   [8 Submission requirements](#submission-requirements)
-   [9 How Will We Evaluate the
    Proposal?](#how-will-we-evaluate-the-proposal)
-   [10 Detailed Instructions for Task 2 (Analysis and
    Presentation)](#detailed-instructions-for-task-2-analysis-and-presentation)

# 1 Introduction

It is hard to learn statistics (or anything else) passively; concurrent
theory and application are essential. Expert clinical researchers and
statisticians repeatedly emphasize how important it is that people be
able to write well, present clearly, work to solve problems, and show
initiative. This project assignment is designed to help you develop your
abilities and have a memorable experience.

In Project 1, you will be analyzing, presenting and discussing a pair of
regression models, specifically a linear regression and a logistic
regression, describing a data set you identify.

# 2 Project 1 involves two tasks

In task 1 (which you’ll do in February), you will develop a **project
proposal**, due at the start of March.

-   This part of the project involves selecting data, ingesting it into
    R and cleaning it, then describing the data.

In task 2 (which you’ll do in March), you will **develop analyses and
present your results**, and this is due near the end of March.

-   The work you’ll do in March will involve analyzing the data, fitting
    and displaying models, and putting together your presentation.

# 3 What Makes an Acceptable Data Set?

1.  **Shareable with the World**. The data must be available to you, and
    shared with me and everyone else in the world (without any
    identifying information) as a well-tidied .csv file on 2020-03-01.
    If the data is from another source, the source (web or other) must
    be completely identified to me. Ongoing projects that require
    anyone’s approval to share data are not appropriate for Project 1,
    but can be used (with Dr. Love’s approval) for Project 2.
    -   You should have the data in R by 2020-02-21, so that you will
        have sufficient time to complete the other elements of this
        proposal. Any data you cannot have by that time is a bad choice.
    -   For Project 1, you may not use any data set used in the 431 or
        432 teaching materials. You may not use any data set included in
        [an R package that we are
        installing](https://thomaselove.github.io/432/r_packages.html)
        this semester, other than NHANES.
    -   You must use meaningfully different data sets in 432 Projects 1
        and 2.
    -   You **are** allowed to use NHANES data in Project 1, but only if
        you are combining information from at least three NHANES data
        sets. If you used NHANES data in your 431 project, you can use
        NHANES data again in Project 1 for 432, but you must study new
        outcomes.
    -   You are permitted to use BRFSS data, but you are not permitted
        to use data from SMART BRFSS, since we will be using that
        regularly in class.
2.  **Size**.
    -   A **minimum** of 100 complete observations are required on each
        variable. It is fine if there are some missing values, as well,
        so long as there are at least 100 rows with complete
        observations on all variables you intend to use in each model.
    -   The **maximum** data set size is 1200 observations, so if you
        have something larger than that, you’ll need to select a random
        subset of the available information as part of your data tidying
        process.
3.  **Outcomes**. The columns must include at least one quantitative
    outcome and one binary categorical outcome.
    -   We prefer distinct outcomes, but if necessary, the binary
        outcome can be generated from the quantitative outcome (as an
        example, your quantitative outcome could be resting heart rate
        in beats per minute, and your binary outcome could be whether
        the resting heart rate is below 70 beats per minute.)
4.  **Inputs**. You will need at least four regression inputs
    (predictors) for each of your two models.
    -   At least one of the four must be quantitative (a variable is
        **not** quantitative for this purpose unless it has at least 10
        different, ordered, observed values), *and* at least one must be
        multi-categorical (with between 3 and 6 categories, each
        containing a minimum of 30 subjects) for each model.
    -   Your other inputs can represent binary, multi-categorical or
        quantitative data.
    -   You can examine different candidate predictors for each outcome,
        or use the same ones in both your linear and logistic regression
        models.
    -   Depending on your sample size, you can study more regression
        inputs. Specifically, if you have N complete observations in
        your data set, you are permitted to study up to 4 + (N-100)/100
        candidate regression inputs, rounding down.
5.  **No hierarchical data**. In project 1, we ask that you restrict
    yourself to cross-sectional data, where rows indicate subjects and
    columns indicate variables gathered to describe those subjects at a
    particular moment in time or space. Do not use “nested” or
    “longitudinal” data in this project.
    -   The singular exception to this rule is that it will usually be
        acceptable to use very limited longitudinal data, specifically,
        for all inputs to be collected at a single (baseline) time point
        and both outcomes to be collected at a single future point in
        time. For example, you could predict systolic blood pressure in
        2019 (or whether or not a subject’s systolic blood pressure in
        2019 was below 140), based on a set of input variables (likely
        including systolic blood pressure) all gathered in 2018.

If you have a question about whether a data set is appropriate for
Project 1, please feel free to ask it [via
Piazza](https://piazza.com/case/spring2021/pqhs432) using the
**project1** label.

# 4 Submission Information and Deadlines

All Project 1 work is to be submitted [via
Canvas](https://canvas.case.edu/).

Deadlines are found on the [Course
Calendar](https://thomaselove.github.io/432/calendar.html).

# 5 Can I work with a partner?

You can choose either to work alone, or with one other person, to
complete Project 1. If you work in a group for Project 1, you may be
asked to work alone for Project 2 later in the term.

-   You will need to identify your Project 1 partner as part of your
    proposal submission.
-   If you are working with a partner, all work must be submitted by
    exactly one of you to [Canvas](https::/canvas.case.edu) while the
    non-reporting partner submits a one-page note to Canvas indicating
    the members of the partnership and that the partner will submit the
    work.

# 6 Getting Help

If you have a question about whether a data set is appropriate for
Project 1 or anything else about Project 1, please feel free to ask it:

1.  [via Piazza](https://piazza.com/case/spring2021/pqhs432) using the
    **project1** label.
2.  at TA office hours
3.  directly of Professor Love before or after class (or, if necessary,
    via email, although we prefer Piazza)

# 7 Detailed Instructions for Task 1 (The Proposal)

## 7.1 At the Start

### 7.1.1 Use one of the templates!

We built three templates to make it easier to meet the requirements
specified here. You are not absolutely required to use a template, but
we very strongly recommend that you do, to avoid problems with missing
or hard-to-find information.

The three templates contain the same information, but use three
different styles. Pick the one that pleases you.

### 7.1.2 Title and Authors

Your project should have a meaningful title (not containing the words
“432” or “Project” or “Proposal”) but rather something describing your
actual data and plans.

-   Please keep the title to no more than 80 characters, including
    spaces.
-   Follow the guidance in the YAML code at the top of the template
    you’ve chosen to insert your title and author information.
-   Unless you really know what you’re doing, I would leave the rest of
    the YAML code alone.

### 7.1.3 R Packages, Setup, General Tips

You’ll load necessary packages at the start in an unnumbered section of
your work (follow the approach in the templates.)

-   Do not use `source("Love-boost.R")` or any other R script or package
    unless you actually need something it provides.
-   Do not load core elements of `tidyverse` or `tidymodels` (like
    `dplyr` or `ggplot2`) separately. instead just load the
    meta-packages, and do so last.
-   Use message = FALSE in the code chunk where the packages are listed
    to eliminate the messages in the HTML showing warnings about when
    packages were built or how objects were masked.
-   Do not use `echo = FALSE` anywhere in your R Markdown code.
-   Do use `knitr::opts_chunk$set(comment=NA)` in the setup chunk to
    avoid R output being preceded by hashtags.
-   Do use the ENTER key sufficiently to prevent any code chunks in the
    HTML file from requiring a scrolling window in order to be seen
    (note that this is a particularly common problem when people list
    many, many packages on the same line, separated by semicolons.)

The Proposal has 10 main sections, as described below.

## 7.2 Proposal Section 1. Data Source

Provide complete information on the source of the data: how did you get
it, how was it gathered, by whom, in what setting, for what purpose, and
using what sampling strategy.

## 7.3 Proposal Section 2. The Subjects

A description (one or two sentences should be sufficient) of who or what
the subjects (rows) are in your data set.

## 7.4 Proposal Section 3. Loading and Tidying the Data

### 7.4.1 Proposal Section 3.1. Loading the Raw Data

Provide code to ingest the raw data.

### 7.4.2 Proposal Sections 3.2. and beyond

Tidy and clean up the data to meet all necessary requirements for your
modeling work. This is likely to require multiple sub-sections as you
tackle different tasks for different sets of variables. Use the
tidyverse for data management whenever possible. Some of things you need
to do here…

-   Eliminate all variables that are not going to be used (either as
    identifiers, outcomes or inputs) in your planned analyses.
-   Change variable names to more meaningful ones, although it’s helpful
    to keep them at 10 characters or less. Use `clean_names()` from the
    `janitor` package as necessary to clean up and standardize variable
    names.
-   Sample the data as needed to ensure that you meet the data set size
    specifications (no more than 1200 rows, for instance.)
-   Convert all variables to appropriate types (factors, etc.) as
    needed, and complete appropriate checks of the values for all
    variables.
-   If you have prospective inputs (predictors) that are
    multi-categorical with more than 6 categories, collapse them to six
    or fewer categories in a rational way at this stage.
-   Ensure that all categorical variables have at least 30 observations
    at each level.
-   Your tidied data set at the end of this section should be arranged
    to adhere to the requirements for minimum and maximum number of rows
    and columns, with a row (subject) identifier at the far left. That
    identifier should have a unique value for each row, and should be
    saved as a character variable in R.
-   We expect your final tibble to have some missing values. Do not
    impute or delete these, but do be sure they are correctly identified
    as missing values by R.

**Note** Do not list the entire tibble or print out large strands of R
output (like summaries of the entire tibble) in this section.

## 7.5 Proposal Section 4. The Tidy Tibble

### 7.5.1 Proposal Section 4.1 Listing the Tibble

In this section, you should start by listing the tibble you created with
your work in Proposal Section 3, with all variables correctly imported
(via your code) as the types of variables (factor/integer/numeric, etc.)
that you need for modeling. This should be a listing, not a glimpse or
anything else.

### 7.5.2 Proposal Section 4.2 Size and Identifiers

Write a sentence specifying the number of rows and the number of columns
in your tibble, and this should match the R output.

Then identify the name of the variable that provides the identifier for
each row in your tidy tibble, and demonstrate that each row has a unique
value for that variable, and that the variable is represented as a
character in R.

-   One way to do this is to run the `n_distinct` function from the
    `dplyr` package on this particular variable.
-   Do not present summary or descriptive results on every variable in
    the whole tibble here - you’ll do that in Proposal Section 5.

### 7.5.3 Proposal Section 4.3 Save the tidied tibble as an .Rds file

Now, please save the tidied data set as an .Rds file (using saveRDS or
the equivalent), which you’ll need to submit to us.

## 7.6 Proposal Section 5. The Code Book

### 7.6.1 Proposal Section 5.1 Defining the Variables

In this section, provide a beautiful codebook which tells us (at a
minimum) the following information for each variable in the tibble you
printed and saved in Section 4.

1.  The name of the variable in your tibble.
2.  The role of the variable in your planned analyses (options include
    identifier, outcome, or input)
3.  The type of variable for each outcome or input (options are
    categorical, in which case tell us how many categories, or
    quantitative)
4.  A short description of the meaning of the variable.
    -   This should include the units of measurement if the variable is
        quantitative, and a list of the possible values if the variable
        is categorical.

As an example, here’s a part of a simple table:

| Variable    | Role       | Type  | Description                                    |
|-------------|------------|-------|------------------------------------------------|
| `subjectID` | identifier | \-    | character code for subjects                    |
| `sysbp`     | outcome    | quant | Most Recent Systolic Blood Pressure, in mm Hg  |
| `statin`    | input      | 2-cat | Has a current statin prescription? (Yes or No) |

### 7.6.2 Proposal Section 5.2 Describing the Tibble

Here, run the `describe` command from the `Hmisc` package on your entire
tibble. Be sure that the results match up with what you’ve described in
defining the variables, and that the same variables appear, in the same
order, in the codebook and in these results.

## 7.7 Proposal Section 6. Linear Regression Plans

### 7.7.1 Proposal Section 6.1 The Planned Outcome

This subsection tells us what you will use your linear regression model
to explain or predict.

-   Tell us the name in the tibble of the linear regression outcome you
    will use (this should one of the outcomes you identified earlier)
    and state why you are interested in predicting this variable.
-   Provide a count of the number of rows in your data with complete
    information on this outcome.
-   Provide a nicely labeled histogram or other graphical summary of
    your outcome to supplement the numerical description you provided in
    Proposal Section 5.2.
-   Comment briefly on the characteristics of the outcome’s
    distribution. Is your outcome skewed or symmetric, is it discrete or
    fairly continuous, is there a natural transformation to consider?
-   Ensure that the variable you have selected meets the standard for a
    quantitative variable used in this Project, specifically that it has
    at least 10 different, ordered, observed values.

### 7.7.2 Proposal Section 6.2 The Inputs (Predictors)

Now, tell us precisely which four (or more) candidate predictors you
intend to use for your linear regression model.

-   Please use the variable names that appear in your code book and
    tibble.
-   Demonstrate to us that you have at least one input which is
    quantitative, specifically that it has at least 10 different,
    ordered, observed values.
-   Demonstrate to us that you have at least one categorical input which
    has between 3 and 6 categories, that will be used as a factor in
    your modeling, and that has at least 30 observations in each level
    of the factor.
-   Demonstrate that the total number of candidate predictors you
    suggest is no more than 4 + (N-100)/100 candidate regression inputs,
    rounding down, where N is the sample size for your tibble.

## 7.8 Proposal Section 7. Logistic Regression Plans

### 7.8.1 Proposal Section 7.1 The Planned Outcome

This subsection tells us what you will use your logistic regression
model to explain or predict.

-   Tell us the name in the tibble of the logistic regression outcome
    you will use (this should one of the outcomes you identified
    earlier) and state why you are interested in predicting this
    variable.
-   Provide a count of the number of rows in your data with each of the
    two possible values of this outcome. Indicate whether you have any
    missing values.

### 7.8.2 Proposal Section 7.2 The Inputs (Predictors)

Now, tell us precisely which four (or more) candidate predictors you
intend to use for your logistic regression model. If you are using the
same predictors as in your linear regression model, you can write that
here and move on past this section.

## 7.9 Proposal Section 8. Affirmation

Next you need to affirm that the data set meets all of the project
requirements, especially that the data can be shared freely over the
internet, and that there is no protected information of any kind
involved.

You need to be able to write “I am certain that it is completely
appropriate for these data to be shared with anyone, without any
conditions. There are no concerns about privacy or security.” If you are
unsure whether this is true, select a different data set.

## 7.10 Proposal Section 9. References

References (you’ll need one to describe the source of your data, at
least) go here.

## 7.11 Proposal Section 10. Session Information

Please provide session information by running `xfun::session_info()`.
This will produce something like this…

``` r
xfun::session_info()
```

    R version 4.0.3 (2020-10-10)
    Platform: x86_64-w64-mingw32/x64 (64-bit)
    Running under: Windows 10 x64 (build 19041)

    Locale:
      LC_COLLATE=English_United States.1252 
      LC_CTYPE=English_United States.1252   
      LC_MONETARY=English_United States.1252
      LC_NUMERIC=C                          
      LC_TIME=English_United States.1252    

    Package version:
      base64enc_0.1.3 compiler_4.0.3  digest_0.6.27   evaluate_0.14  
      glue_1.4.2      graphics_4.0.3  grDevices_4.0.3 highr_0.8      
      htmltools_0.5.0 jsonlite_1.7.2  knitr_1.31      magrittr_2.0.1 
      markdown_1.1    methods_4.0.3   mime_0.9        rlang_0.4.9    
      rmarkdown_2.6   stats_4.0.3     stringi_1.5.3   stringr_1.4.0  
      tinytex_0.29    tools_4.0.3     utils_4.0.3     xfun_0.19      
      yaml_2.2.1     

# 8 Submission requirements

The proposal is to be submitted via file uploads to
[Canvas](https://canvas.case.edu). Your submitted proposal will include
the following:

1.  A raw data file (we prefer a `.csv` file) containing your raw data
    prior to any cleaning or tidying. This should be the file you load
    at the beginning of Proposal Section 3.1.
    -   Do not submit a raw data file with more than 5000 rows or with
        more than 25 columns. Should the original raw data available to
        you contain more than 5000 rows or more than 25 columns, reduce
        it in scope prior to building your Proposal document, and treat
        the “reduced” version as your “raw” version in what you include
        in your proposal and what you submit to us.
    -   Remember that your final “clean” data set is restricted in size
        even further, to no more than 1200 rows and also in terms of the
        number of columns.
    -   Should the original raw source of the data come in some other
        format besides `.csv`, you can either convert it to `.csv` or
        submit it in its original form, but if you take the latter
        course, you will need to provide complete code in your proposal
        to ingest the data into R.
    -   If your project uses an R package to extract raw data from the
        internet (for example, data from NHANES) then you will not
        submit a raw file here.
2.  A “tidied” R data set (saved in the .Rds format in Proposal Section
    4.3) containing your cleaned, tidy data obtained using the code you
    develop in the proposal.
    -   This tidied data set must include a subject identifier as the
        far left column saved as a character variable in R, followed by
        the outcomes you will use for the linear and logistic regression
        models, followed by your regression inputs in their final form,
        and then any other necessary variables.
    -   All variables which you plan to treat as factors should be saved
        as factors with appropriately ordered levels in your submitted R
        data set.
3.  An R Markdown file, built using one of our three available
    templates, which contains the information required in the proposal
    as described above.
    -   Please feel free to adapt the templates to produce a more
        visually appealing result, should that be of interest to you.
    -   If you decide to modify these templates, please retain the order
        of items in the table of contents to facilitate our finding what
        you did quickly.
4.  An HTML document which is the unedited result of knitting your
    submitted R Markdown file. This is the main document we will
    interact with in reviewing your proposal, so be sure to proofread it
    closely.

# 9 How Will We Evaluate the Proposal?

-   To evaluate your work, we will have to receive all necessary
    materials (raw data if needed, clean data as .Rds, .Rmd and HTML)
    successfully.
    -   If you are working with a partner, one of you must submit the
        proposal, and the other must submit a single-page text document
        (Word is fine) which states that their partner will submit the
        joint proposal, before we will evaluate your work.
-   We will evaluate each of the 10 main sections of the proposal. You
    will receive one point for each section that is successfully
    completed.
    -   The TAs will evaluate the proposals, using a rubric we will make
        available soon.
-   If you receive a grade lower than 10, we will specify the
    problematic sections and then you will have to redo the work
    (quickly) to fix the problems until we are satisfied.
-   One you have successfully completed all tasks, you will receive full
    credit for the proposal and can move on to the second task (Analysis
    and Presentation).

# 10 Detailed Instructions for Task 2 (Analysis and Presentation)

are coming soon.
