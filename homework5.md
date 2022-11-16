homework5
================
wz2631
2022-11-16

## Problem 1

The code chunk below imports the data in individual spreadsheets
contained in `./data/zip_data/`. To do this, the dataframe that includes
the list of all files in that directory and the complete path to each
file was created. Next, I `map` over paths and import data using the
`read_csv` function. Finally, I `unnest` the result of `map`.

``` r
full_df = 
  tibble(
    files = list.files("data/zip_data/"),
    path = str_c("data/zip_data/", files)
  ) %>% 
  mutate(data = map(path, read_csv)) %>% 
  unnest()
```

    ## Rows: 1 Columns: 8
    ## ── Column specification ────────────────────────────────────────────────────────
    ## Delimiter: ","
    ## dbl (8): week_1, week_2, week_3, week_4, week_5, week_6, week_7, week_8
    ## 
    ## ℹ Use `spec()` to retrieve the full column specification for this data.
    ## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.
    ## Rows: 1 Columns: 8
    ## ── Column specification ────────────────────────────────────────────────────────
    ## Delimiter: ","
    ## dbl (8): week_1, week_2, week_3, week_4, week_5, week_6, week_7, week_8
    ## 
    ## ℹ Use `spec()` to retrieve the full column specification for this data.
    ## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.
    ## Rows: 1 Columns: 8
    ## ── Column specification ────────────────────────────────────────────────────────
    ## Delimiter: ","
    ## dbl (8): week_1, week_2, week_3, week_4, week_5, week_6, week_7, week_8
    ## 
    ## ℹ Use `spec()` to retrieve the full column specification for this data.
    ## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.
    ## Rows: 1 Columns: 8
    ## ── Column specification ────────────────────────────────────────────────────────
    ## Delimiter: ","
    ## dbl (8): week_1, week_2, week_3, week_4, week_5, week_6, week_7, week_8
    ## 
    ## ℹ Use `spec()` to retrieve the full column specification for this data.
    ## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.
    ## Rows: 1 Columns: 8
    ## ── Column specification ────────────────────────────────────────────────────────
    ## Delimiter: ","
    ## dbl (8): week_1, week_2, week_3, week_4, week_5, week_6, week_7, week_8
    ## 
    ## ℹ Use `spec()` to retrieve the full column specification for this data.
    ## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.
    ## Rows: 1 Columns: 8
    ## ── Column specification ────────────────────────────────────────────────────────
    ## Delimiter: ","
    ## dbl (8): week_1, week_2, week_3, week_4, week_5, week_6, week_7, week_8
    ## 
    ## ℹ Use `spec()` to retrieve the full column specification for this data.
    ## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.
    ## Rows: 1 Columns: 8
    ## ── Column specification ────────────────────────────────────────────────────────
    ## Delimiter: ","
    ## dbl (8): week_1, week_2, week_3, week_4, week_5, week_6, week_7, week_8
    ## 
    ## ℹ Use `spec()` to retrieve the full column specification for this data.
    ## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.
    ## Rows: 1 Columns: 8
    ## ── Column specification ────────────────────────────────────────────────────────
    ## Delimiter: ","
    ## dbl (8): week_1, week_2, week_3, week_4, week_5, week_6, week_7, week_8
    ## 
    ## ℹ Use `spec()` to retrieve the full column specification for this data.
    ## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.
    ## Rows: 1 Columns: 8
    ## ── Column specification ────────────────────────────────────────────────────────
    ## Delimiter: ","
    ## dbl (8): week_1, week_2, week_3, week_4, week_5, week_6, week_7, week_8
    ## 
    ## ℹ Use `spec()` to retrieve the full column specification for this data.
    ## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.
    ## Rows: 1 Columns: 8
    ## ── Column specification ────────────────────────────────────────────────────────
    ## Delimiter: ","
    ## dbl (8): week_1, week_2, week_3, week_4, week_5, week_6, week_7, week_8
    ## 
    ## ℹ Use `spec()` to retrieve the full column specification for this data.
    ## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.
    ## Rows: 1 Columns: 8
    ## ── Column specification ────────────────────────────────────────────────────────
    ## Delimiter: ","
    ## dbl (8): week_1, week_2, week_3, week_4, week_5, week_6, week_7, week_8
    ## 
    ## ℹ Use `spec()` to retrieve the full column specification for this data.
    ## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.
    ## Rows: 1 Columns: 8
    ## ── Column specification ────────────────────────────────────────────────────────
    ## Delimiter: ","
    ## dbl (8): week_1, week_2, week_3, week_4, week_5, week_6, week_7, week_8
    ## 
    ## ℹ Use `spec()` to retrieve the full column specification for this data.
    ## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.
    ## Rows: 1 Columns: 8
    ## ── Column specification ────────────────────────────────────────────────────────
    ## Delimiter: ","
    ## dbl (8): week_1, week_2, week_3, week_4, week_5, week_6, week_7, week_8
    ## 
    ## ℹ Use `spec()` to retrieve the full column specification for this data.
    ## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.
    ## Rows: 1 Columns: 8
    ## ── Column specification ────────────────────────────────────────────────────────
    ## Delimiter: ","
    ## dbl (8): week_1, week_2, week_3, week_4, week_5, week_6, week_7, week_8
    ## 
    ## ℹ Use `spec()` to retrieve the full column specification for this data.
    ## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.
    ## Rows: 1 Columns: 8
    ## ── Column specification ────────────────────────────────────────────────────────
    ## Delimiter: ","
    ## dbl (8): week_1, week_2, week_3, week_4, week_5, week_6, week_7, week_8
    ## 
    ## ℹ Use `spec()` to retrieve the full column specification for this data.
    ## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.
    ## Rows: 1 Columns: 8
    ## ── Column specification ────────────────────────────────────────────────────────
    ## Delimiter: ","
    ## dbl (8): week_1, week_2, week_3, week_4, week_5, week_6, week_7, week_8
    ## 
    ## ℹ Use `spec()` to retrieve the full column specification for this data.
    ## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.
    ## Rows: 1 Columns: 8
    ## ── Column specification ────────────────────────────────────────────────────────
    ## Delimiter: ","
    ## dbl (8): week_1, week_2, week_3, week_4, week_5, week_6, week_7, week_8
    ## 
    ## ℹ Use `spec()` to retrieve the full column specification for this data.
    ## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.
    ## Rows: 1 Columns: 8
    ## ── Column specification ────────────────────────────────────────────────────────
    ## Delimiter: ","
    ## dbl (8): week_1, week_2, week_3, week_4, week_5, week_6, week_7, week_8
    ## 
    ## ℹ Use `spec()` to retrieve the full column specification for this data.
    ## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.
    ## Rows: 1 Columns: 8
    ## ── Column specification ────────────────────────────────────────────────────────
    ## Delimiter: ","
    ## dbl (8): week_1, week_2, week_3, week_4, week_5, week_6, week_7, week_8
    ## 
    ## ℹ Use `spec()` to retrieve the full column specification for this data.
    ## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.
    ## Rows: 1 Columns: 8
    ## ── Column specification ────────────────────────────────────────────────────────
    ## Delimiter: ","
    ## dbl (8): week_1, week_2, week_3, week_4, week_5, week_6, week_7, week_8
    ## 
    ## ℹ Use `spec()` to retrieve the full column specification for this data.
    ## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.

