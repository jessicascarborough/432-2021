# 432 Class 07: 2021-02-23

[Main Website](https://thomaselove.github.io/432/) | [Calendar](https://thomaselove.github.io/432/calendar.html) | [Syllabus](https://thomaselove.github.io/432-2021-syllabus/) | [Course Notes](https://thomaselove.github.io/432-notes/) | [Canvas](https://canvas.case.edu) | [Data and Code](https://github.com/THOMASELOVE/432-data) | [Sources](https://github.com/THOMASELOVE/432-2021/edit/master/references) | [Contact Us](https://thomaselove.github.io/432/contact.html)
:-----------: | :--------------: | :----------: | :---------: | :-------------: | :-----------: | :------------: | :-------------:
for everything | deadlines | expectations | from Dr. Love | zoom info | downloads | read/watch | need help?

![](https://github.com/THOMASELOVE/432-2021/blob/master/classes/class07/figures/spear_tw.png)

The [Credit Where Credit is Due article on Mary Eleanor Spear is here](https://medium.com/nightingale/credit-where-credit-is-due-mary-eleanor-spear-6a7a1951b8e6), and check out [her Wikipedia page](https://en.wikipedia.org/wiki/Mary_Eleanor_Spear) as well, if you like.

## Materials for Today's Class

- Today's Slides are [available in PDF](https://github.com/THOMASELOVE/432-2021/blob/master/classes/class07/432_2021_slides07.pdf), as well as in [R Markdown](https://github.com/THOMASELOVE/432-2021/blob/master/classes/class07/432_2021_slides07.Rmd).
- All 432 classes are video-recorded, and the recordings will be archived in the Zoom section of [Canvas](https://canvas.case.edu).

## Announcements

1. There is a [Minute Paper after Class 07](https://github.com/THOMASELOVE/432-2021/tree/master/minutepapers). Please complete it by noon Wednesday 2021-02-24.
2. The [Project 1 Proposal](https://github.com/THOMASELOVE/432-2021/blob/master/project1/01_project1_proposal.md) is due at 9 PM Monday 2021-03-01. If you don't have a data set ingested into R yet, I'd get on that today.
    - A tip: when developing an outcome for a *logistic* regression model, frame it as a "1 = yes/0 = no" numeric variable in R for modeling purposes, even if it originally comes as a Yes/No or other type of character variable. We will want to see that you have such a variable in place in your proposal, and it's perfectly OK if you also want to have it in your data as a named factor as well (perhaps for plotting purposes?)
3. The [Answer Sketch for Lab 2](https://github.com/THOMASELOVE/432-2021/tree/master/labs/lab02) will be posted in time for today's class.

## Sources for Today's Class

We'll be discussing the tools for regression fitting and evaluation in the `rms` package (developed by Frank Harrell and colleagues) quite a bit over the next couple of weeks. 

- You may be interested in [An introduction to the Harrell verse](https://www.nicholas-ollberding.com/post/an-introduction-to-the-harrell-verse-predictive-modeling-using-the-hmisc-and-rms-packages/) by Nicholas Ollberding. 
- Quoting that work: "(The) `Hmisc` and `rms` packages link users to a much broader set of materials on modern statistical methods and computing including predictive modeling, estimation, hypothesis testing, and study design."

Two key book-length references from Frank are:

- Frank E. Harrell and Chris Slaughter [Biostatistics for Biomedical Research Notes](http://hbiostat.org/doc/bbr.pdf) (pdf).
- Frank E. Harrell [Regression Modeling Strategies](https://github.com/THOMASELOVE/432-2021/blob/master/references/pdf/Harrell_Regression_Modeling_Strategies_2015_2e_protected.pdf), 2nd Edition, 2015.

We won't get to these other references much today, but they'll come up going forward...

- [Spending our data](https://www.tmwr.org/splitting.html), which is a chapter in Max Kuhn and Julia Silge [Tidy Modeling with R](https://www.tmwr.org/).
- Peter C. Austin and Ewout W. Steyerberg (2015) [The number of subjects per variable required in linear regression analyses](https://github.com/THOMASELOVE/432-2021/blob/master/references/pdf/Austin_and_Steyerberg_2015_subjects_per_variable_in_linear_regression_jce.pdf) *J Clinical Epidemiology* 68: 627-636.
- Richard D Riley, Joie Ensor, Kym I E Snell et al. [Calculating the sample size required for developing a clinical prediction model](https://github.com/THOMASELOVE/432-2021/blob/master/references/pdf/Riley_etal_2020_Sample_Size_Required.pdf) (pdf) *BMJ* 2020; 368:m441. [Link at BMJ](https://www.bmj.com/content/368/bmj.m441).

## One Last Thing

I'll link to a note and visualization by Jia You in *Science* from 2017-04-27 entitled "[Here's the visual proof of why vaccines do more good than harm](Here’s the visual proof of why vaccines do more good than harm)" in case you might be interested, as Ohio begins to announce its priorities for subsequent COVID-19 vaccination administration after the current group of people ages 65 and older.
