<!-- README.md is generated from README.Rmd. Please edit that file -->



# congress

<!-- badges: start -->
[![Travis build status](https://travis-ci.org/kjhealy/congress.svg?branch=master)](https://travis-ci.org/kjhealy/congress)
<!-- badges: end -->

`congress` is a dataset of individuals who have served in the US Congress since 1945. Each row is an individual's spell in Congress in some elected office: US Representative, US Senator, President, or Vice-President.

## Installation


The `congress` package contains term-level data on every US Congressional Representative (House, Senate, Presidency, Vice-Presidency) between 1945 (the 79th Congress) and 2019 (the 116th Congress). The data includes information on the representative's demographic characteristics and political affiliation.


## Installation

`congress` is a data package. The relatively large size of the data in the package means it is not suitable for hosting on [CRAN](https://cran.r-project.org/), the core R package repository. There are two ways to install it.

### Install direct from GitHub

You can install the beta version of congress from [GitHub](https://github.com/kjhealy/congress) with:

``` r
devtools::install_github("kjhealy/congress")
```

### Installation using `drat`

While using `install_github()` works just fine, it would be nicer to be able to just type `install.packages("congress")` or `update.packages("congress")` in the ordinary way. We can do this using Dirk Eddelbuettel's [drat](http://eddelbuettel.github.io/drat/DratForPackageUsers.html) package. Drat provides a convenient way to make R aware of package repositories other than CRAN.

First, install `drat`:


```r
if (!require("drat")) {
    install.packages("drat")
    library("drat")
}
```

Then use `drat` to tell R about the repository where `congress` is hosted:


```r
drat::addRepo("kjhealy")
```

You can now install `congress`:


```r
install.packages("congress")
```

To ensure that the `congress` repository is always available, you can add the following line to your `.Rprofile` or `.Rprofile.site` file:


```r
drat::addRepo("kjhealy")
```

With that in place you'll be able to do `install.packages("congress")` or `update.packages("congress")` and have everything work as you'd expect. 

Note that the drat repository only contains data packages that are not on CRAN, so you will never be in danger of grabbing the wrong version of any other package.


## Loading the data

The data is stored as a tibble and works best with (but does not strictly require) the [tidyverse](http://tidyverse.org/) libraries.


```r
library(tidyverse)
```

Load the data:


```r
library(congress)
```

To look at the tibble that contains the data, do this:


```r
congress
#> # A tibble: 21,009 x 32
#>    congress   pid last  first middle suffix born       death      sex  
#>       <dbl> <dbl> <chr> <chr> <chr>  <chr>  <date>     <date>     <chr>
#>  1       79     1 Aber… Thom… Gerst… <NA>   1903-05-16 1953-01-23 M    
#>  2       79     2 Adams Sher… <NA>   <NA>   1899-01-08 1986-10-27 M    
#>  3       79     3 Aiken Geor… David  <NA>   1892-08-20 1984-11-19 M    
#>  4       79     4 Allen Asa   Leona… <NA>   1891-01-05 1969-01-05 M    
#>  5       79     5 Allen Leo   Elwood <NA>   1898-10-05 1973-01-19 M    
#>  6       79     6 Almo… J.    Linds… Jr.    1898-06-15 1986-04-14 M    
#>  7       79     7 Ande… Herm… Carl   <NA>   1897-01-27 1978-07-26 M    
#>  8       79     8 Ande… Clin… Presba <NA>   1895-10-23 1975-11-11 M    
#>  9       79     9 Ande… John  Zuing… <NA>   1904-03-22 1981-02-09 M    
#> 10       79    10 Andr… Augu… Herman <NA>   1890-10-11 1958-01-14 M    
#> # … with 20,999 more rows, and 23 more variables: position <chr>,
#> #   party <chr>, state <chr>, district <chr>, start <date>, end <chr>,
#> #   religion <chr>, race <chr>, education <chr>, occ1 <chr>, occ2 <chr>,
#> #   occ3 <chr>, mil1 <chr>, mil2 <chr>, mil3 <chr>, start_year <date>,
#> #   end_year <date>, start_age <int>, poc <chr>, days_old <dbl>,
#> #   entry_age <int>, end_career <date>, yr_fac <fct>
```
