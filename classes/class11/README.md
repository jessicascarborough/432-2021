# 432 Class 11: 2021-03-11

[Main Website](https://thomaselove.github.io/432/) | [Calendar](https://thomaselove.github.io/432/calendar.html) | [Syllabus](https://thomaselove.github.io/432-2021-syllabus/) | [Course Notes](https://thomaselove.github.io/432-notes/) | [Canvas](https://canvas.case.edu) | [Data and Code](https://github.com/THOMASELOVE/432-data) | [Sources](https://github.com/THOMASELOVE/432-2021/edit/master/references) | [Contact Us](https://thomaselove.github.io/432/contact.html)
:-----------: | :--------------: | :----------: | :---------: | :-------------: | :-----------: | :------------: | :-------------:
for everything | deadlines | expectations | from Dr. Love | zoom info | downloads | read/watch | need help?

![](https://github.com/THOMASELOVE/432-2021/blob/master/classes/class11/figures/amira.png)

## Materials for Today's Class

- Today's Slides will be [available in PDF](https://github.com/THOMASELOVE/432-2021/blob/master/classes/class11/432_2021_slides11.pdf), as well as in [R Markdown](https://github.com/THOMASELOVE/432-2021/blob/master/classes/class11/432_2021_slides11.Rmd).
- All 432 classes are video-recorded, and the recordings will be archived in the Zoom section of [Canvas](https://canvas.case.edu).

We'll continue talking about the `tidymodels` packages today. I'll remind you of some useful supplemental learning resources.

1. Max Kuhn and Julia Silge's book [Tidy Modeling with R](https://www.tmwr.org/) which has been my main resource.
2. For videos with great `tidymodels` examples, try [Julia Silge's YouTube page](https://www.youtube.com/c/JuliaSilge/videos). I highlighted a few specific videos in the [Class 10 README](https://github.com/THOMASELOVE/432-2021/tree/master/classes/class10).
3. The [tidymodels website](https://www.tidymodels.org/), in particular the [Get Started](https://www.tidymodels.org/start/) tutorials, and the [Learn section](https://www.tidymodels.org/learn/).

## Announcements about 432

1. The [Class 08 Effects Note](https://github.com/THOMASELOVE/432-2021/tree/master/classes/class08) is now fixed. I fixed problems with the interpretations on old pages 9-11 of the prior version, and I fixed the display of nomograms and added some other helpful hints in my explanations. You want the version dated today.
    - Another identical copy of [the fixed version is here](https://github.com/THOMASELOVE/432-2021/blob/master/classes/class11/effects_note.pdf) (pdf) and [here](https://github.com/THOMASELOVE/432-2021/blob/master/classes/class11/effects_note.Rmd) (Rmd).
    - Please use [the fixed version](https://github.com/THOMASELOVE/432-2021/blob/master/classes/class11/effects_note.pdf) in all work going forward, especially your Project 1 and Lab 3. I've deleted the old version from our web site, but check the date to be sure.
2. Dr. Love's [Feedback on the Minute Paper after Class 10](http://bit.ly/432-2021-min10-feedback) is now available. Three things to add:
    - If you want an appealing discussion of some of the exciting things you can do with the `rms` and `Hmisc` packages, take a look at Nicholas Ollberding's [An Introduction to the Harrell-verse: Predictive Modeling using the Hmisc and rms Packages](https://www.nicholas-ollberding.com/post/an-introduction-to-the-harrell-verse-predictive-modeling-using-the-hmisc-and-rms-packages/).
    - There were lots of imputation questions, and I wrote a lot in response. You might like: [When and how should multiple imputation be used for handling missing data in randomised clinical trials – a practical guide with flowcharts](https://bmcmedresmethodol.biomedcentral.com/articles/10.1186/s12874-017-0442-1) by Janus Christian Jakobsen, Christian Gluud, Jørn Wetterslev & Per Winkel. I like the flowchart, at any rate. 
    - [Introduction to Bayesian Linear Regression: An explanation of the Bayesian approach to linear modeling](https://towardsdatascience.com/introduction-to-bayesian-linear-regression-e66e60791ea7) by Will Koehrsen seems like something many of you might be interested in, too, and I thought it was a nice read, pitched an approrpriate level.
3. [Lab 3](https://github.com/THOMASELOVE/432-2021/blob/master/labs/lab03/lab03_instructions.md) is due 2021-03-15 at 9 PM. Be sure to use the [current version of the instructions](https://github.com/THOMASELOVE/432-2021/blob/master/labs/lab03/lab03_instructions.md).
4. [Quiz A](https://github.com/THOMASELOVE/432-2021/tree/master/quizzes/quizA) will be available by noon tomorrow, and is due 2021-03-22 at 9 PM.
    - The Quiz includes materials from the first 9 classes, from Chapters 1-14 of the course notes, from all of Jeff Leek's *How to be a modern scientist* and from Nate Silver's *The Signal and the Noise* through Chapter 7. It does not include this week's `tidymodels` material.
    - The instructions for Quiz A [are already posted](https://github.com/THOMASELOVE/432-2021/tree/master/quizzes/quizA).
5. Your [Project 1 Portfolio and Presentation](https://github.com/THOMASELOVE/432-2021/blob/master/project1/02_project1_analyses.md) are due 2021-03-29 at 9 PM. You should be able to complete this work now.
6. Remember that next Tuesday 2021-03-16 is a University Break day, and so we will not have class. Our next Class (Class 12) will be held on 2021-03-18.
7. I will spend time in the next week thinking about what to do with my current plans for April and May, and whether some revision to that plan might be helpful, and I expect to announce whether there will be a revision in Class 12. I won't change anything on the Calendar for March. Stay tuned.

## Other Opportunities

1. If you're interested in another example of formulating a machine learning activity within the tidymodels framework (especially if you've previously worked with the `caret` package) you might enjoy [The simplest tidy machine learning workflow](https://www.r-bloggers.com/2020/02/the-simplest-tidy-machine-learning-workflow/) by Jorge Cimentada.
2. The next session in the CAUSE/Journal of Statistics and Data Science Education webinar series is 2021-03-23 at 4 PM. It features talks about two related papers on data ingestation, data collection, and data analysis. [Register or learn more here](https://psu.zoom.us/webinar/register/WN_aTtp-SdYRwi3pLvPkMEGMQ).
3. I missed highlighting the sad passing last month of [Dr. Arianna Wright Rosenbluth](https://www.nytimes.com/2021/02/09/science/arianna-wright-dead.html), who was a critical figure in data science, and programmed the Metropolis algorithm that is a fundamental part of the way we do sampling these days in many contexts.
4. If you work with people who think in Word, consider [Using Word Reference Documents with RMarkdown to Create Custom Reports](https://rfortherestofus.com/2020/07/word-reference-documents-rmarkdown/)

## One Last Thing

It's probably time to trot this out again, from [XKCD](https://xkcd.com/2048/)...

![](https://imgs.xkcd.com/comics/curve_fitting.png)


