# Extract CRU variable names from file paths

Strips the `grid_10min_` prefix and `.dat.gz` suffix from CRU filenames,
returning the bare variable identifier (e.g. "pre", "pre_cv", "elv").

## Usage

``` r
.cru_varname(files)
```

## Arguments

- files:

  Character vector of CRU `.dat.gz` file paths.

## Value

Character vector of variable names.
