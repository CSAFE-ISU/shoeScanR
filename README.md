
<!-- README.md is generated from README.Rmd. Please edit that file -->

# shoeScanR

<!-- badges: start -->

<!-- badges: end -->

The goal of shoeScanR is to …

## Installation

Install the development version of shoeScanR from
[GitHub](https://github.com/) with:

``` r
# install.packages("devtools")
devtools::install_github("CSAFE-ISU/shoeScanR")
```

## Example

This is a basic example which shows you how to solve a common problem:

``` r
library(shoeScanR)
#> Loading required package: Rvcg
#> Loading required package: Arothron
#> Loading required package: rgl
#> Warning: package 'rgl' was built under R version 3.6.2
#> Loading required package: geometry
#> Loading required package: dplyr
#> Warning: package 'dplyr' was built under R version 3.6.2
#> 
#> Attaching package: 'dplyr'
#> The following objects are masked from 'package:stats':
#> 
#>     filter, lag
#> The following objects are masked from 'package:base':
#> 
#>     intersect, setdiff, setequal, union
#> Loading required package: tidyr
#> Warning: package 'tidyr' was built under R version 3.6.2
#> Loading required package: tibble
#> Warning: package 'tibble' was built under R version 3.6.2
#> Loading required package: magrittr
#> 
#> Attaching package: 'magrittr'
#> The following object is masked from 'package:tidyr':
#> 
#>     extract
#> Loading required package: assertthat
#> 
#> Attaching package: 'assertthat'
#> The following object is masked from 'package:tibble':
#> 
#>     has_name
## basic example code
```

  - minimal example of two scan parts that show the same shoe
  - visualize, and
  - work through alignment process

The following examples are using sony shoes (and absolute file paths,
which is a big NO), that’s going to be too complicated for the final
README:

``` r
# read scans
sony1 <- read_stl("/Users/heike/Documents/Data/shoe3d/data-raw/My_Scans/Asic06_03_19.stl")
#> Removed 6600453 duplicate 0 unreferenced vertices and 0 duplicate faces
sony2 <- read_stl("/Users/heike/Documents/Data/shoe3d/data-raw/My_Scans/SonyL_20190702.stl")
#> Removed 4683185 duplicate 0 unreferenced vertices and 0 duplicate faces

# center the scans
sony1 <- center3d(sony1)
sony2 <- center3d(sony2)
```

Visualize the scans

``` r
rgl::plot3d(sony2, aspect="iso", col="blue", add=TRUE)
rgl::plot3d(sony1, aspect="iso", col="green", add=TRUE)
axes3d()
```
