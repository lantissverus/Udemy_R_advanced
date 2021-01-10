R\_advanced\_P5\_Apply
================

## Import Data

``` r
Chicago_F = read.csv("./data/Weather Data/Chicago-F.csv", row.names = 1)
NewYork_F = read.csv("./data/Weather Data/NewYork-F.csv", row.names = 1)
Houston_F = read.csv("./data/Weather Data/Houston-F.csv", row.names = 1)
SanFrancisco_F = read.csv("./data/Weather Data/SanFrancisco-F.csv", row.names = 1)
```

``` r
is.data.frame(Chicago_F)
```

    ## [1] TRUE

### Let’s convert to matrices:

``` r
Chicago_F = as.matrix(Chicago_F)
NewYork_F = as.matrix(NewYork_F)
Houston_F = as.matrix(Houston_F)
SanFrancisco_F = as.matrix(SanFrancisco_F)
```

check:

``` r
is.matrix(Chicago_F)
```

    ## [1] TRUE

## Put all of these data into a list:

``` r
weather_F = list(Chicago = Chicago_F, Houston = Houston_F, NewYork = NewYork_F, SanFrancisco = SanFrancisco_F) 
```

Try

``` r
weather_F[[3]] %>% knitr::kable()
```

|                 |   Jan |    Feb |    Mar |    Apr |    May |   Jun |    Jul |    Aug |    Sep |    Oct |    Nov |    Dec |
| :-------------- | ----: | -----: | -----: | -----: | -----: | ----: | -----: | -----: | -----: | -----: | -----: | -----: |
| AvgHigh\_F      |  39.0 |  42.00 |  50.00 |  60.00 |  71.00 |  79.0 |  85.00 |  83.00 |  76.00 |  65.00 |  54.00 |  44.00 |
| AvgLow\_F       |  26.0 |  29.00 |  35.00 |  44.00 |  55.00 |  64.0 |  70.00 |  69.00 |  61.00 |  50.00 |  41.00 |  32.00 |
| AvgPrecip\_inch |   3.9 |   2.95 |   4.06 |   3.94 |   4.45 |   3.5 |   4.53 |   4.13 |   3.98 |   3.39 |   3.82 |   3.58 |
| DaysWithPrecip  |  11.0 |  10.00 |  12.00 |  11.00 |  11.00 |  10.0 |  11.00 |  10.00 |   8.00 |   8.00 |   9.00 |  10.00 |
| HoursOfSunshine | 154.0 | 171.00 | 213.00 | 237.00 | 268.00 | 289.0 | 302.00 | 271.00 | 235.00 | 213.00 | 169.00 | 155.00 |

``` r
weather_F$NewYork %>% knitr::kable()
```

|                 |   Jan |    Feb |    Mar |    Apr |    May |   Jun |    Jul |    Aug |    Sep |    Oct |    Nov |    Dec |
| :-------------- | ----: | -----: | -----: | -----: | -----: | ----: | -----: | -----: | -----: | -----: | -----: | -----: |
| AvgHigh\_F      |  39.0 |  42.00 |  50.00 |  60.00 |  71.00 |  79.0 |  85.00 |  83.00 |  76.00 |  65.00 |  54.00 |  44.00 |
| AvgLow\_F       |  26.0 |  29.00 |  35.00 |  44.00 |  55.00 |  64.0 |  70.00 |  69.00 |  61.00 |  50.00 |  41.00 |  32.00 |
| AvgPrecip\_inch |   3.9 |   2.95 |   4.06 |   3.94 |   4.45 |   3.5 |   4.53 |   4.13 |   3.98 |   3.39 |   3.82 |   3.58 |
| DaysWithPrecip  |  11.0 |  10.00 |  12.00 |  11.00 |  11.00 |  10.0 |  11.00 |  10.00 |   8.00 |   8.00 |   9.00 |  10.00 |
| HoursOfSunshine | 154.0 | 171.00 | 213.00 | 237.00 | 268.00 | 289.0 | 302.00 | 271.00 | 235.00 | 213.00 | 169.00 | 155.00 |

## Apply Family

  - *apply* : use on a matrix, either the rows or columns.
  - *tapply* : use on a vector to extract subgroups and apply a function
    to them by - use on data frams. Same concept as in group by in SQL.
  - *eapply* : use on an environment.
  - *lapply* : apply a function to elements of a list.
  - *sapply* : a version of lapply. Can simplify S the result so it’s
    not presented as a list.
  - *vapply* : has a pre-specified type of return value(V).
  - *replicate* : run a function several times. Usually used with
    generation of random variables.
  - *mapply*: multivariate version of sapply. Arguments can be recycled.
  - *rapply* : recursive version of lapply.