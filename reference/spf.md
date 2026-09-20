# Surplus production function

Extracts data frame containing relationships between the depletion,
sustainable captures and the harvest rate. Depletion is measured using
the 1+ age classes.

## Usage

``` r
spf(object, harvest_rate, ...)

# S4 method for class 'om,numeric'
spf(object, harvest_rate, stochastic, time, iterations, verbose = FALSE)
```

## Arguments

- object:

  `om` class object

- harvest_rate:

  numeric vector of harvest rates over which surplus production should
  be calculated

- ...:

  arguments for the generic function definition

- stochastic:

  logical value indicating whether stochastic production function should
  be calculated (defaults to value in `settings$ref_points`)

- time:

  equilibrium time horizon over which values are calculated (defaults to
  value in `settings$ref_points`)

- iterations:

  numeric value indicating number of iterations for when
  `stochastic = TRUE` (defaults to value in `settings$ref_points`)

- verbose:

  logical value indicating whether values `stochastic`, `time` or
  `iterations` should be printed

## Value

A data frame containing depletion, sustainable captures and the harvest
rate, for each of the input harvest rate values.

## Details

This function is designed to facilitate the easy creation of plots of
the production function, that can be used to validate operating model
assumptions regarding the depletion and harvest rate at MNPL. The
production function is calculated assuming either deterministic or
stochastic reference point calculations, depending on the arguments
provided or settings stored in `object@settings$ref_points`. If
life-history inputs are uncertain, these input distributions are sampled
to represent uncertainty in the operating model conditioning.
