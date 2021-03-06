SDS 192 PS07
================

## INTRODUCTION

Hi! I’m Sophie (she/hers), an undergraduate student in Smith College,
MA. I’m double majoring in Statistical & Data Sciences (SDS) and
Computer Science (CS), so the computer languages I use include R,
Python, Java, Javascript, etc. I’m in my way of self-learning SQL, HTML
& CSS. There are a lot more to learn!

## SDS 192 Classworks

These are interesting projects and class works of SDS 192 - Introduction
to Data Science.

-   Data Wrangling & Plotting Practices
-   More will be added!

### Data Wrangling & Plotting Practices

``` r
gapminder_2007 <- gapminder %>% 
  filter(year == 2007)
```

![](README_files/figure-gfm/unnamed-chunk-3-1.png)<!-- -->

``` r
weekly_campaign_stops <- pres_2016_trail %>% 
  mutate(week = floor_date(date, unit = "week")) %>% 
  group_by(candidate, week) %>% 
  summarize(number_of_stops = n())
```

``` r
ggplot(data = weekly_campaign_stops, aes(x = candidate, y = number_of_stops, color = candidate)) +
  geom_point() +
  ggtitle("2016 Campaign Stops by Candidates") +
  labs(y= "Number of Stops", x = "Candidates") #simple dot plot
```

![](README_files/figure-gfm/unnamed-chunk-5-1.png)<!-- -->

``` r
ggplot(data = weekly_campaign_stops, mapping = aes(x = candidate, y = number_of_stops, fill = candidate)) +
  geom_boxplot()  +
  ggtitle("2016 Campaign Stops by Candidatees") +
  labs(y= "Number of Stops", x = "Candidates") #boxplot
```

![](README_files/figure-gfm/unnamed-chunk-5-2.png)<!-- -->

``` r
ggplot(data = weekly_campaign_stops, mapping = aes(x = candidate, y = number_of_stops, fill = week)) +
  geom_col()  +
  ggtitle("2016 Campaign Stops by Candidates") +
  labs(y= "Number of Stops", x = "Candidates") # bar plot
```

![](README_files/figure-gfm/unnamed-chunk-5-3.png)<!-- -->

``` r
ggplot(data = weekly_campaign_stops, mapping = aes(x = week, y = number_of_stops, fill = candidate)) +
  geom_col(position = position_dodge(preserve = "single"))  +
  ggtitle("2016 Campaign Stops by Candidates") +
  labs(y= "Number of Stops", x = "Weeks", fill = "Candidates") #side-by-side bar plot
```

![](README_files/figure-gfm/unnamed-chunk-5-4.png)<!-- -->

``` r
ggplot(data = evals, mapping = aes(x = score)) +
  geom_histogram(binwidth = 0.25, color = "white")
```

![](README_files/figure-gfm/unnamed-chunk-6-1.png)<!-- -->

``` r
ggplot(data = evals, mapping = aes(x = score)) +
  geom_histogram(binwidth = 0.25, color = "white") +
  facet_wrap(~ ethnicity)
```

![](README_files/figure-gfm/unnamed-chunk-7-1.png)<!-- -->
