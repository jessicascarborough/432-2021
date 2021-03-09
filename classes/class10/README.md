# 432 Class 10: 2021-03-09

[Main Website](https://thomaselove.github.io/432/) | [Calendar](https://thomaselove.github.io/432/calendar.html) | [Syllabus](https://thomaselove.github.io/432-2021-syllabus/) | [Course Notes](https://thomaselove.github.io/432-notes/) | [Canvas](https://canvas.case.edu) | [Data and Code](https://github.com/THOMASELOVE/432-data) | [Sources](https://github.com/THOMASELOVE/432-2021/edit/master/references) | [Contact Us](https://thomaselove.github.io/432/contact.html)
:-----------: | :--------------: | :----------: | :---------: | :-------------: | :-----------: | :------------: | :-------------:
for everything | deadlines | expectations | from Dr. Love | zoom info | downloads | read/watch | need help?

![](https://github.com/THOMASELOVE/432-2021/blob/master/classes/class10/figures/carr_tw.png)

## Materials for Today's Class

- Today's Slides are [available in PDF](https://github.com/THOMASELOVE/432-2021/blob/master/classes/class10/432_2021_slides10.pdf), as well as in [R Markdown](https://github.com/THOMASELOVE/432-2021/blob/master/classes/class10/432_2021_slides10.Rmd).
- All 432 classes are video-recorded, and the recordings will be archived in the Zoom section of [Canvas](https://canvas.case.edu).

Today we're introducing the `tidymodels` set of packages. **Note** Rather than creating a set of materials (in Chapters 15-17 of the Course Notes) to cover tidymodels topics, I'm going to instead point you to the following excellent external resources for learning more.

1. The [tidymodels website](https://www.tidymodels.org/), in particular the [Get Started](https://www.tidymodels.org/start/) tutorials, and the [Learn section](https://www.tidymodels.org/learn/), which has additional information on performing analyses, tuning models, and developing custom approaches, among other things.
2. Max Kuhn and Julie Silge's book [Tidy Modeling with R](https://www.tmwr.org/) which has been my main way to learn about these approaches.
3. For videos with great `tidymodels` examples, try [Julie Silge's YouTube page](https://www.youtube.com/c/JuliaSilge/videos). I'll highlight...
    - [Model student debt inequality with tidymodels](https://www.youtube.com/watch?v=4ayOjlRv8bA) from 2021-02-12
    - [Get started with tidymodels and classification of penguin data](https://www.youtube.com/watch?v=z57i2GVcdww) from 2020-07-28
    - [Predict astronauts' mission duration with tidymodels and bootstrap aggregation](https://www.youtube.com/watch?v=rzfTA3xi-W0) from 2020-07-15
    - [Data preprocessing and resampling using tidymodels](https://www.youtube.com/watch?v=s3TkvZM60iU) from 2020-03-10
    - [Get started with tidymodels using vaccination rate data](https://www.youtube.com/watch?v=E2Ld3QdXYZo) from 2020-02-25
4. You may be interested in Bruna Wundervald's [An introduction to the tidymodels package](http://brunaw.com/tidymodels-webinar/slides/slides.html#1) slides, too.

## Announcements

1. There is a [Minute Paper after today's class](https://github.com/THOMASELOVE/432-2021/blob/master/minutepapers/README.md) (Class 10) due Wednesday 2021-03-10 at noon.
2. All Project 1 proposals are approved. [Details and project titles are here](https://github.com/THOMASELOVE/432-2021/blob/master/project1/proposal_review.md), and thank you, all.
    -  The [Project 1 Portfolio and Presentation](https://github.com/THOMASELOVE/432-2021/blob/master/project1/02_project1_analyses.md) are due 2021-03-29 at 9 PM.
    -  Be sure to read "[Your proposal is approved. Now what?](https://github.com/THOMASELOVE/432-2021/blob/master/project1/02_project1_analyses.md#your-proposal-is-approved-now-what)" if you are unclear on what to do next.
3. [Lab 3](https://github.com/THOMASELOVE/432-2021/blob/master/labs/lab03/lab03_instructions.md) is due next Monday 2021-03-15 at 9 PM.
    - As mentioned on Piazza, on 2021-03-05, Dr. Love changed [the instructions](https://github.com/THOMASELOVE/432-2021/blob/master/labs/lab03/lab03_instructions.md). Be sure to use [the current version of the instructions](https://github.com/THOMASELOVE/432-2021/blob/master/labs/lab03/lab03_instructions.md).
        1. We adjusted the instructions (slightly) for the fourth part of question 1, and 
        2. added [four hints we hope will be helpful for question 1](https://github.com/THOMASELOVE/432-2021/blob/master/labs/lab03/lab03_instructions.md#four-hints-for-question-1), and
        3. completely changed the presentation of Question 2 so that it walks you through the process we'd like you to follow, step-by-step, which should make creating the R code much less onerous.
    - Today's class will include the things you need to respond to Question 2 on Lab 3.
4. [Quiz A](https://github.com/THOMASELOVE/432-2021/tree/master/quizzes/quizA) will be made available on 2021-03-12, and is due 2021-03-22 at 9 PM. It includes materials from the first 9 classes, from Chapters 1-14 of the course notes, from all of Jeff Leek's *How to be a modern scientist* and from Nate Silver's *The Signal and the Noise* through Chapter 7. It does not include this week's `tidymodels` material.
5. Remember that next Tuesday 2021-03-16 is a University Break day, and so we will not have class.
6. [Language for communicating frequentist results about treatment effects](https://discourse.datamethods.org/t/language-for-communicating-frequentist-results-about-treatment-effects/934) from the discourse page at datamethods.org is, I think, worth some of your time.
7. You may be interested in [A clinician's primer on epidemiology for COVID-19](https://www.cell.com/med/fulltext/S2666-6340(21)00068-4).
    - from the abstract: "Here, we provide a brief primer on key concepts and terms related to COVID-19 epidemiology in the hopes that this information will help provide clinicians with a starting point for evaluating the emerging COVID-19 literature."
8. You might also be interested in a paper [we recently published](https://link.springer.com/article/10.1007/s11606-020-06440-7) on Adoption of Health System Innovations: Evidence of Urban-Rural Disparities from the Ohio Primary Care Marketplace, for the *Journal of General Internal Medicine*. The paper was led by JT Tanenbaum, who completed his MD/PhD at CWRU and is now in his first year of post-graduate work in orthopaedic surgery at Northwestern University.

## One Last Thing

Monday was International Women's Day. 

[Here](https://rss.org.uk/news-publication/news-publications/2021/general-news/watch-our-international-women-s-day-playlist/) is the Royal Statistical Society's [International Women's Day Playlist](https://rss.org.uk/news-publication/news-publications/2021/general-news/watch-our-international-women-s-day-playlist/).

I'll highlight three especially interesting talks:

[Using data to improve health from the time of the Crimea to the time of Covid](https://www.youtube.com/watch?v=OrRoeQaucF0)

- The full title is "Florence Nightingale, pigeonholes and mustard seeds: using data to improve health from the time of the Crimea to the time of Covid, and the talk was given by Deborah Ashby in June 2020, when she was President of the Royal Statistical Society.

[What do we learn about significance tests from the replication crisis?](https://www.youtube.com/watch?v=VRF-UwrepAs)

- Deborah Mayo from the Department of Philosophy, Virginia Tech discussed today’s problems of replication and significance tests. She discusses how we should rethink the controversies of statistical significance in light of high-profile failures of replication. Recoding from 2018-10-23.

[Florence Nightingale and her colleagues: Using statistics to save lives](https://www.youtube.com/watch?v=Y2AzKuywBrE)

- Lynn McDonald explores Nightingale's work in analysing data from the Crimean War, peacetime British Army, nurse deaths in hospitals, maternal deaths post-childbirth, deaths in Indigenous residential schools and stressing the need for good population data on health and housing, on to evidence-based healthcare. Recording from 2020-09-08.

