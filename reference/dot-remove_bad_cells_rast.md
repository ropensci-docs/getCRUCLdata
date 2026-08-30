# Mask bad cells in a SpatRaster

Sets the package-level `.bad_coords` cells to NA. Used exclusively for
the elevation layer.

## Usage

``` r
.remove_bad_cells_rast(r)
```

## Arguments

- r:

  A [terra::rast](https://rspatial.github.io/terra/reference/rast.html)
  to modify.

## Value

The modified
[terra::rast](https://rspatial.github.io/terra/reference/rast.html).
