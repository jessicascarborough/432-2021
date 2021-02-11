# 432 Class 04: 2021-02-11

[Main Website](https://thomaselove.github.io/432/) | [Calendar](https://thomaselove.github.io/432/calendar.html) | [Syllabus](https://thomaselove.github.io/432-2021-syllabus/) | [Course Notes](https://thomaselove.github.io/432-notes/) | [Canvas](https://canvas.case.edu) | [Data and Code](https://github.com/THOMASELOVE/432-data) | [Sources](https://github.com/THOMASELOVE/432-2021/edit/master/references) | [Contact Us](https://thomaselove.github.io/432/contact.html)
:-----------: | :--------------: | :----------: | :---------: | :-------------: | :-----------: | :------------: | :-------------:
for everything | deadlines | expectations | from Dr. Love | zoom info | downloads | read/watch | need help?

![](https://imgs.xkcd.com/comics/hug_count.png) from [XKCD](https://xkcd.com/2419/)

## Materials for Today's Class

- Today's Slides are now [available in PDF](https://github.com/THOMASELOVE/432-2021/blob/master/classes/class04/432_2021_slides04.pdf), as well as in [R Markdown](https://github.com/THOMASELOVE/432-2021/blob/master/classes/class04/432_2021_slides04.Rmd).
    - We'll pick up where we left off in Class 3. I've incorporated the key parts of what we did then, and then built augmented versions of what I'd planned, all into this new deck, so it should stand on its own.
- All 432 classes are video-recorded, and the recordings will be archived in the Zoom section of [Canvas](https://canvas.case.edu).

## Announcements

1. [Dr. Love's feedback for the Minute Paper after Class 03](http://bit.ly/432-2021-min03-feedback) is now available.
2. If you're looking for more information about restricted cubic splines after today's discussion, try Frank E. Harrell and Chris Slaughter [Biostatistics for Biomedical Research Notes](http://hbiostat.org/doc/bbr.pdf) (pdf).
3. The American Statistical Association has a new monthly podcast called [Practical Significance](https://magazine.amstat.org/podcast-2), meant to inspire listeners with compelling stories from statistics and data science and to propel data-driven careers forward with learning opportunities for all. The latest episode ([Episode 2](https://magazine.amstat.org/podcast-2/), entitled How to Become a JEDI) is about the ASA's Anti-Racism Task Force, and its outreach group to address justice, equity, diversity and inclusion (JEDI).
    - ASA's complete [roster of sponsored podcasts can be found here](https://magazine.amstat.org/blog/2021/02/01/asa-sponsored-podcasts/).
4. A new monthly Zoom lecture series on social determinants of health, led by my colleague Dr. Ash Sehgal at [MetroHealth](https://www.metrohealth.org/) and the [Institute for H.O.P.E.](https://www.metrohealth.org/institute-for-hope) starts soon. [This two-page flyer](https://github.com/THOMASELOVE/432-2021/blob/master/classes/class04/figures/SDOH_Seminar_Series_2021_March_and_April.pdf) describes the sessions and speakers for 2021-03-01 (Laura Gottlieb) and 2021-04-05 (Rishi Manchanda).
5. Boston University and the Society for Epidemiologic Research are hosting a 3 part webinar series called  "[Epidemiology and Race: Why and How We Study Racial Health Disparities](https://www.bu.edu/sph/conversations/uncategorized/part-1-epidemiology-and-race-why-and-how-we-study-racial-health-disparities/)". The sessions are on 2021-02-25 and 2021-02-26 and registration is required.
6. We will be learning a fair amount about the [tidymodels ecosystem](https://www.tidymodels.org/) (of which broom, rsample and yardstick are parts) in the sessions to come (really starting around Class 7 or 8), and that provides an excellent schematic for lots of statistical learning engines besides `lm`. The [tidymodels book](https://www.tmwr.org/) by Max Kuhn and Julia Silge will be a helpful follow-up resource for what we'll be doing. I just learned that Max Kuhn, one of the authors of that book, will be presenting at [a Cleveland R Meetup session on TidyModels from 6 to 7:30 PM on 2021-02-24](https://www.meetup.com/Cleveland-UseR-Group/events/273725112/). If you're interested, [go here to register (for free) and attend](https://www.meetup.com/Cleveland-UseR-Group/events/273725112/).

## Running a Data Set Past Us for Project 1

To get Dr. Love and the TAs to "sign off" on a data set as appropriate for your project 1 proposal, you need to tell us five things in a (private or public - your choice) note on Piazza in the project1 folder:

1. the data source, as described [here in item 1 in the proposal instructions](https://github.com/THOMASELOVE/432-2021/blob/master/project1/01_project1_proposal.md#1-data-source) along with a URL so we can access the data
2. a description of who the subjects are and how they were selected, as described [here in item 2 in the proposal instructions](https://github.com/THOMASELOVE/432-2021/blob/master/project1/01_project1_proposal.md#2-the-subjects) - it helps if you also tell us how many subjects are in the data
3. what quantitative outcome you plan to use in your linear regression model, including its units of measurement and the minimum, mean and maximum values available in your data
4. what binary outcome you plan to use in your logistic regression model, specifying both of the mutually exclusive and collectively exhaustive categories and how many subjects fall into each of those two categories.
5. that you've carefully read the [what makes an acceptable data set section of the project 1 instructions](https://github.com/THOMASELOVE/432-2021/blob/master/project1/00_project1_general.md#3-what-makes-an-acceptable-data-set) and can confirm that your data meets all of those specifications.

Also, we ask that you not ask us to pick between two "options" - submit the one you'd rather do. If it's a problem, we'll let you know, and you can then change to another option if necessary.

## from [rstudio::global(2021)](https://rstudio.com/resources/rstudioglobal-2021) 

Today, I'll share Kara Woo's terrific 22-minute talk [Always look on the bright side of plots](https://rstudio.com/resources/rstudioglobal-2021/always-look-on-the-bright-side-of-plots/). 

- Everyone who creates visualizations in R is bound to make mistakes that prevent their plots from looking as they should. Sometimes, these mistakes create beautiful "accidental aRt", though other times they're just plain frustrating. Either way, however, there's something to be learned.

## Reminders

1. A reminder to take advantage of the relative lull coming up this weekend in 432 work to look closely at the requirements of [Project 1](https://github.com/THOMASELOVE/432-2021/tree/master/project1) and in particular, the [Project 1 Proposal](https://github.com/THOMASELOVE/432-2021/blob/master/project1/01_project1_proposal.md) which is due on 2021-03-01. See our [comments in the Class 3 README](https://github.com/THOMASELOVE/432-2021/tree/master/classes/class03) on this subject.
    - It is never a bad idea to run a project data set past Dr. Love and/or the TAs via Piazza or Office Hours. 
    - To quickly assess your data, we need to know the data source (including a URL where we can see the data) and we need to know what variables you're intending to use as outcomes, and the variables you intend to use as predictors.
2. [Lab 2](https://github.com/THOMASELOVE/432-2021/tree/master/labs/lab02) is the next substantial assignment, due at 9 PM on 2021-02-22.

## One Last Thing

Enjoy your weekend.

![](https://github.com/THOMASELOVE/432-2021/blob/master/classes/class04/figures/alejo_tw.png)
