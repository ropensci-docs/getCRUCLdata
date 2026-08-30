# For `elv`: produces a single-layer raster with bad coordinates masked to NA. For all other variables: produces 12 layers (one per month), named `<varname>_<month>`.

For `elv`: produces a single-layer raster with bad coordinates masked to
NA. For all other variables: produces 12 layers (one per month), named
`<varname>_<month>`.

## Usage

``` r
.dt_to_rast(dt, varname)
```

## Arguments

- dt:

  A tidy data.table with columns: lat, lon, value, and (for non-elv
  variables) month.

- varname:

  Character scalar: variable identifier (e.g., "tmp", "pre", "elv").

## Value

A [terra::rast](https://rspatial.github.io/terra/reference/rast.html) -
one layer for elv, 12 layers for all others.
