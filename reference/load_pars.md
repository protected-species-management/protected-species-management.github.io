# Load or update parameters

Load or update parameters in
[`om`](https://github.com/protected-species-management/operating-model/om/reference/om-class.md)
class object. Each parameter should be provided as a
[`distribution-class`](https://github.com/protected-species-management/operating-model/om/reference/distribution-class.md).

## Usage

``` r
load_pars(object, value, ...)

# S4 method for class 'om,list'
load_pars(object, value)

update_pars(object, value, ...)

# S4 method for class 'om,list'
update_pars(object, value, ...)
```

## Arguments

- object:

  `om` class object

- value:

  named list object containing parameter distributions.

- ...:

  arguments for the generic function definition
