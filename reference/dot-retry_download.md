# Use httr2 to fetch a file with retries

Downloads a file with retry logic and optional progress display. The
downloaded file is written to `dest`.

## Usage

``` r
.retry_download(url, dest, .max_tries = 3L)
```

## Arguments

- url:

  Character. The full URL to download.

- dest:

  Character. File path where the downloaded file will be written.

- .max_tries:

  Integer. Number of retry attempts.

## Value

Invisibly returns `dest` for convenience.
