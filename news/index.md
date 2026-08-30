# Changelog

## getCRUCLdata 2.0.0

CRAN release: 2026-05-20

### Major changes

- Almost a complete rewrite of the package.

- R \>= 4.1.0 is now required.

- `create_CRU_stack()` and `create_CRU_df()` functions have been
  removed.

- `get_CRU_stack()` and `get_CRU_df()` functions have been removed.

- New functions
  [`read_cru_rast()`](https://docs.ropensci.org/getCRUCLdata/reference/read_cru_rast.md)
  to align with {terra} naming and
  [`read_cru_dt()`](https://docs.ropensci.org/getCRUCLdata/reference/read_cru_dt.md)
  to align with {data.table} naming have been added to either download
  or load data from local files using a single unified function.

- Caching is no longer supported, this is both to simplify the package
  and to avoid issues with CRAN policies. Users are encouraged to manage
  their own caching solutions if needed, *e.g.*, {targets} or save the
  data locally after downloading using their preferred format and
  methods.

### Minor changes

- Update documentation to reflect new functionality.

- Improvements to the file handling and object creation to be more
  efficient and faster.

## getCRUCLdata 1.0.3

CRAN release: 2025-02-08

### Major Changes

- `create_CRU_stack()` and `create_CRU_df()` now only work with locally
  available files. If you need to fetch and create a data frame or
  raster stack of the data, please use the new functions,
  `get_CRU_stack()` and `get_CRU_stack()`.

- R \>=3.2.0 now required.

- Data can be cached using either `get_CRU_stack()` or `get_CRU_df()`
  for later use.

### Minor Changes

- Improved documentation with examples on mapping and graphing and more
  detail regarding the data itself.

- Change the method in which files are downloaded to use `httr::GET()`.

- Ingest data using
  [`data.table::fread`](https://rdrr.io/pkg/data.table/man/fread.html)
  to decrease the amount of time necessary to run the functions.

- Functions check to see if data file(s) have already been downloaded
  during current R session, if so data file(s) are not requested for
  download again.

- Months are returned as a factor object in the tidy data frame.

## getCRUCLdata 0.1.4

CRAN release: 2017-02-03

### Minor Changes

- Correct fix bug in data frame object generation where elevation was
  improperly handled and function would stop.

## getCRUCLdata 0.1.3

CRAN release: 2017-02-01

### Minor Changes

- Correct fix bug in raster object generation where the objects were
  incorrectly cropped.

- Update documentation with ROxygen 6.0.0.

- Minor edits to documentation for clarity.

## getCRUCLdata 0.1.2

CRAN release: 2017-01-18

### Minor Changes

- Correct documentation to read that the data resolution is 10 minute,
  not 10 seconds.

- Correct URLs in DESCRIPTION file.

- Add required version for {purrr}.

- Add required version for R.

- Corrected URL pointing to CRU readme.txt file.

## getCRUCLdata 0.1.1

CRAN release: 2017-01-05

### Minor Changes

- Renamed to {getCRUdata} as suggested by CRAN maintainers.

- Revised description file as requested by CRAN maintainers.

- Enhanced vignette.

### getCRUCL2.0 0.1.0

- Initial submission to CRAN.
