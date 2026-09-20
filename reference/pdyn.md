# Population dynamics function

Project the population dynamics foward in time.

## Usage

``` r
pdyn(object, ...)

# S4 method for class 'om'
pdyn(
  object,
  stochastic,
  iterations,
  time,
  initial_depletion = 1,
  verbose = FALSE,
  use_rmax = TRUE
)
```

## Arguments

- object:

  an `om` class object

- ...:

  arguments for the generic function definition

- stochastic:

  logical value (no default value)

- iterations:

  number of iterations for stochastic projection

- time:

  number of time steps (can be used to override value stored in
  `object`)

- initial_depletion:

  starting depletion (must be \>0 and \<= 1; defaults to 1.0)

- verbose:

  logical value (defaults to FALSE)

- use_rmax:

  logical value (defaults to TRUE)

## Note

Reference points are always estimated using \\r\_{max}\\, meaning that
projections that use \\r\_{max}\\ have better behavioural properties
when examined relative to reference point values. This is because the
\\\theta\\ shape parameter has been estimated per sample and will
therefore be correctly correlated with the samples from the distribution
of \\r\_{max}\\ values. However, it is also possible to project the
dynamics using \\r\\ by setting `use_rmax = FALSE`. In this case \\r\\
is provided as a separate and independent distribution to the dynamics
equation. This is helpful for robustness testing when it may be assumed
that the population is currently not in it's optimal state, meaning that
\\r \< r\_{max}\\. Note however, that the PST is always calculated using
\\r\_{max}\\, and if \\r\\ is used for the population dynamics, then
this will decouple the assumed \\r\_{max}\\ from the true \\r\\ value.
