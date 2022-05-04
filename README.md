
<!-- README.md is generated from README.Rmd. Please edit that file -->

# codebook

<!-- badges: start -->
<!-- badges: end -->

The codebook package is intended to make it easy for users to create
codebooks (i.e. data dictionaries) directly from data frame.

## Installation

You can install the development version of codebook like so:

``` r
# install.packages("devtools")
devtools::install_github("brad-cannell/codebook")
```

## Simple example

This simple example demonstrates how to use the `codebook` package to
make a codebook from a **labeled** data frame.

``` r
library(codebook)
library(dplyr, warn.conflicts = FALSE)
```

### Load data

By default, `codebook` assumes that you want to make a codebook about a
dataset file that you have saved somewhere, as opposed to a data frame
you’re working on in an r session, but don’t intend to save. Therefore,
the first thing you will need to do is read the data into the current R
session.

For the purposes of making a self-contained example, the codebook
package comes with a small example data frame that is intended to have
some of the features of real study data. We will use it to demonstrate
how to use `codebook` below.

``` r
# Load example data
data(study)
```

### Column types

`codebook` classifies all columns as one of four types and uses these
categories to determine which descriptive statistics are given in the
codebook document:

1.  Categorical with many different categories, for example the `id`
    column of the `study` data frame.  
2.  Categorical with few different categories, for example the `gender`
    column of the `study` data frame.  
3.  Date, for example the `date` column of the `study` data frame.  
4.  Numeric, for example the `height` column of the `study` data frame.