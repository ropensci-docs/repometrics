# Collate 'repometrics' data for a local R package.

This function collates all data for a local R package or repository
needed to create a dashboard with the
[repometrics_dashboard](https://docs.ropensci.org/repometrics/reference/repometrics_dashboard.md)
function. It combines data from both the
[repometrics_data_repo](https://docs.ropensci.org/repometrics/reference/repometrics_data_repo.md)
and
[repometrics_data_user](https://docs.ropensci.org/repometrics/reference/repometrics_data_user.md)
functions.

## Usage

``` r
repometrics_data(
  path,
  date_interval = "month",
  num_cores = -1L,
  end_date = Sys.Date(),
  nyears = 1
)
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

- end_date:

  Parameter used in some aspects of resultant data to limit the end date
  of data collection. Defaults to
  [`Sys.Date ()`](https://rdrr.io/r/base/Sys.time.html).

- nyears:

  Parameter \<= 1 determining fraction of a year over which data up
  until `end_date` are collected.

## Value

A list of five items:

1.  "pkgstats" containing statistics on the historical development of
    package code, derived from the pkgstats package;

2.  "rm" containing data from GitHub on the repository, including data
    on contributors, issues, pull requests, and people watching and
    starring the repository.

3.  "contributors" as a named list of data on every individual
    contributor to the repository, whether by code contributions or
    GitHub issues or discussions.

4.  "rm_metrics" as a list of values for all CHAOSS metrics defined in
    the output of
    [rm_metrics_list](https://docs.ropensci.org/repometrics/reference/rm_metrics_list.md).

5.  "rm_models" as a list of values for CHAOSS models, derived from
    aggregating various metrics.

## See also

Other data:
[`repo_pkgstats_history()`](https://docs.ropensci.org/repometrics/reference/repo_pkgstats_history.md),
[`repometrics_data_repo()`](https://docs.ropensci.org/repometrics/reference/repometrics_data_repo.md),
[`repometrics_data_user()`](https://docs.ropensci.org/repometrics/reference/repometrics_data_user.md)
