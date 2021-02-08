# The csaw book

This repository contains a Bioconductor package to deploy the **csaw** user guide as a **bookdown** book.
Install all relevant packages used in the book with:

```r
BiocManager::install(remotes::local_package_deps(dependencies=TRUE))
```

Building the book can be done by either running the usual **bookdown** invocation in `inst/book`:

```r
bookdown::render_book("index.Rmd")
```

Or by `R CMD build` on the package itself to compile the book during the vignette build process.

To contribute reports, follow standard procedure: fork and PR.
This requires updating of files in `inst/rebook` to support links from external packages.
The updates are usually handled by the GitHub Action but can be done manually with:

```r
rebook::updateDependencies("inst/book", path='DESCRIPTION')
rebook::configureBook()
```
