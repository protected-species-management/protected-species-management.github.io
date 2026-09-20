# Stochastic reference point calculation

Calculate the Maximum Net Productivity reference points.

## Usage

``` r
rp(object, ...)

# S4 method for class 'om'
rp(object, stochastic, time, iterations, verbose = FALSE)
```

## Arguments

- object:

  `om` class object

- ...:

  arguments for the generic function definition

- stochastic:

  logical value indicating whether stochastic production function should
  be calculated (defaults to value in `object@settings$ref_points`)

- time:

  equilibrium time horizon over which values are calculated (defaults to
  value in `settings$ref_points`)

- iterations:

  numeric value indicating number of iterations for when
  `stochastic = TRUE` (defaults to value in
  `object@settings$ref_points`)

- verbose:

  logical value indicating whether values `stochastic`, `time` or
  `iterations` should be printed

## Note

This function would typically be preceded by a call to
[`shape`](https://github.com/protected-species-management/operating-model/om/reference/shape.md),
which estimates the shape parameter necessary for definition of the
production function.

## See also

[`shape`](https://github.com/protected-species-management/operating-model/om/reference/shape.md)
[`targets`](https://github.com/protected-species-management/operating-model/om/reference/targets.md)