The result of the previous code chunk isn’t tidy – data are wide rather
than long, and some important variables are included as parts of others.
The code chunk below tides the data using string manipulations on the
file, converting from wide to long, and selecting relevant variables.

``` r
tidy_df = 
  full_df %>% 
  mutate(
    files = str_replace(files, ".csv", ""),
    group = str_sub(files, 1, 3)) %>% 
  pivot_longer(
    week_1:week_8,
    names_to = "week",
    values_to = "outcome",
    names_prefix = "week_") %>% 
  mutate(week = as.numeric(week)) %>% 
  select(group, subj = files, week, outcome)
```

Finally, the code chunk below creates a plot showing individual data,
faceted by group.

``` r
tidy_df %>% 
  ggplot(aes(x = week, y = outcome, group = subj, color = group)) + 
  geom_point() + 
  geom_path() + 
  facet_grid(~group)
```

<img src="homework5_files/figure-gfm/unnamed-chunk-4-1.png" width="90%" />

This plot suggests high within-subject correlation – subjects who start
above average end up above average, and those that start below average
end up below average. Subjects in the control group generally don’t
change over time, but those in the experiment group increase their
outcome in a roughly linear way.

## Problem 2

#### Import and describe the raw data.

The code chunk below imports and cleans the data in `homicide-data.csv`.

``` r
homicide_df = 
  read_csv("./data/homicide-data.csv") %>% 
  janitor::clean_names()
```

    ## Rows: 52179 Columns: 12
    ## ── Column specification ────────────────────────────────────────────────────────
    ## Delimiter: ","
    ## chr (9): uid, victim_last, victim_first, victim_race, victim_age, victim_sex...
    ## dbl (3): reported_date, lat, lon
    ## 
    ## ℹ Use `spec()` to retrieve the full column specification for this data.
    ## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.

There are 12 columns and 52179 rows in this dataframe, and the important
variables included are uid, reported_date, victim_last, victim_first,
victim_race, victim_age, victim_sex, city, state, lat, lon, disposition,
which are used to describe the information of homicides in 50 large U.S.
cities.

#### Create a city_state variable by mutate function.

``` r
homicide_df =
  homicide_df %>% 
  mutate(city_state = str_c(city, ', ',state))
```

#### Summarize within cities to obtain the total number of homicides.

