# 432 Class 02: 2021-02-04

[Main Website](https://thomaselove.github.io/432/) | [Calendar](https://thomaselove.github.io/432/calendar.html) | [Syllabus](https://thomaselove.github.io/432-2021-syllabus/) | [Course Notes](https://thomaselove.github.io/432-notes/) | [Canvas](https://canvas.case.edu) | [Data and Code](https://github.com/THOMASELOVE/432-data) | [Sources](https://github.com/THOMASELOVE/432-2021/edit/master/references) | [Contact Us](https://thomaselove.github.io/432/contact.html)
:-----------: | :--------------: | :----------: | :---------: | :-------------: | :-----------: | :------------: | :-------------:
for everything | deadlines | expectations | from Dr. Love | zoom info | downloads | read/watch | need help?

![](https://github.com/THOMASELOVE/432-2021/blob/master/classes/class02/figures/galvan_2020-11-17.png)

- Note that Tony also [shares his R code](https://twitter.com/GDataScience1/status/1328860920534106112?s=20) working with [data culled from Wikipedia](https://en.wikipedia.org/wiki/List_of_African-American_firsts).
- The most recent [TidyTuesday live screencast](https://www.youtube.com/watch?v=TSG74voJQ3E) from David Robinson looks at data about enrollment in historically black colleges and universities.

## Materials for Today's Class

- Today's Slides will be [available in PDF](https://github.com/THOMASELOVE/432-2021/blob/master/classes/class01/432_2021_slides02.pdf), as well as in [R Markdown](https://github.com/THOMASELOVE/432-2021/blob/master/classes/class01/432_2021_slides02.Rmd).
- All 432 classes are video-recorded, and the recordings will be archived in the Zoom section of [Canvas](https://canvas.case.edu).

## References for Today's Material

- Jonas Kristoffer Lindeløv's post [Common statistical tests are linear models](https://lindeloev.github.io/tests-as-linear/) makes the point that a wide range of "statistical tests" are just linear models, including all of the ANOVA and ANCOVA models we'll build today. While I don't refer to this within the slides, I was motivated by it in deciding to present these ideas exclusively through the lens of regression.

## Announcements

1. I placed a *Student List* of names, emails, pronouns, programs on our Shared Google Drive.
    - While looking at it (to be sure you're listed properly), you can also learn something interesting (lightly edited from the Welcome to 432 survey) about each of your colleagues.
2. Carrie Wright, Shannon Ellis, Stephanie Hicks, and Roger D. Peng have a new book out for sale (suggested price: $25) at LeanPub called [Tidyverse Skills for Data Science in R](https://leanpub.com/tidyverseskillsdatascience) which looks terrific, including some materials discussed in 431 and some we'll discuss this term.
3. If you're looking for a free tutorial to learn how to do something in R, I might suggest the [curated list at learnR4free](https://www.learnr4free.com/en/index.html).

## A little bit of inspiration

In each of the next few class READMEs, I've decided to spend a moment sharing one of the many great talks from the recent [rstudio::global(2021)](https://rstudio.com/resources/rstudioglobal-2021) conference. Today, I'll share Alex Cookson's 5-minute talk [The Power of Great Datasets](https://rstudio.com/resources/rstudioglobal-2021/the-power-of-great-datasets/). 

- I hope Alex will motivate you to curate Great Datasets and perhaps explore something you're not currently thinking about for a project or other activity to develop your statistical or programming skills. 

![](https://github.com/THOMASELOVE/432-2021/blob/master/classes/class02/figures/tufte_2020-06-27.png)

## One Last Thing - RStudio Tips

- Jānis Stūris at [Data Cornering](http://datacornering.com/) had a nice post back on 2020-01-01 of [My favorite RStudio tips and tricks](http://datacornering.com/my-favorite-rstudio-tips-and-tricks/) some of which would definitely save me some time and energy. Jānis produces lots of useful tips, and I encourage you to take a look.
- In a similar vein, you might also be interested in [6 RStudio Keyboard Shortcuts](https://www.youtube.com/watch?v=U373PGg8Y_0) on YouTube, or if you prefer, just [read the article](https://www.r-bloggers.com/2021/01/6-life-altering-rstudio-keyboard-shortcuts/).
- Perhaps my favorite RStudio tip is to hit F7 for spell-check. Another thing I use a lot is [this PDF of Colors in R](http://www.stat.columbia.edu/~tzheng/files/Rcolor.pdf).
- When working with tidyverse and similar packages, I'm forever opening the [RStudio Cheat Sheets](https://rstudio.com/resources/cheatsheets/), as well.
