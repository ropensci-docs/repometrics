# Collate code and repository data for a local R package.

This forms part of the data collated by the main
[repometrics_data](https://docs.ropensci.org/repometrics/reference/repometrics_data.md)
function, along with detailed data on individual contributors extracted
by the
[repometrics_data_user](https://docs.ropensci.org/repometrics/reference/repometrics_data_user.md)
function.

## Usage

``` r
repometrics_data_repo(path, date_interval = "month", num_cores = -1L)
```

## Arguments

- path:

  Path to local repository containing an R package.

- date_interval:

  Interval at which to analyse package statistics, with options of
  "day", "week", "month", or "year". The last commit for each period is
  chosen.

- num_cores:

  Number of cores to use in multi-core processing. Has no effect on
  Windows operating systems, on which calculations are always
  single-core only. Negative values are subtracted from number of
  available cores, determined as
  [`parallel::detectCores()`](https://rdrr.io/r/parallel/detectCores.html),
  so default of `num_cores = -1L` uses `detectCores() - 1L`. Positive
  values use precisely that number, restricted to maximum available
  cores, and a value of zero will use all available cores.

## Value

A list of two items:

1.  "pkgstats" Containing summary data from apply `pkgstats` routines
    across the git history of the repository.

2.  "rm" Containing data used to derive "CHAOSS metrics", primarily from
    GitHub data.

## See also

Other data:
[`repo_pkgstats_history()`](https://docs.ropensci.org/repometrics/reference/repo_pkgstats_history.md),
[`repometrics_data()`](https://docs.ropensci.org/repometrics/reference/repometrics_data.md),
[`repometrics_data_user()`](https://docs.ropensci.org/repometrics/reference/repometrics_data_user.md)
