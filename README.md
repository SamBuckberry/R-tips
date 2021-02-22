# R-tips
## A place to store links and tips for R programming

### Updating R packages for CRAN and Bioconductor after upgrading R

First, save a list of currently installed packages
```
## Get currently installed packages
lib <- .libPaths()[1]

package_df <- as.data.frame(installed.packages(lib))

package_list <- as.character(package_df$Package)

write.table(package_list, "R_package_list.txt")
```
Now, install the latest version of R from (CRAN)[https://cran.r-project.org/]

Install and update Bioconductor. See https://bioconductor.org/install/ for something like
```
if (!requireNamespace("BiocManager", quietly = TRUE))
        install.packages("BiocManager")
BiocManager::install(version = "3.12")
```

Install all CRAN and Bioconductor packages using the BiocManager installer
```
pkg_list <- read.table("R_package_list.txt")
BiocManager::install(pkgs = pkg_list$x, site_repository = "CRAN")
```


### A really good R cheat-sheet
https://cran.r-project.org/doc/contrib/Baggott-refcard-v2.pdf

### The top 50 ggplot master list.
http://r-statistics.co/Top50-Ggplot2-Visualizations-MasterList-R-Code.html#Google%20Road%20Map

### Tables in R

A page with packages and examples for making beautifil tables in R.  
https://rfortherestofus.com/2019/11/how-to-make-beautiful-tables-in-r/
