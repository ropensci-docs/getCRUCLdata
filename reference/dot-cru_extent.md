# CRU CL 2.0 output crop extent

Crops all raster outputs to ymin = -60, ymax = 85, xmin = -180, xmax =
180, matching the stated coverage of the CRU CL 2.0 dataset in the
package's README. This crops the wind data that cover the Antarctic
region.

## Usage

``` r
.cru_extent()
```

## Value

A terra::ext object.
