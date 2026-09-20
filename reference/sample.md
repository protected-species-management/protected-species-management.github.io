# Sample from distribution class object

Overwrites the generic `sample` function to sample from a `distribution`
class object.

## Usage

``` r
sample(x, size, ...)

# S3 method for class 'distribution'
sample(x, size = 1, replace, ...)

# S3 method for class 'numeric'
sample(x, size = 1, replace = FALSE, ...)
```

## Arguments

- x:

  input distribution class object

- size:

  sample size

- ...:

  (ignored)

- replace:

  logical indicating whether values should be sampled with replacement
  (set to `'replace = TRUE'` if `size` is greater than the number of
  values stored in the object). Only used for non-parametric sampling.

## Details

Monte-Carlo samples are generated from a
[`distribution`](https://github.com/protected-species-management/om/reference/distribution-class.md)
class object. If values are stored in the object then these are sampled
non-parameterically (with replacement if necessary). If values are not
present, and `pars` and `density` are specified in the object, then
parametric sampling is performed.

## See also

[`distribution`](https://github.com/protected-species-management/om/reference/distribution-class.md)

## Examples

``` r
# non-parametric
# sampling
x <- distribution(values = 1:3)
sample(x, 3)
#> ! sampling with 'replace = FALSE'
#> [1] 2 1 3

# non-parametric
# sampling
x <- distribution(values = 1:3, density = "uniform")
sample(x, 3)
#> ! sampling with 'replace = FALSE'
#> [1] 3 2 1

# parametric sampling
x[] <- numeric()
sample(x, 3)
#> [1] 2.364358 1.598414 1.880417
```
