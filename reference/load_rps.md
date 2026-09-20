# Load reference point targets.

Load management targets into
[`om`](https://github.com/protected-species-management/operating-model/om/reference/om-class.md)
class object. These can be the Maximum Net Productivity Level (MNPL) and
corresponding harvest rate and depletion values.

## Usage

``` r
load_rps(object, value, ...)

# S4 method for class 'om,list'
load_rps(object, value)
```

## Arguments

- object:

  `om` class object

- value:

  named list object containing target reference points. List elements
  can be all or one of `captures`, `depletion` and `harvest_rate`.

- ...:

  arguments for the generic function definition

## Details

Targets are assumed to be known without error, and used to measure
outcome of the population projection.

## See also

See
[`rp`](https://github.com/protected-species-management/operating-model/om/reference/rp.md)
for reference point estimation.
