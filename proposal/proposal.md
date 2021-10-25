The Big-Mac Index - Project Proposal
================
The Code Ninjas

``` r
library(tidyverse)
library(broom)
```

*For instructions on what each section should include, please see the
[project page](https://idsed.digital/assessments/project/#proposal) on
the course website. Remove this text when completing your proposal*.

## 1. Introduction

## 2. Data

## 3. Data analysis plan

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
