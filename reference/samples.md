# Specify number of samples

Specify the number of samples with which to represent uncertainty in the
input parameters.

## Usage

``` r
samples(object, ...)

# S4 method for class 'om'
samples(object)

samples(object, ...) <- value

# S4 method for class 'om,numeric'
samples(object) <- value
```

## Arguments

- object:

  `om` class object

- ...:

  arguments for the generic function definition

- value:

  numeric value with which to update `object@samples`
