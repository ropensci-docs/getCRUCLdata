# Ensure gzip support is available for reading .gz files

Internal helper used by both .tidy_dt() and .create_rast().

## Usage

``` r
.check_gzip_support(files)
```

## Arguments

- files:

  Character vector of file paths.

## Value

An invisible `TRUE` if support is found.

## Details

Aborts if .gz files are present and neither R.utils nor system gzip is
available.
