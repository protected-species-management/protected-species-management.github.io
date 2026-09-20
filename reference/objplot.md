# Plot performance diagnostics over time

Plots the dynamics over time of the projected captures, depletion or
harvest rate, each summarised as a probability relative to the MNPL
reference points.

## Usage

``` r
objplot(object, ...)

# S3 method for class 'om'
objplot(object, ..., pars = "depletion", labels)
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
percentiles across samples from the input life-history distributions.

## Note

Multiple model objects can be supplied, in which case they are
over-plotted, using the `labels` argument in the legend if supplied.

## See also

[`dynplot`](https://github.com/protected-species-management/om/reference/dynplot.md)
