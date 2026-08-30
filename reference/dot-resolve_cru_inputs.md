# Resolve CRU variable flags and input file paths

Internal helper used by higher-level CRU readers to convert user-facing
arguments (e.g., `pre = TRUE`, `tmp = TRUE`, `x = <dir>`) into a
standardised structure containing:

## Usage

``` r
.resolve_cru_inputs(pre = FALSE, tmp = FALSE, x = NULL, ...)
```

## Arguments

- pre:

  Logical. Whether precipitation (`pre`) is requested.

- tmp:

  Logical. Whether temperature (`tmp`) is requested.

- x:

  Character. Either a directory containing CRU files or one or more CRU
  `.dat.gz` file paths.

- ...:

  Ignored. Allows future expansion.

## Value

A list with two elements:

- vars:

  Named logical vector of CRU variable flags.

- files:

  Character vector of resolved CRU file paths.

## Details

- a named logical vector of requested CRU variables (`vars`)

- a character vector of file paths (`files`)

If `x` is a directory, all matching CRU files (`grid_10min_*.dat.gz`)
inside that directory are returned. If `x` is one or more file paths,
they are returned unchanged.

This function does **not** read or validate file contents; it only
resolves which files should be processed downstream.
