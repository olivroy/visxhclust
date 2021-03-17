
<!-- README.md is generated from README.Rmd. Please edit that file -->

# visxhclust: visual exploration of hierarchical clustering

<!-- badges: start -->
<!-- badges: end -->

visxhclust is a package that consists mainly of a Shiny application for
**v**isual e**x**ploration of **h**ierarchical **c**lustering. It
implements hierarchical clustering for numeric data and includes various
plots and interactions to facilitate iterative workflows. Features
include:

-   Selection of variables supported by a correlation-driven t-test
-   Visual inspection of MDS and PCA projections
-   Visualisation of results through heatmap and boxplots
-   Validation by significance testing, internal validation scores and
    indices and computation of Gap statistic
-   Comparison of multiple cluster computations with Sankey plots
-   Saving and loading of settings and results

The app includes multiple help points in the interface, and the package
additionally exports various functions to help with documenting and
reproducing a clustering workflow in R Markdown – check
`vignette("clusterworkflow")` for an example.

## Installation

The package can be installed from github using:

``` r
remotes::install_github("rhenkin/visxchlust")
```

Most packages are from CRAN. However, three packages are part of
[Bioconductor](http://www.bioconductor.org/) and may require a separate
installation:

``` r
install.packages("BiocManager")
BiocManager::install(c("ComplexHeatmap", "circlize", "dendextend"))
```

## Requirements and usage

Basic usage of the tool has one single requirement: a column named `ID`
to identify each data point. The tool supports loading RDS, CSV and TSV
(or TXT tab-delimited) files. It will automatically treat text fields as
columns used to annotate the heatmap.

Clustering requires complete datasets with no empty values, NULLs or
NAs. If any column contains missing values, it will be set aside to be
used as a heatmap annotation. Imputation packages can be used to fill
missing data or the faulty rows should be removed before loading the
file into the tool.

To run the app once the package is installed:

``` r
library(visxhclust)
run_app()
```