# Remove source vars if not requested

If `tmin` or `tmax` are requested but `tmp` or `dtr` are not requested,
this function drops the unrequested vars.

## Usage

``` r
.drop_source_vars_dt(dt, vars)
```

## Arguments

- dt:

  A data.table object of CRU data containing `tmp` and `dtr` in order to
  calculate tmin and tmax.

- vars:

  A named logical vector.

## Value

A data.table with the unrequested var columns removed.
