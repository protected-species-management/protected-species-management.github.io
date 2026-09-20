# Calculate shape

Calculates shape parameter given assumed depletion at MNPL.

## Usage

``` r
shape(object, depletion, ...)

# S4 method for class 'om,numeric'
shape(
  object,
  depletion,
  stochastic,
  time,
  iterations,
  verbose = FALSE,
  safe = TRUE
)

# S4 method for class 'om,ANY'
shape(object, depletion, ...)

shape(object, ...) <- value

# S4 method for class 'om,numeric'
shape(object) <- value
```

## Arguments

- object:

  `om` class object

- depletion:

  Assumed depletion of breeding-age individuals at MNPL

- ...:

  arguments for the generic function definition

- stochastic:

  logical value indicating whether stochastic production function should
  be calculated (defaults to value in `object@settings$ref_points`)

- time:

  equilibrium time horizon over which values are calculated (defaults to
  value in `object@settings$ref_points`)

- iterations:

  numeric value indicating number of iterations for when
  `stochastic = TRUE` (defaults to value in `settings$ref_points`)

- verbose:

  logical value indicating whether values `stochastic`, `time` or
  `iterations` should be printed

- safe:

  logical value indicating whether RTMB model should be recompiled with
  each sample (resulting in a more stable estimation)

- value:

  numeric value or vector of length equal to `object@samples`

## See also

[`rp`](https://github.com/protected-species-management/operating-model/om/reference/rp.md)
