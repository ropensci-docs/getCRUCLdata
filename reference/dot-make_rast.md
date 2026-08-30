# Internal helper for creating terra layers

Internal helper for creating terra layers

Internal helper for creating terra layers

## Usage

``` r
.make_rast(file, wrld, vars, varname)

.make_rast(file, wrld, vars, varname)
```

## Arguments

- file:

  CRU .dat.gz file path.

- wrld:

  Empty
  [`terra::rast`](https://rspatial.github.io/terra/reference/rast.html)
  template.

- vars:

  Named logical vector of CRU variable selections.

## Value

A [terra::rast](https://rspatial.github.io/terra/reference/rast.html)
object for one variable.

A [terra::rast](https://rspatial.github.io/terra/reference/rast.html)
object for one variable.
