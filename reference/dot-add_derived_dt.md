# Add derived temperature values for TMAX and TMIN

Add derived temperature values for TMAX and TMIN

## Usage

``` r
.add_derived_dt(dt, vars)
```

## Arguments

- dt:

  A data.table object of CRU data containing `tmp` and `dtr` in order to
  calculate tmin and tmax.

- vars:

  A named logical vector.

## Value

A data.table with tmin and or tmax cols.
