# Extract and combine data on all contributors to a repository.

This forms part of the data collated by the main
[repometrics_data](https://docs.ropensci.org/repometrics/reference/repometrics_data.md)
function, along with data on repository structure and historical
developed extracted by the
[repometrics_data_repo](https://docs.ropensci.org/repometrics/reference/repometrics_data_repo.md)
function.

## Usage

``` r
repometrics_data_user(
  login,
  end_date = Sys.Date(),
  nyears = 1,
  n_per_page = 100
)
```

## Arguments

- login:

  GitHub login of user

- end_date:

  Parameter used in some aspects of resultant data to limit the end date
  of data collection. Defaults to
  [`Sys.Date ()`](https://rdrr.io/r/base/Sys.time.html).

- nyears:

  Parameter \<= 1 determining fraction of a year over which data up
  until `end_date` are collected.

- n_per_page:

  Number of items per page to pass to GitHub GraphQL API requests. This
  should never need to be changed.

## Value

A list of the following `data.frame` objects:

1.  `commit_cmt` with details of commits made on commits

2.  `commits` with summaries of all repositories to which user made
    commits

3.  `followers` A list of followers of specified user

4.  `following` A list of other people who nominated user is following

5.  `general` with some general information about specified user

6.  `issue_cmts` with information on all issue comments made by user

7.  `issues` with information on all issues opened by user

## See also

Other data:
[`repo_pkgstats_history()`](https://docs.ropensci.org/repometrics/reference/repo_pkgstats_history.md),
[`repometrics_data()`](https://docs.ropensci.org/repometrics/reference/repometrics_data.md),
[`repometrics_data_repo()`](https://docs.ropensci.org/repometrics/reference/repometrics_data_repo.md)
