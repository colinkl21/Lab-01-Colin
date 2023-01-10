Lab 01 - Hello R
================
Colin
1-10-2023

## Load packages and data

``` r
library(tidyverse) 
library(datasauRus)
```

## Exercises

### Exercise 1

1846 rows and 3 variables/columns variables are dataset, x, and y

datasaurus_dozen %\>% count(dataset) %\>% print(13) \#12 datasets

### Exercise 2

``` r
dino_data <- datasaurus_dozen %>%
  filter(dataset == "dino")

ggplot(data = dino_data, mapping = aes(x = x, y = y)) +
  geom_point()
```

![](lab-01-hello-r_files/figure-gfm/plot-dino-1.png)<!-- -->

``` r
dino_data %>%
  summarize(r = cor(x, y))
```

    ## # A tibble: 1 × 1
    ##         r
    ##     <dbl>
    ## 1 -0.0645

### Exercise 3

``` r
star_data <- datasaurus_dozen %>%
  filter(dataset == "star")

ggplot(data = star_data, mapping = aes(x = x, y = y)) +
  geom_point()
```

![](lab-01-hello-r_files/figure-gfm/plot-star-1.png)<!-- -->

``` r
star_data %>%
  summarize(r = cor(x, y))
```

    ## # A tibble: 1 × 1
    ##         r
    ##     <dbl>
    ## 1 -0.0630

Answer: star correlation (-.0630) and dino correlation (-.0645) are
almost the same

### Exercise 4

Add code and narrative as needed. Note that two R chunks are given but
they are not labeled. Use the convention from above to name them
appropriately.

### Exercise 5

Add code and narrative as needed.

To add R chunks either type out the backticks, curly braces, and the
letter `r` or use the Insert chunk button above, green C+.

## Bonus Tips by Yoo Ri

Here are some helpful tips :)

- filter() is for extracting rows

- group_by() is for grouping datasets by assigned column

- ungroup() cancels the grouping

- summarize() is often used with group_by(). This function can print the
  output according to the group_by().

- facet_grid(y\~x,…) creates a grid with variable y as a row, variable x
  as a column  

- facet_wrap(x,… ) is useful when there is only one variable
