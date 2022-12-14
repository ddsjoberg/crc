
<!-- README.md is generated from README.Rmd. Please edit that file -->

# crc <a href="http://www.danieldsjoberg.com/crc/"><img src="man/figures/logo.png" align="right" height="138" /></a>

<!-- badges: start -->

[![R-CMD-check](https://github.com/ddsjoberg/crc/actions/workflows/R-CMD-check.yaml/badge.svg)](https://github.com/ddsjoberg/crc/actions/workflows/R-CMD-check.yaml)
[![Codecov test
coverage](https://codecov.io/gh/ddsjoberg/crc/branch/main/graph/badge.svg)](https://app.codecov.io/gh/ddsjoberg/crc?branch=main)
<!-- badges: end -->

Use two independently estimated risks of death from other causes and
death from disease to get a corrected estimate of risk of death from
disease. For example, given a patient’s risk of death from cancer based
on their oncologic burden and their risk of death from other causes
based on their comorbidities, we calculate an adjusted risk of death
from cancer. To illustrate the importance of this correction, image two
patients with identical disease burden, and therefore, identical
predicted risk of death from disease. Now imagine, that one of these
patients also has sever heart disease and it likely we pass away from
hear disease before they would succumb to the cancer. Our correction
makes the appropriate update to the risk of death from disease
incorporating the risk of death from other causes.

## Installation

You can install the development version of crc from
[GitHub](https://github.com/) with:

``` r
# install.packages("devtools")
devtools::install_github("ddsjoberg/crc")
```

## Example

In the example below, we see how the risk for two patients are updated:
one healthy and the other comorbid with a high probability of death from
other causes.

``` r
library(crc)

update_cancer_death_risk(
  risk_cancer_death = c(0.2, 0.2),
  risk_other_cause = c(0.01, 0.95),
  time = 10
)
#> [1] 0.1990355 0.0665505
```
