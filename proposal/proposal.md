The Big-Mac Index - Project Proposal
================
The Code Ninjas

``` r
library(tidyverse)
library(broom)
```

## 1. Introduction

Our research question is “What is Purchasing Power Parity (PPP) and how
has it changed over the years across countries?”

To find this out, we are going to use the “Big-mac Index” data and this
tells us approximately how many MacDonald’s Big Macs can be bought in
different places with the same amount of money. The data survey is
created by ‘The Economist’ in 1986 and collected from areas worldwide.

In this dataset, there are 1,520 observations and 19 variables; date,
country code, currency code, country name, price of the big-mac in the
local currency, local currency units per dollar, price of Big Mac in
dollars, raw index relative to the (US dollar, Euro, British pound,
Japanese yen, Chinese yuan), GDP per person in dollars, GDP-adjusted
price of a Big-Mac in dollars, and adjusted index relative to the (US
dollar, Euro, British pound, Japanese yen, Chinese yuan). Each row
represents a country at a specific time (year-month-date). The data is
accountable for the years 2000-2020.

The Big Mac prices are from McDonald’s, and the exchange rates are from
Thomson Reuters. The GDP per person data is from the IMF World Economic
Outlook reports.

## 2. Data

``` r
big_mac_full_index = read.csv(file = "/cloud/project/data/big-mac-data-2021-07.1/output-data/big-mac-full-index.csv")

glimpse(big_mac_full_index)
```

    ## Rows: 1,520
    ## Columns: 19
    ## $ date          <chr> "2000-04-01", "2000-04-01", "2000-04-01", "2000-04-01", …
    ## $ iso_a3        <chr> "ARG", "AUS", "BRA", "CAN", "CHE", "CHL", "CHN", "CZE", …
    ## $ currency_code <chr> "ARS", "AUD", "BRL", "CAD", "CHF", "CLP", "CNY", "CZK", …
    ## $ name          <chr> "Argentina", "Australia", "Brazil", "Canada", "Switzerla…
    ## $ local_price   <dbl> 2.50, 2.59, 2.95, 2.85, 5.90, 1260.00, 9.90, 54.37, 24.7…
    ## $ dollar_ex     <dbl> 1.0000000, 1.6800000, 1.7900000, 1.4700000, 1.7000000, 5…
    ## $ dollar_price  <dbl> 2.500000, 1.541667, 1.648045, 1.938776, 3.470588, 2.4513…
    ## $ USD_raw       <dbl> -0.00398, -0.38579, -0.34341, -0.22758, 0.38270, -0.0233…
    ## $ EUR_raw       <dbl> 0.05007, -0.35246, -0.30778, -0.18566, 0.45774, 0.02964,…
    ## $ GBP_raw       <dbl> -0.16722, -0.48645, -0.45102, -0.35417, 0.15609, -0.1834…
    ## $ JPY_raw       <dbl> -0.09864, -0.44416, -0.40581, -0.30099, 0.25130, -0.1161…
    ## $ CNY_raw       <dbl> 1.09091, 0.28939, 0.37836, 0.62152, 1.90267, 1.05023, 0.…
    ## $ GDP_dollar    <dbl> NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, …
    ## $ adj_price     <dbl> NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, …
    ## $ USD_adjusted  <dbl> NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, …
    ## $ EUR_adjusted  <dbl> NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, …
    ## $ GBP_adjusted  <dbl> NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, …
    ## $ JPY_adjusted  <dbl> NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, …
    ## $ CNY_adjusted  <dbl> NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, …

## 3. Data analysis plan

Variables:

We aim to use a number of variables from the data set to answer our
question, including GDP_dollar against respective countries and
calculated PPP.

Visualisations:

At this point we believe the best visualisation to demonstrate our
findings will be a bar chart which plots GDP changes, as the countries
act as categorical variables which are best placed in this form. To
observe further variables we may use a segmented bar plot with the
argument position = “fill” to expand the bars and allow easier
comparisons of proportions. To compare years and countries we may facet
the bar plots too.

Statistical methods:

The main use of the big mac index is to calculate PPP using the relative
price of a big mac in one country compared to another then seeing how
this compares to the exchange rate of the two countries, therefore a lot
of calculations in this data set will be dividing the local price of one
big mac by the local price in another. However this is not the only
statistical methods that will be used in the project, we will be using
dollars as the base currency, therefore we will be able to calculate the
average exchange rate between all countries compared to the dollar
within a certain year. We can then use other methods to find the median,
standard deviation, IQR etc. of these values.

Hypothesized results:

One question we are going to try and answer is “Is Purchasing Power
Parity higher in High GDP countries compared to low GDP countries” This
will be done by using the “gdp_dollar” variable along with the countries
respective exchange rate. Another possible question we could analyse is
the difference in GDP between different countries post and pre-Covid
then getting a percentage change, the assumption is that GDP will have
decreased in most countries after Covid compared to the year before the
pandemic.This will also use the gdp_dollar variable. There will also be
significant variations in exchange rates after the pandemic also which
will be analysed in the project.

Preliminary Exploratory Analysis:

To get an initial idea of the exchange rates in high GDP vs low GDP
countries we can compare the average dollar price of a Big Mac over the
years for a high GDP country like Britain versus a lower GDP country
like Indonesia.

``` r
big_mac_full_index %>%
  filter(name == "Britain") %>%
  summarise(mean_dollar = mean(dollar_price))
```

    ##   mean_dollar
    ## 1    3.947897

``` r
big_mac_full_index %>%
  filter(name == "Indonesia") %>%
  summarise(mean_dollar = mean(dollar_price))
```

    ##   mean_dollar
    ## 1    2.180917

We can see that the mean dollar price over the years for a Big Mac in
Britain was $3.95 versus $2.18 in Indonesia. This suggests that over the
21 years of data recording, on average you pay more for a Big Mac in
Britain than in Indonesia. This is obviously just a small glimpse into a
much broader situation, and other countries over time need to be
explored, but it is an interesting statistic to consider.
