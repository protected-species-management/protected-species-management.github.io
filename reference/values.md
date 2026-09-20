# Values calculated by the population dynamics function

Extracts values generated internally for projection by
[`pdyn`](https://github.com/protected-species-management/om/reference/pdyn.md).

## Usage

``` r
values(object, ...)

# S4 method for class 'om'
values(object)
```

## Arguments

- object:

  `om` class object

- ...:

  arguments for the generic function definition

## Note

Requires that the `om` object already has values for `stochastic` and
`iterations` stored in `object@settings`.
