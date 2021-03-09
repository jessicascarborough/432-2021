# 432 Class 08: 2021-02-26

[Main Website](https://thomaselove.github.io/432/) | [Calendar](https://thomaselove.github.io/432/calendar.html) | [Syllabus](https://thomaselove.github.io/432-2021-syllabus/) | [Course Notes](https://thomaselove.github.io/432-notes/) | [Canvas](https://canvas.case.edu) | [Data and Code](https://github.com/THOMASELOVE/432-data) | [Sources](https://github.com/THOMASELOVE/432-2021/edit/master/references) | [Contact Us](https://thomaselove.github.io/432/contact.html)
:-----------: | :--------------: | :----------: | :---------: | :-------------: | :-----------: | :------------: | :-------------:
for everything | deadlines | expectations | from Dr. Love | zoom info | downloads | read/watch | need help?

![](https://github.com/THOMASELOVE/432-2021/blob/master/classes/class08/figures/harrell_tw.png)

## Materials for Today's Class

- Today's Slides are [available in PDF](https://github.com/THOMASELOVE/432-2021/blob/master/classes/class08/432_2021_slides08.pdf), as well as in [R Markdown](https://github.com/THOMASELOVE/432-2021/blob/master/classes/class08/432_2021_slides08.Rmd).
    - We will first clean up slides 56-74 from Class 07, before looking at the slides for Class 08. You can get [the PDF for Class 07 here](https://github.com/THOMASELOVE/432-2021/blob/master/classes/class07/432_2021_slides07.pdf).
- All 432 classes are video-recorded, and the recordings will be archived in the Zoom section of [Canvas](https://canvas.case.edu).

## Announcements

1. The [Project 1 Proposal](https://github.com/THOMASELOVE/432-2021/tree/master/project1) is due at 9 PM Monday 2021-03-01.
2. Dr. Love's [Feedback on the Minute Paper after Class 07](https://github.com/THOMASELOVE/432-2021/tree/master/minutepapers) is now available.
3. A reminder that **we will not have class** on Tuesday 2021-03-02. [Class 09](https://github.com/THOMASELOVE/432-2021/tree/master/classes/class09) will be held on Thursday 2021-03-04.
4. Use the "free" time next Tuesday to be sure you're caught up on the reading. You should be finished with the Leek book this weekend, and up to Chapter 6 in *The Signal and the Noise*.
5. [Lab 03](https://github.com/THOMASELOVE/432-2021/tree/master/labs/lab03) is due at 9 PM Monday 2021-03-15.
    - You'll need material I'll discuss in Class 09 to do Question 1, and material from Class 10 to do Question 2. (Question 3 should be something you can do now.)
6. A semi-authoritative source suggests the [correct pronounciation of Gini](https://www.youtube.com/watch?v=Wy7_EwDtrcM) is the same as the word "Genie" (think the Aladdin stories).
7. If you like [skim() and the skimr package](https://cran.r-project.org/web/packages/skimr/vignettes/skimr.html), you might also be interested in [the summarytools package](https://cran.r-project.org/web/packages/summarytools/vignettes/Introduction.html) and the `dfSummary()` function.

## Notes from Dr. Love on Effect Size and Interpreting Effect Sizes

I [built a description of effect sizes and how to discuss them](https://github.com/THOMASELOVE/432-2021/blob/master/classes/class08/class08_effects_note.pdf). 

- I strongly encourage you to read this document. 
- If you want to see the R Markdown file I used to generate this result, [here it is](https://github.com/THOMASELOVE/432-2021/blob/master/classes/class08/class08_effects_note.Rmd).
- For more on these sorts of handouts (popularized by Edward Tufte) see [RStudio's implpementation](https://rstudio.github.io/tufte/)

## Project Data Cleaning Advice (repeated here from note on Piazza)

There is nothing here that is a new requirement, or that should be interpreted as changing the original instructions. Just a few tips.

1. You cannot use the same variable (or any form of the same underlying variable) as both an outcome and a predictor in the same model.
2. Collapse levels sensibly for multi-categorical variables with more than 6 categories, and be sure that all have at least 30 observations in each level, and that they're treated as **factors** in R. 
3. Some binary variables are coded 1 and 2. Fix that by using the real names and treating the variable as a factor, or by converting the 1-2 to a proper 1-0 indicator variable.
   - Use the formula **NEWVAR = 2 - OLDVAR** to turn OLDVAR: 1 = Yes, 2 = No into NEWVAR: 1 = Yes, 0 = No.
   - If you have OLDVAR: 1 = No, 2 = Yes, create a NEWVAR with 1 = Yes, 0 = No using **NEWVAR = OLDVAR - 1**.
4. Things I would treat as missing include Refused, Don't Know, Unknown, No response and missing. Be sure that R recognizes things that are missing as missing and filters them out if you look for complete cases.
5. If you find yourself with `labelled` variables after import with (for example, the `read_xpt()` function), get rid of them with `zap_labels()` from the `haven` package, part of the tidyverse.
6. **Hmisc::describe** (a required part of the proposal) is an incredibly useful step to support range checks across all of your variables as a final check that you've cleaned the data properly. Things to check after cleaning any kind of data:
    - Make sure all of your quantitative variables have a sensible minimum and maximum value.
    - Be sure that all of your categorical variables only include sensible, interpretable categories, contain a reasonable number of subjects, and that don't know/refused/missing are not included as categories. All of your categorical predictors have at least 2 levels and no more than 6 levels after collapsing. 
7. Run a spell-check before knitting the R Markdown into HTML. Just hit F7.
8. Look at the HTML version of your work, not just the R Markdown, to make sure we can read everything.

## Where was Dr. Love this morning (and again through next Tuesday)?

- Meeting as part of the [Agency for Health Care Research and Quality's](https://www.ahrq.gov/) [Health Care Research Training Study Section](https://www.ahrq.gov/funding/process/study-section/hcrtrst.html).
    - This study section reviews applications requesting support for health services research training and career development at the dissertation, junior faculty, and senior faculty level. Research infrastructure applications are also reviewed in this study section and demonstrations and evaluations in topics spanning the entire spectrum of health services research, including but not limited to cost, quality, access, outcomes, quality and effectiveness research, and implementation and innovation research. 
    - The study section will review applications submitted through the auspices of the National Research Service Awards (NRSA) (institutional T32 awards, individual fellowship awards [such as F32 postdoctoral awards and other similar programs]); requesting support for dissertation research (R36), curriculum development, training models, innovations (R25 awards), individual and program career development awards (K series grants), mid-career training enhancement awards, healthcare-related IT training; and training-related conferences and workshops (R13).

## One Last Thing

I'll link to an interesting presentation of some survey results on nearly 4000 science and engineering PhDs reported by Maggie Kuo and Jia You in *Science* for 2017-11-27, entitled [Explore the skills that can open career doors after your doctoral training](https://www.sciencemag.org/careers/2017/11/explore-skills-can-open-career-doors-after-your-doctoral-training). 

- A series of what are called [radar charts](https://en.wikipedia.org/wiki/Radar_chart) (also known as spider charts or web charts) illustrate how well PhD training prepares you for a job.
- Separate charts describe technical skills, then interpersonal skills and then day-to-day skills.
- The three images I've clipped below describe results across all sectors, but in [the actual presentation](https://www.sciencemag.org/careers/2017/11/explore-skills-can-open-career-doors-after-your-doctoral-training), you can look at specific subgroups including several types of research positions, consulting, scientific writing, teaching, and others.

![](https://github.com/THOMASELOVE/432-2021/blob/master/classes/class08/figures/phd_fig1.png)
![](https://github.com/THOMASELOVE/432-2021/blob/master/classes/class08/figures/phd_fig2.png)
![](https://github.com/THOMASELOVE/432-2021/blob/master/classes/class08/figures/phd_fig3.png)

- Interested in drawing charts like these in R? Check out [Beautiful Radar Charts in R using the fmsb and ggradar packages](https://www.datanovia.com/en/blog/beautiful-radar-chart-in-r-using-fmsb-and-ggplot-packages/) at datanovia.com.
