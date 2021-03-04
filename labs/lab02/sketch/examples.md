# Lab 02 Results for Spring 2021

## Nice Visualizations for Question 1

Partial code for these examples can be found at the bottom of this page.

### Example 1

![](https://github.com/THOMASELOVE/432-2021/blob/master/labs/lab02/sketch/viz/viz1.png)

### Example 2

![](https://github.com/THOMASELOVE/432-2021/blob/master/labs/lab02/sketch/viz/viz2.png)

I don't love the title (everything correlates with everything else, really) but I do like everything else.

### Example 3

![](https://github.com/THOMASELOVE/432-2021/blob/master/labs/lab02/sketch/viz/viz3.png)

### Example 4

![](https://github.com/THOMASELOVE/432-2021/blob/master/labs/lab02/sketch/viz/viz4.PNG)


## Nice Essays for Question 2

Here are four of the many nice essays we enjoyed in response to Question 2, which was...

> Identify an important thing that you learned about prediction from your reading of Nate Silver’s *The Signal and the Noise* either in Chapter 2 (about political predictions) or in chapters 3 (baseball), 4 (weather) or 5 (earthquakes). What does this thing you learned suggest to you about the way you build prediction models, and how can you adopt this new way of thinking to improve the models you’ll generate in this Lab and elsewhere in your scientific life?

### Example 1

The concept of overfitting was the most important problem that I read about. An overfit model means that you are fitting noise in the data instead of evaluating its underlying structure (Silver, 163.). We have an abundance of statistical tests available to us, but if we try to connect all dots through complex functions, we are moving away from the true relationship, and according to Silver, we are no more scientific than a child finding animal patterns in clouds (Silver, 166-167). This concept of thinking helped me improve the model I generated in question 3 and will help me throughout life. My immediate reaction to improve the model from question 3 was to add more predictors and possibly a polynomial in order to improve r-squared. Silver highlights how models deemed “better” by r-squared may be cheating by fitting noise and actually do a worse job in the real world. After learning about this, I will no longer be concerned about making my models look better on paper (eg variability in the data that is accounted for), but rather caring more about the underlying data structure. According to George Box, all models are wrong, but some are useful. I know my models will be wrong, but I would like them to at least be useful. Even if that means having them look even more wrong on paper.

### Example 2

While reading Nate Silver’s “The Signal and the Noise”, I found two important topics about prediction that were both intriguing and useful. Chapter 4 examines how difficult it can be to make accurate predictions and uses weather forecasting examples and analogies to present the concepts of "chaos theory" and "forecast/prediction quality."

Chaos theory deals with systems that are both dynamic and nonlinear. “The most basic tenet of chaos theory is that a small change in initial conditions—a butterfly flapping its wings in Brazil—can produce a large and unexpected divergence in outcomes—a tornado in Texas.” (Silver, Chapter 4) Inaccuracies in data or assumptions can result in significant discrepancies when building mathematical prediction models and must be carefully examined. Consideration of whether to include or exclude particular variables and interaction terms, whether to transform certain variables into factors and the ordering and leveling those factors are also very important decisions to make.

Nate Silver explains the 3 definitions of forecast quality and how important it is to keep them in mind. They include the quality or accuracy of the prediction model, whether consistency or honesty was incorporated into the model effectively, and the economic value of a prediction. Considering these definitions and attempting to produce a model which is accurate and without bias is imperative. Thoughtful consideration of the question: "Is this the best model that I can produce?", coupled with the understanding of chaos theory would greatly benefit my future work in building scientific prediction models.

### Example 3

One piece of advice that Nate Silver gives about making predictions is to think probabilistically (Silver, Chapter 2). Silver suggests that this is a better way to express the uncertainty inherent in real-world situations than a yes-or-no prediction. Thus, categorizing predictions produced by logistic regression based on a set cutoff point may not be an ideal approach to evaluating a model. An alternative might be to separate the predictions into bins (for example, response values of 0-0.1, 0.1-0.2, etc.) and look at the percentage of data points in each bin that had the outcome of interest. An effective model should display evidence of good calibration. Similarly, when interpreting the outputs of logistic regression models, care should be taken to interpret them as probabilities or probabilistic statements rather than simple yes-or-no predictions. As Silver points out, this is not intuitively easy to do, and a better intuition can only be built through experience.

### Example 4

From Nate Silver’s "The Signal and the Noise" I especially appreciate the generalized breakdown of approaches into bullish yet sensational hedgehogs and cautious and more often correct foxes. While I wanted to be a fox I found that I was instead a hedgehog in many more aspects; stalwart instead of adaptable, order-seeking rather than tolerant of complexity (Silver, Chapter 2). I habitually fall into the hedgehog tendencies, begrudgingly using better practices when reminded. I enjoy applying overarching theories. I was under the assumption (even with evidence to the contrary) that increasing information must make models which better fit the data. These habits allow me to craft interesting narratives yet I noticed the tell-tale traps Silver describes; instead of using evidence to steer my prediction it is instead my values at the helm, grasping information to prop up my position rather than building a strong foundation that requires no aid. And although I am open to changes and modifications I tend to leap toward sensational conclusions. An optimistic take away from this chapter is the ability to change and develop foxlike tendencies. Again, and as Silver states in the second chapter "[i]t isn’t easy to be objective," but knowing that I may one day get closer to desirable, fox characteristics while utilizing the useful hedgehog traits is yet another reason to expand my exposure to material and take my time digesting this new information (Silver, Chapter 2).

## Partial Code for Visualizations

#### Example 1

```
ggplot(data=oh20_lab02, mapping = aes(x = hsgrads, y = sti_rate))+
  geom_point(na.rm=TRUE, color="mediumpurple4", size=2, alpha=0.6)+
  geom_point(data = oh20_lab02 %>%
               slice_max(sti_rate, n=5),
             col = "goldenrod1", size = 3) +
  geom_point(data = oh20_lab02 %>%
               slice_min(sti_rate, n=5),
             col = "goldenrod1", size = 3) +
  geom_text_repel(data = oh20_lab02 %>%
                    slice_max(sti_rate, n = 5), 
                  aes(label = county), min.segment.length = unit(0, 'lines'), nudge_x = 5, col = "black") +
  geom_text_repel(data = oh20_lab02 %>%
                    slice_min(sti_rate, n = 5), 
                  aes(label = county), min.segment.length = unit(0, 'lines'), nudge_x = -5, col = "black") +
  facet_grid(~median_cat, labeller = label_both) +
  geom_smooth(method="lm", se=FALSE, na.rm=TRUE, col="goldenrod2") +
  labs(title="Effect of High School Graduation on STI Rate by Median Income Category", 
       x="High School Graduation Rate (%)", y="Chlamydia Cases per Population x 100,000") +
  theme_bw()
```

#### Example 2

```
caption_wrap <- str_wrap("Using the 2020 County Health Rankings data for Ohio, we plot a point for each county, indicating the population percentage (16+) who is unemployed and looking for work and a metric denoting access to healthy foods, with counties separated by younger and older populations. Counties with increased unemployment tend to have decreased access to healthy foods. This trend is true in both younger and older communities.")

ggplot(q01, aes(x = unemployed, y = food_env, color = age65plus_fct)) + 
  geom_point(aes(size = 4, alpha = 0.5), show.legend = FALSE) + 
  facet_wrap(~age65plus_fct) + 
  labs(x = "Unemployment Rate",
       y = "Access to Healthy Foods\n(0-10 from worst to best)", 
       title = "Increased unemployment correlates to decreased access to healthy foods", 
       subtitle = "As seen in both younger and older Ohio counties", 
       caption = caption_wrap) +
  scale_x_continuous(labels = percent_format(scale = 1)) + 
  scale_color_manual(values = c("lightsteelblue3", "lightsteelblue4")) +
  theme_bw() +
  theme(plot.title = element_text(hjust = 0.5),
        plot.subtitle = element_text(hjust = 0.5),
        plot.caption = element_text(hjust = 0.5))
```

### Example 3

```
question1_df <- oh_2020 %>%
  select(fips, county, obese_pct, food_insecure, dm_prev, food_env) %>%
  mutate(county = tolower(county))

ohio_data <- map_data("county", region = "Ohio") %>% 
  rename(county = subregion)

ohio_map <- left_join(ohio_data, question1_df, by = "county")

p1 <- ggplot(ohio_map, aes(long, lat, group = group)) + 
  theme_classic() + 
  geom_polygon(color = "black") +
  geom_polygon(aes(fill = food_env), color = "black") + 
  scale_fill_viridis_c(option = "C") + 
  theme(panel.grid = element_blank(),
        axis.text = element_blank(),
        axis.ticks = element_blank(),
        axis.line = element_blank(), 
        panel.background = element_blank()) + 
  labs(title = "", 
       x = "A", 
       y = "", 
       fill="Food Environment")

p2 <- ggplot(ohio_map, aes(long, lat, group = group)) + 
  theme_classic() + 
  geom_polygon(color = "black") +
  geom_polygon(aes(fill = obese_pct), color = "black") + 
  scale_fill_viridis_c(option = "C") + 
  theme(panel.grid = element_blank(),
        axis.text = element_blank(),
        axis.ticks = element_blank(),
        axis.line = element_blank(), 
        panel.background = element_blank()) + 
  labs(title = "", 
       x = "B", 
       y = "", 
       fill="% Obese")

p3 <- ggplot(ohio_map, aes(long, lat, group = group)) + 
  theme_classic() + 
  geom_polygon(color = "black") + 
  geom_polygon(aes(fill = food_insecure), color = "black") + 
  scale_fill_viridis_c(option = "C") + 
  theme(panel.grid = element_blank(),
        axis.text = element_blank(),
        axis.ticks = element_blank(),
        axis.line = element_blank(), 
        panel.background = element_blank()) + 
  labs(title = "", 
       x = "C", 
       y = "", 
       fill="% Food Insecure")

p4 <- ggplot(ohio_map, aes(long, lat, group = group)) + 
  theme_classic() + 
  geom_polygon(color = "black") + 
  geom_polygon(aes(fill = dm_prev), color = "black") + 
  scale_fill_viridis_c(option = "C") + 
  theme(panel.grid = element_blank(),
        axis.text = element_blank(),
        axis.ticks = element_blank(),
        axis.line = element_blank(), 
        panel.background = element_blank()) + 
  labs(title = "", 
       x = "D", 
       y = "", 
       fill="Diabetes Prevelance")

(p1 + p2) / (p3 + p4) + plot_layout() + 
  plot_annotation(title = "Contribution of Food Availability to Common Metabolic Conditions")
```

### Example 4

```
lab2<-lab2 %>%
  mutate(rural2 = case_when(rural>.75 ~ "Greater than 75% Rural Population",
                            .50<rural&rural<.75 ~ "50 - 75% Rural Population",
                            .25<rural&rural<.50 ~ "25 - 50%  Rural Population",
                            rural<.25 ~ "Less than 25% Rural Population"))%>%
         mutate(rural2=fct_relevel(rural2, c("Less than 25% Rural Population", 
                                             "25 - 50%  Rural Population", 
                                              "50 - 75% Rural Population", 
                                              "Greater than 75% Rural Population")))

ggplot(lab2, aes(x=teen_births, y=hsgrads, color=rural2, fill=rural2) +
   geom_point() +
   geom_smooth(method = "lm", formula = "y ~ x", alpha = 0.3, show.legend = FALSE, color="black") +
  scale_color_brewer(palette = "Spectral") +
  scale_fill_brewer(palette = "Spectral") +
  facet_wrap(~rural2) +
  labs(title= "Scatterplot of Counties' Teen Birth Rates versus High School Graduation Rates",
       subtitle = "     by Percent of Population Living in Rural Areas", 
       x = "Teen Births per Females Aged 15-19 Years (x 1,000)", 
       y = "High School Graduation Rate (%)",
       fill = "Percent Rural", color = "Percent Rural")+
  stat_cor(label.y = 84.8, color="black")+
  stat_regline_equation(label.y = 83.5, color="black")+
  theme_new() +
  theme(legend.position = "none")
```
