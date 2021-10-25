The Big-Mac Index - Project Proposal
================
The Code Ninjas

``` r
library(tidyverse)
library(broom)
```

## 1. Introduction

In this project, we are going to measure the purchasing power parity
also known as PPP between countries, and to do this, we are going to use
the “Big-mac Index” data.

The Big-mac index tells us approximately how many MacDonald’s Big Macs
can be bought in different places with the same amount of money. The
data survey is created by ‘The Economist’ in 1986 and collected from
areas worldwide.

In this dataset, there are 1,386 observations and 19 variables; date,
country code, currency code, country name, price of the big-mac in the
local currency, local currency units per dollar, price of Big Mac in
dollars, raw index relative to the (US dollar, Euro, British pound,
Japanese yen, Chinese yuan), GDP per person in dollars, GDP-adjusted
price of a Big-Mac in dollars, and adjusted index relative to the (US
dollar, Euro, British pound, Japanese yen, Chinese yuan). Each row
represents a country at a specific time (year-month-date).

## 2. Data

## 3. Data analysis plan

Variables:

We aim to use a number of variables from the data set to answer our
question, including GDP\_dollar against respective countries and
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
will be done by using the “gdp\_dollar” variable along with the
countries respective exchange rate. Another possible question we could
analyse is the difference in GDP between different countries post and
pre-Covid then getting a percentage change, the assumption is that GDP
will have decreased in most countries after Covid compared to the year
before the pandemic.This will also use the gdp\_dollar variable. There
will also be signficant variations in exchange rates after the pandemic
also which will be analysed in the project.
