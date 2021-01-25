432 Homework 1
================

# General Instructions

Submit your work via [Canvas](https://canvas.case.edu/). The deadline is
specified on [the Course
Calendar](https://github.com/THOMASELOVE/432/calendar.html).

Your response should include an R Markdown file and an HTML document
that is the result of applying your R Markdown file to the `hbp3456.csv`
data, available in the data subfolder for this homework, as well as on
our Data and Code page. Start a separate R Project for Homework 1, as
your first step, and place the data in that project’s directory or (if
you want to match what I did) in a data sub-directory.

## The `hbp3456` data

The (simulated) data describe a total of 3456 individuals living with
hypertension (high blood pressure) diagnoses who receive primary care in
one of eight practices. 432 (different) individuals were sampled from
each practice. The data are based on real electronic health records, but
with some noise added. The practices are named after streets that appear
in *The Simpsons* and the identification of providers are fictional.

|    Variable | Description                                                                                                                                                                     |
|------------:|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    `record` | unique code for each subject (six digits, first digit is 9, last indicates practice)                                                                                            |
|  `practice` | primary care practice, of which there are eight in the data                                                                                                                     |
|  `provider` | primary care provider (each practice has multiple providers)                                                                                                                    |
|       `age` | subject’s age as of the start of the reporting period                                                                                                                           |
|      `race` | subject’s race (4 levels: Asian, AA\_Black, White, Other)                                                                                                                       |
|  `eth_hisp` | is subject of Hispanic/Latino ethnicity? Yes or No                                                                                                                              |
|       `sex` | subject’s sex (F or M)                                                                                                                                                          |
| `insurance` | subject’s primary insurance (Medicare, Commercial, Medicaid, Uninsured)                                                                                                         |
|    `income` | estimated median income of subject’s home neighborhood (via American Community Survey, to nearest $100)                                                                         |
|    `hsgrad` | estimated percentage of adults living in the subject’s home neighborhood who have graduated from high school (via American Community Survey, to the nearest tenth of a percent) |
|   `tobacco` | tobacco use status (Current, Former, or Never)                                                                                                                                  |
|   `depdiag` | does subject have depression diagnosis? Yes or No                                                                                                                               |
|    `height` | subject’s height in meters, rounded to two decimal places                                                                                                                       |
|    `weight` | subject’s weight in kilograms, rounded to one decimal place                                                                                                                     |
|       `ldl` | subject’s LDL cholesterol level, in mg/dl                                                                                                                                       |
|    `statin` | does subject have a current prescription for a statin medication? Yes or No                                                                                                     |
|     `bpmed` | does subject have a current prescription for a blood pressure control medication? Yes or No                                                                                     |
|       `sbp` | subject’s most recently obtained systolic blood pressure, in mm Hg                                                                                                              |
|       `dbp` | subject’s most recently obtained diastolic blood pressure, in mm Hg                                                                                                             |
|  `visits_1` | subject’s number of visits for primary care in reporting period (one year)                                                                                                      |
|  `visits_2` | subject’s visits for primary care in the past two years                                                                                                                         |
|    `acearb` | does subject have a current prescription for an ACE-inhibitor or ARB? Yes or No                                                                                                 |
|     `betab` | does subject have a current prescription for a beta-blocker? Yes or No                                                                                                          |

The list of medications included in `bpmed` is: ACE-inhibitor, ARB,
Diuretic, Calcium-Channel Blocker, Beta-Blocker, Alpha-1 Blocker,
Centrally acting Alpha-2 Agonist, Vasodilator or other antihypertensive
agents. A subject with a current prescription for any of these will have
a Yes in `bpmed`.

Here’s a quick glimpse of the data.

``` r
hw1 <- read_csv(here("data", "hbp3456.csv"))
hw1 <- hw1 %>%
    mutate(record = as.character(record))

mosaic::inspect(hw1)
```


    categorical variables:  
            name     class levels    n missing
    1     record character   3456 3456       0
    2   practice character      8 3456       0
    3   provider character     62 3456       0
    4       race character      4 3364      92
    5   eth_hisp character      2 3345     111
    6        sex character      2 3456       0
    7  insurance character      4 3456       0
    8    tobacco character      3 3451       5
    9  depr_diag character      2 3456       0
    10    statin character      2 3456       0
    11    bp_med character      2 3456       0
    12    acearb character      2 3456       0
    13     betab character      2 3456       0
                                        distribution
    1  900018 (0%), 900024 (0%) ...                 
    2  Center (12.5%), Elm (12.5%) ...              
    3  P_04 (4.8%), P_03 (4.2%) ...                 
    4  White (51.8%), AA_Black (43.4%) ...          
    5  No (93.6%), Yes (6.4%)                       
    6  F (59.7%), M (40.3%)                         
    7  Medicare (40%), Commercial (29.9%) ...       
    8  Never (46.9%), Former (30.3%) ...            
    9  No (72.9%), Yes (27.1%)                      
    10 Yes (51.1%), No (48.9%)                      
    11 Yes (94.3%), No (5.7%)                       
    12 Yes (60.8%), No (39.2%)                      
    13 No (64.8%), Yes (35.2%)                      

    quantitative variables:  
              name   class     min       Q1   median       Q3       max
    ...1       age numeric   25.00    51.00    59.00    68.00     80.00
    ...2    income numeric 6500.00 23900.00 35800.00 52100.00 130000.00
    ...3    hsgrad numeric   40.00    75.35    84.30    90.05     99.90
    ...4    height numeric    1.35     1.60     1.68     1.75      2.03
    ...5    weight numeric   40.90    74.80    88.90   105.70    231.30
    ...6       ldl numeric   30.00    82.00   106.00   135.00    246.00
    ...7       sbp numeric   84.00   122.00   132.00   142.00    214.00
    ...8       dbp numeric   42.00    70.00    78.00    84.00    136.00
    ...9  visits_1 numeric    1.00     2.00     3.00     4.00     12.00
    ...10 visits_2 numeric    2.00     3.00     5.00     7.00     24.00
                  mean           sd    n missing
    ...1     59.188657 1.251674e+01 3456       0
    ...2  38626.930924 1.843596e+04 3431      25
    ...3     82.148237 1.078447e+01 3431      25
    ...4      1.674610 1.029425e-01 3438      18
    ...5     92.287111 2.522100e+01 3437      19
    ...6    111.191736 3.963922e+01 3025     431
    ...7    132.541377 1.650277e+01 3456       0
    ...8     76.871238 1.114215e+01 3456       0
    ...9      3.055845 1.863366e+00 3456       0
    ...10     5.346065 3.089411e+00 3456       0

## Question 1. (40 points)

Build a Table 1 to compare the subjects in the Highland practice to the
subjects in the Sycamore practice on the following nine variables: age,
race, Hispanic ethnicity, sex, primary insurance, body mass index, BMI
category, and systolic and diastolic blood pressure. Make the Table as
well as you can within R Markdown, and display the result as part of
your HTML file. **Include a description of the important results from
your Table 1 that does not exceed 100 words, using complete English
sentences**.

1.  Be sure that your table specifies the number of subjects in each
    practice. **Note that you’ll have to do something so that your work
    focuses on the comparison of Highland to Sycamore, leaving out (for
    this question only) the other practices.**
2.  You’ll have to deal with some missingness in the data, in an
    appropriate way. Be sure to specify what you did with the missing
    data (and how much you had to deal with) in a footnote to the table.
    Specifically, list the notes as a bulleted list in the Markdown
    file, and never leave Markdown during the entire enterprise. It’s
    not usually appropriate to report results that include imputation in
    a Table 1, so I expect the best choice is to build a note specifying
    the amount of missing data.
3.  Some variables will present as characters in the data if you import
    it as I did above, but you’d instead prefer them to appear as
    **factors**. Be sure to include code in your response to make these
    changes (the `forcats` package is your friend here) and then
    (perhaps using the `fct_relevel` function in the `forcats` package)
    be sure to move the levels of those factors into an order that
    facilitates interpretation.
4.  Be sure, too, to make reasoned choices about whether means and
    standard deviations or instead medians and quartiles are more
    appropriate displays for the quantitative variables. Include your
    reasons in your bulleted list of footnotes at the end of your table.
5.  Note that body mass index (BMI) and BMI category are not supplied in
    the data, although you do have height and weight. **So, you’ll have
    to calculate the BMI and add it to the data set.** If you don’t know
    the formula for BMI, you have Google to help you figure it out.
6.  For BMI categories, use the four groups specified in the [How is BMI
    interpreted for Adults section of this
    description](https://www.cdc.gov/healthyweight/assessing/bmi/adult_bmi/index.html)
    of Adult BMI by the Centers for Disease Control. **Again, you’ll
    need to use your calculated BMI values and then create the
    categories in your data set, and you’ll need to figure out a way to
    accurately get each subject into the correct category.**
7.  Do not include R output without complete sentences describing what
    you are doing in each step, and what you conclude from that work.

## Question 2. (20 points)

Now, look at the complete data, describing all eight practices (the
names are Center, Elm, Highland, King, North, Plympton, Sycamore and
Walnut.)

Does which **insurance** status a person has seem to have a meaningful
impact on their **systolic blood pressure**, adjusting for whether or
not they have a prescription for a **beta-blocker**? Decide whether your
model should include an interaction term in a sensible way (providing a
graph to help us understand your reasoning), and then fit your choice of
model using a linear model. Be sure to provide a written explanation of
your findings, in complete sentences. In that explanation, you should
address both the overall quality of fit and the interpretation of the
coefficients of your chosen model.

1.  As a hint, one graph you might use would be one to assess the need
    for an interaction term. Another graph (or perhaps table) to
    consider for insight would look at the relationship between
    **insurance** and **beta-blocker** status in these subjects.
2.  Do not include R output without complete sentences describing what
    you are doing in each step, and what you conclude from that work.

## Question 3. (20 points)

Question from Silver.

Write an essay of 150-250 words (using complete sentences, and examples
derived from your modeling) that explains how this advice is connected
to your thinking about presenting your results.

## Question 4. (10 points)

Please verify your presence on Piazza by placing a non-anonymous post in
the **lab01\_music** folder [on
Piazza](https://piazza.com/case/spring2021/pqhs432) describing your
favorite kind of music. You can specify a kind of music, a favorite
song, or recording artist. A single sentence is sufficient for this
task. We simply want to verify that you can post on Piazza, and gather a
little more information about what people taking this class like to
listen to. Dr. Love has provided his own post on this issue in the
**lab01\_music** folder on Piazza.

## Question 5. (10 points)

Please tell us your Github user name. To learn more about Git and
Github, we recommend <https://happygitwithr.com/>.

## Please add the session information.

Finally, at the end of this homework and all subsequent assignments
(including the projects), please add the session information. My
preferred way for you to do this is…

``` r
xfun::session_info()
```

the results of which are shown at the bottom of this page.

### End of Homework 1

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
      askpass_1.1             assertthat_0.2.1        backports_1.2.1        
      base64enc_0.1.3         BH_1.75.0.0             blob_1.2.1             
      brio_1.1.1              broom_0.7.3             callr_3.5.1            
      cellranger_1.1.0        cli_2.2.0               clipr_0.7.1            
      colorspace_2.0-0        compiler_4.0.3          cpp11_0.2.5            
      crayon_1.3.4            crosstalk_1.1.1         curl_4.3               
      DBI_1.1.1               dbplyr_2.0.0            desc_1.2.0             
      diffobj_0.3.3           digest_0.6.27           dplyr_1.0.3            
      ellipsis_0.3.1          evaluate_0.14           fansi_0.4.2            
      farver_2.0.3            forcats_0.5.0           fs_1.5.0               
      generics_0.1.0          ggdendro_0.1.22         ggforce_0.3.2          
      ggformula_0.10.1        ggplot2_3.3.3           ggrepel_0.9.1          
      ggridges_0.5.3          ggstance_0.3.5          glue_1.4.2             
      graphics_4.0.3          grDevices_4.0.3         grid_4.0.3             
      gridExtra_2.3           gtable_0.3.0            haven_2.3.1            
      here_1.0.1              highr_0.8               hms_1.0.0              
      htmltools_0.5.0         htmlwidgets_1.5.3       httr_1.4.2             
      isoband_0.2.3           janitor_2.1.0           jpeg_0.1.8.1           
      jsonlite_1.7.2          knitr_1.30              labeling_0.4.2         
      labelled_2.7.0          lattice_0.20-41         latticeExtra_0.6.29    
      lazyeval_0.2.2          leaflet_2.0.4.1         leaflet.providers_1.9.0
      lifecycle_0.2.0         lubridate_1.7.9.2       magrittr_2.0.1         
      markdown_1.1            MASS_7.3-53             Matrix_1.2-18          
      methods_4.0.3           mgcv_1.8.33             mime_0.9               
      modelr_0.1.8            mosaic_1.8.3            mosaicCore_0.9.0       
      mosaicData_0.20.2       munsell_0.5.0           nlme_3.1.149           
      openssl_1.4.3           pillar_1.4.7            pkgbuild_1.2.0         
      pkgconfig_2.0.3         pkgload_1.1.0           plyr_1.8.6             
      png_0.1.7               polyclip_1.10-0         praise_1.0.0           
      prettyunits_1.1.1       processx_3.4.5          progress_1.2.2         
      ps_1.5.0                purrr_0.3.4             R6_2.5.0               
      raster_3.4.5            RColorBrewer_1.1.2      Rcpp_1.0.6             
      RcppEigen_0.3.3.9.1     readr_1.4.0             readxl_1.3.1           
      rematch_1.0.1           rematch2_2.1.2          reprex_0.3.0           
      rlang_0.4.9             rmarkdown_2.6           rprojroot_2.0.2        
      rstudioapi_0.13         rvest_0.3.6             scales_1.1.1           
      selectr_0.4.2           snakecase_0.11.0        sp_1.4.5               
      splines_4.0.3           stats_4.0.3             stringi_1.5.3          
      stringr_1.4.0           sys_3.4                 testthat_3.0.1         
      tibble_3.0.5            tidyr_1.1.2             tidyselect_1.1.0       
      tidyverse_1.3.0         tinytex_0.29            tools_4.0.3            
      tweenr_1.0.1            utf8_1.1.4              utils_4.0.3            
      vctrs_0.3.6             viridis_0.5.1           viridisLite_0.3.0      
      waldo_0.2.3             whisker_0.4             withr_2.4.0            
      xfun_0.19               xml2_1.3.2              yaml_2.2.1             
