
<!-- README.md is generated from README.Rmd. Please edit that file -->

# alphaN <img src="man/figures/logo.png" align="right" height="120" />

<!-- badges: start -->

[![CRAN
Version](https://www.r-pkg.org/badges/version/alphaN)](https://cran.r-project.org/package=alphaN)
[![Downloads](https://cranlogs.r-pkg.org/badges/alphaN?color=brightgreen)](https://CRAN.R-project.org/package=alphaN)
[![R-CMD-check](https://github.com/jespernwulff/alphaN/actions/workflows/R-CMD-check.yaml/badge.svg)](https://github.com/jespernwulff/alphaN/actions/workflows/R-CMD-check.yaml)
<!-- badges: end -->

The goal of alphaN is to help the user set their significance level as a
function of the sample size. The function `alphaN` allows users to set
the significance level as function of the sample size based on the
evidence and the prior features they desire. The function `JABt` and
`JABp` converts test statistics and $p$-values into sample size
dependent Bayes factors. `JAB_plot` plots the Bayes factor as a function
of the $p$-value, and `alphaN_plot` plots the alpha level as a function
of sample size for a given Bayes factor.

Calculations are based on [Wulff & Taylor
(2024)](https://doi.org/10.31234/osf.io/3cbh7). If you enjoy the
package, please consider citing the paper.

If you’re not an R user, you may also be interested in the associated
[Shiny app](https://crossvalidated.shinyapps.io/alphaN/).

## Installation

To install the latest release version from CRAN use:

``` r
install.packages("alphaN")
```

You can install the development version of alphaN from
[GitHub](https://github.com/) with:

``` r
# install.packages("devtools")
devtools::install_github("jespernwulff/alphaN")
```

## Example

Here is an example: We are planning to run a linear regression model
with 1000 observations. We thus set `n = 1000`. The default `BF` is 1
meaning that we want to avoid Lindley’s paradox, i.e., we just want the
null and the alternative to be at least equally likely when we reject
the null.

``` r
library(alphaN)

alpha <- alphaN(n = 1000, BF = 1)
alpha
#> [1] 0.008582267
```

Therefore, to obtain evidence of at least 1, we should set our alpha to
0.0086.
