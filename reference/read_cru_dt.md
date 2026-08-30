# Create a data.table of CRU CL v. 2.0 climatology elements

Automates importing CRU CL v.2.0 climatology data and from either the
CRU server or local files and creates a
[data.table](https://CRAN.R-project.org/package=data.table) of the data.
If requested, minimum and maximum temperature may also be calculated as
described in the data
[readme.txt](https://crudata.uea.ac.uk/cru/data/hrg/tmc/readme.txt) file
and returned.

## Usage

``` r
read_cru_dt(
  pre = FALSE,
  pre_cv = FALSE,
  rd0 = FALSE,
  tmp = FALSE,
  dtr = FALSE,
  reh = FALSE,
  tmn = FALSE,
  tmx = FALSE,
  sunp = FALSE,
  frs = FALSE,
  wnd = FALSE,
  elv = FALSE,
  x = NULL
)
```

## Source

- pre:

  <https://crudata.uea.ac.uk/cru/data/hrg/tmc/grid_10min_pre.dat.gz>

- rd0:

  <https://crudata.uea.ac.uk/cru/data/hrg/tmc/grid_10min_rd0.dat.gz>

- tmp:

  <https://crudata.uea.ac.uk/cru/data/hrg/tmc/grid_10min_tmp.dat.gz>

- dtr:

  <https://crudata.uea.ac.uk/cru/data/hrg/tmc/grid_10min_dtr.dat.gz>

- reh:

  <https://crudata.uea.ac.uk/cru/data/hrg/tmc/grid_10min_reh.dat.gz>

- sunp:

  <https://crudata.uea.ac.uk/cru/data/hrg/tmc/grid_10min_sunp.dat.gz>

- frs:

  <https://crudata.uea.ac.uk/cru/data/hrg/tmc/grid_10min_frs.dat.gz>

- wnd:

  <https://crudata.uea.ac.uk/cru/data/hrg/tmc/grid_10min_wnd.dat.gz>,
  areas originally including Antarctica are removed.

- elv:

  <https://crudata.uea.ac.uk/cru/data/hrg/tmc/grid_10min_elv.dat.gz>,
  values are converted from kilometres to metres.

This package crops all spatial outputs to an extent of ymin = -60, ymax
= 85, xmin = -180, xmax = 180.

## Arguments

- pre:

  Read precipitation (millimetres/month) and return it, `TRUE`. Defaults
  to `FALSE`.

- pre_cv:

  Read cv of precipitation (percent) and return it, `TRUE`. Defaults to
  `FALSE`. NOTE. Setting this to `TRUE` will always results in `pre`
  being set to `TRUE` and returned as well.

- rd0:

  Read wet-days (number days with \>0.1 millimetres rain per month) and
  return it, `TRUE`. Defaults to `FALSE`.

- tmp:

  Reads temperature (degrees Celsius) and return it,
  TRUE`. Defaults to `FALSE\`.

- dtr:

  Read mean diurnal temperature range (degrees Celsius) and return it,
  `TRUE`. Defaults to `FALSE`.

- reh:

  Read relative humidity and return it, `TRUE`. Defaults to `FALSE`.

- tmn:

  Calculate minimum temperature values (degrees Celsius) and return it,
  `TRUE`. Defaults to `FALSE`.

- tmx:

  Calculate maximum temperature (degrees Celsius) and return it, `TRUE`.
  Defaults to `FALSE`.

- sunp:

  Read sunshine, percent of maximum possible (percent of day length) and
  return it, `TRUE`. Defaults to `FALSE`.

- frs:

  Read ground-frost records (number of days with ground- frost per
  month) and return it, `TRUE`. Defaults to `FALSE`.

- wnd:

  Read 10 m wind speed (metres/second) and return it, `TRUE`. Defaults
  to `FALSE`.

- elv:

  Read elevation (converted to metres) and return it, `TRUE`. Defaults
  to `FALSE`.

- x:

  An optional local file path where CRU CL v.2.0 .dat.gz files are
  located. If this is empty, the requested data will automatically be
  downloaded from the server.

## Value

A
[data.table::data.table](https://rdrr.io/pkg/data.table/man/data.table.html)
object of CRU CL v. 2.0 climatology elements.

## Nomenclature and Units

- pre:

  precipitation (millimetres/month)

- rd0:

  wet-days (number days with \>0.1 millimetres rain per month)

- tmp:

  mean temperature (degrees Celsius)

- dtr:

  mean diurnal temperature range (degrees Celsius)

- reh:

  relative humidity (percent)

- sunp:

  sunshine (percent of maximum possible (percent of day length))

- frs:

  ground-frost (number of days with ground-frost per month)

- wnd:

  10 metre wind speed (metres/second)

- elv:

  elevation (automatically converted to metres from kilometres)

For more information see the description of the data provided by CRU,
<https://crudata.uea.ac.uk/cru/data/hrg/tmc/readme.txt>

## References

New, Mark, et al. "A high-resolution data set of surface climate over
global land areas." Climate research 21.1 (2002): 1-25.
<https://crudata.uea.ac.uk/cru/data/hrg/tmc/new_et_al_10minute_climate_CR.pdf>

## See also

[read_cru_rast](https://docs.ropensci.org/getCRUCLdata/reference/read_cru_rast.md).

## Author

Adam H. Sparks, <adamhsparks@gmail.com>

## Examples

``` r
if (FALSE) { # interactive()
# Create a data frame of temperature from locally available files in the
# tempdir() directory.
library(fs)

f <- path(path_temp(), "grid_10min_tmp.dat.gz")

download.file(
  url = "https://crudata.uea.ac.uk/cru/data/hrg/tmc/grid_10min_tmp.dat.gz",
  destfile = f
)


cru_tmp <- read_cru_dt(tmp = TRUE, x = f)

cru_tmp

# or downloading directly from the CRU server

cru_tmp <- read_cru_dt(tmp = TRUE)

cru_tmp
}
```
