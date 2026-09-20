# Plot dynamics from `om` object

Plots the dynamics over time of the projected captures, depletion or
harvest rate.

## Usage

``` r
dynplot(object, ...)

# S3 method for class 'om'
dynplot(object, ..., pars = "depletion", labels)
```

## Arguments

- object:

  `om` class object.

- ...:

  additional `om` class objects

- pars:

  character vector of model parameters to be plotted. Must be one or
  more of `'depletion'`, `'captures'` or `'harvest_rate'`.

- labels:

  character vector of labels per model run

## Value

Returns a `ggplot` object that can be displayed or assigned and
manipulated using further arguments from the ggplot2 package. The
plotted dynamics are summarised as the mean and the 75th and 95th
percentiles across samples from the input life-history distributions and
stochastic iterations (where stochastic projection has been used to
generate the object).

## Note

Multiple model objects can be supplied, in which case they are
over-plotted.

## See also

[`objplot`](https://github.com/protected-species-management/om/reference/objplot.md)
