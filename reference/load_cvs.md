# Load coefficients of variation

Load coefficients of variation into
[`om`](https://github.com/protected-species-management/om/reference/om-class.md)
class object for stochastic projection and (optionally) reference point
estimation.

## Usage

``` r
load_cvs(object, value, ...)

# S4 method for class 'om,list'
load_cvs(object, value)
```

## Arguments

- object:

  `om` class object

- value:

  named list object containing values for `survivorship`, `birth`,
  `observation`, `mortality`

- ...:

  arguments for the generic function definition
