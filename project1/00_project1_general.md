432 Project 1: General Instructions
================

-   [1 Introduction](#introduction)
-   [2 Project 1 involves two tasks](#project-1-involves-two-tasks)
-   [3 What Makes an Acceptable Data
    Set?](#what-makes-an-acceptable-data-set)
-   [4 Submission Information and
    Deadlines](#submission-information-and-deadlines)
-   [5 Can I work with a partner?](#can-i-work-with-a-partner)
-   [6 Getting Help](#getting-help)
-   [Links](#links)

Last Update: 2021-01-28 22:42:19

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

In Task 1 (which you’ll do in February), you will develop a **project
proposal**, due at the start of March.

-   This part of the project involves selecting data, ingesting it into
    R and cleaning it, then describing the data.
-   We have [provided several templates](#links) for this work, any one
    of which you should use to facilitate your interactions with R
    Markdown.

In Task 2 (which you’ll do in March), you will **develop analyses and
present your results**, and this is due near the end of March.

-   The work you’ll do in March will involve analyzing the data, fitting
    and displaying models, and putting together your presentation.
-   Task 2 builds on Task 1 considerably, and the same
    [templates](#links) will be useful for both Tasks.

[Detailed Instructions for each Task](#links) are linked at the bottom
of this page.

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
    -   In submitting your proposal, you will need to be able to write
        “I am certain that it is completely appropriate for these data
        to be shared with anyone, without any conditions. There are no
        concerns about privacy or security.” So be sure that’s true
        before you pick a data set.
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
Canvas](https://canvas.case.edu/). Details on what you need to submit
are specified in the [detailed instructions for each Task](#links).

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

# Links

-   Detailed [Instructions for Project 1 Task 1 (The
    Proposal)](https://github.com/THOMASELOVE/432-2021/blob/master/project1/01_project1_proposal.md)
-   [Templates for Project
    1](https://github.com/THOMASELOVE/432-2021/tree/master/project1/templates)
-   Detailed [Instructions for Project 1 Task 2 (Analyses and
    Presentation)](https://github.com/THOMASELOVE/432-2021/blob/master/project1/02_project1_analyses.md)
-   [Main Page for Project
    1](https://github.com/THOMASELOVE/432-2021/tree/master/project1)