``` r
homicide_total = homicide_df %>% 
  group_by(city_state) %>% 
  count(city_state) %>% 
  summarize(n) 
homicide_total %>% 
  knitr::kable()
```

| city_state         |    n |
|:-------------------|-----:|
| Albuquerque, NM    |  378 |
| Atlanta, GA        |  973 |
| Baltimore, MD      | 2827 |
| Baton Rouge, LA    |  424 |
| Birmingham, AL     |  800 |
| Boston, MA         |  614 |
| Buffalo, NY        |  521 |
| Charlotte, NC      |  687 |
| Chicago, IL        | 5535 |
| Cincinnati, OH     |  694 |
| Columbus, OH       | 1084 |
| Dallas, TX         | 1567 |
| Denver, CO         |  312 |
| Detroit, MI        | 2519 |
| Durham, NC         |  276 |
| Fort Worth, TX     |  549 |
| Fresno, CA         |  487 |
| Houston, TX        | 2942 |
| Indianapolis, IN   | 1322 |
| Jacksonville, FL   | 1168 |
| Kansas City, MO    | 1190 |
| Las Vegas, NV      | 1381 |
| Long Beach, CA     |  378 |
| Los Angeles, CA    | 2257 |
| Louisville, KY     |  576 |
| Memphis, TN        | 1514 |
| Miami, FL          |  744 |
| Milwaukee, wI      | 1115 |
| Minneapolis, MN    |  366 |
| Nashville, TN      |  767 |
| New Orleans, LA    | 1434 |
| New York, NY       |  627 |
| Oakland, CA        |  947 |
| Oklahoma City, OK  |  672 |
| Omaha, NE          |  409 |
| Philadelphia, PA   | 3037 |
| Phoenix, AZ        |  914 |
| Pittsburgh, PA     |  631 |
| Richmond, VA       |  429 |
| Sacramento, CA     |  376 |
| San Antonio, TX    |  833 |
| San Bernardino, CA |  275 |
| San Diego, CA      |  461 |
| San Francisco, CA  |  663 |
| Savannah, GA       |  246 |
| St. Louis, MO      | 1677 |
| Stockton, CA       |  444 |
| Tampa, FL          |  208 |
| Tulsa, AL          |    1 |
| Tulsa, OK          |  583 |
| Washington, DC     | 1345 |

#### Summarize within cities to obtain the number of unsolved homicides (those for which the disposition is “Closed without arrest” or “Open/No arrest”).

``` r
homicide_unsolved = homicide_df %>% 
  mutate(
    homicide_statu =  ifelse(disposition != "Closed by arrest", "unsolved", "solved")) %>%
  group_by(city_state) %>% 
  summarize(
    n_unsolved = sum(homicide_statu == "unsolved")) 
homicide_unsolved %>% 
  knitr::kable()
```

| city_state         | n_unsolved |
|:-------------------|-----------:|
| Albuquerque, NM    |        146 |
| Atlanta, GA        |        373 |
| Baltimore, MD      |       1825 |
| Baton Rouge, LA    |        196 |
| Birmingham, AL     |        347 |
| Boston, MA         |        310 |
| Buffalo, NY        |        319 |
| Charlotte, NC      |        206 |
| Chicago, IL        |       4073 |
| Cincinnati, OH     |        309 |
| Columbus, OH       |        575 |
| Dallas, TX         |        754 |
| Denver, CO         |        169 |
| Detroit, MI        |       1482 |
| Durham, NC         |        101 |
| Fort Worth, TX     |        255 |
| Fresno, CA         |        169 |
| Houston, TX        |       1493 |
| Indianapolis, IN   |        594 |
| Jacksonville, FL   |        597 |
| Kansas City, MO    |        486 |
| Las Vegas, NV      |        572 |
| Long Beach, CA     |        156 |
| Los Angeles, CA    |       1106 |
| Louisville, KY     |        261 |
| Memphis, TN        |        483 |
| Miami, FL          |        450 |
| Milwaukee, wI      |        403 |
| Minneapolis, MN    |        187 |
| Nashville, TN      |        278 |
| New Orleans, LA    |        930 |
| New York, NY       |        243 |
| Oakland, CA        |        508 |
| Oklahoma City, OK  |        326 |
| Omaha, NE          |        169 |
| Philadelphia, PA   |       1360 |
| Phoenix, AZ        |        504 |
| Pittsburgh, PA     |        337 |
| Richmond, VA       |        113 |
| Sacramento, CA     |        139 |
| San Antonio, TX    |        357 |
| San Bernardino, CA |        170 |
| San Diego, CA      |        175 |
| San Francisco, CA  |        336 |
| Savannah, GA       |        115 |
| St. Louis, MO      |        905 |
| Stockton, CA       |        266 |
| Tampa, FL          |         95 |
| Tulsa, AL          |          0 |
| Tulsa, OK          |        193 |
| Washington, DC     |        589 |

#### 
