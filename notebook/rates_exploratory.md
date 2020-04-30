Exploring sequestration rates for trees in crop and pasture lands
(global)
================
Millie Chapman
4/29/2020

Just a first pass at calcualting rates of sequestration for trees in
crop and pasture
    lands.

``` r
library(tidyverse)
```

    ## ── Attaching packages ────────────────────────────────────────────── tidyverse 1.3.0 ──

    ## ✓ ggplot2 3.2.1.9000     ✓ purrr   0.3.3     
    ## ✓ tibble  2.1.3          ✓ dplyr   0.8.3     
    ## ✓ tidyr   1.0.0          ✓ stringr 1.4.0     
    ## ✓ readr   1.3.1          ✓ forcats 0.4.0

    ## ── Conflicts ───────────────────────────────────────────────── tidyverse_conflicts() ──
    ## x dplyr::filter() masks stats::filter()
    ## x dplyr::lag()    masks stats::lag()

``` r
library(ggplot2)
```

Pull in mean growth rates from (Feliciano et al. 2018)

``` r
growth_rates <- read_csv("../data/growth_rates.csv")
```

    ## Parsed with column specification:
    ## cols(
    ##   continent = col_character(),
    ##   agroforestry_system = col_character(),
    ##   mean = col_double(),
    ##   variance = col_double(),
    ##   n = col_double(),
    ##   CP = col_character()
    ## )

Read in standing biomass histograms

``` r
crop_hist <- read_csv("../data/crop_hist_25.csv") 
```

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_character(),
    ##   ABBREV_LEN = col_double(),
    ##   ADM0_A3_UN = col_double(),
    ##   ADM0_A3_WB = col_double(),
    ##   ADM0_DIF = col_double(),
    ##   BIOME_NUM = col_double(),
    ##   BRK_DIFF = col_double(),
    ##   BRK_GROUP = col_logical(),
    ##   ECO_ID = col_double(),
    ##   GDP_MD_EST = col_double(),
    ##   GDP_YEAR = col_double(),
    ##   GEOU_DIF = col_double(),
    ##   HOMEPART = col_double(),
    ##   LABELRANK = col_double(),
    ##   LASTCENSUS = col_double(),
    ##   LEVEL = col_double(),
    ##   LONG_LEN = col_double(),
    ##   MAPCOLOR13 = col_double(),
    ##   MAPCOLOR7 = col_double(),
    ##   MAPCOLOR8 = col_double(),
    ##   MAPCOLOR9 = col_double()
    ##   # ... with 19 more columns
    ## )

    ## See spec(...) for full column specifications.

    ## Warning: 3 parsing failures.
    ##  row       col           expected            actual                       file
    ## 1348 BRK_GROUP 1/0/T/F/TRUE/FALSE Channel Islands   '../data/crop_hist_25.csv'
    ## 1351 BRK_GROUP 1/0/T/F/TRUE/FALSE Channel Islands   '../data/crop_hist_25.csv'
    ## 1490 BRK_GROUP 1/0/T/F/TRUE/FALSE Jammu and Kashmir '../data/crop_hist_25.csv'

``` r
pasture_hist <- read_csv("../data/pasture_hist_25.csv")
```

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_character(),
    ##   ABBREV_LEN = col_double(),
    ##   ADM0_A3_UN = col_double(),
    ##   ADM0_A3_WB = col_double(),
    ##   ADM0_DIF = col_double(),
    ##   BIOME_NUM = col_double(),
    ##   BRK_DIFF = col_double(),
    ##   ECO_ID = col_double(),
    ##   GDP_MD_EST = col_double(),
    ##   GDP_YEAR = col_double(),
    ##   GEOU_DIF = col_double(),
    ##   HOMEPART = col_double(),
    ##   ISO_N3 = col_double(),
    ##   LABELRANK = col_double(),
    ##   LASTCENSUS = col_double(),
    ##   LEVEL = col_double(),
    ##   LONG_LEN = col_double(),
    ##   MAPCOLOR13 = col_double(),
    ##   MAPCOLOR7 = col_double(),
    ##   MAPCOLOR8 = col_double(),
    ##   MAPCOLOR9 = col_double()
    ##   # ... with 20 more columns
    ## )
    ## See spec(...) for full column specifications.

## References

<div id="refs" class="references">

<div id="ref-feliciano2018agroforestry">

Feliciano, Diana, Alicia Ledo, Jon Hillier, and Dali Rani Nayak. 2018.
“Which Agroforestry Options Give the Greatest Soil and Above Ground
Carbon Benefits in Different World Regions?” *Agriculture, Ecosystems &
Environment* 254. Elsevier: 117–29.

</div>

</div>
