# Load maximum intrinsic growth parameter

Load \\r\_{max}\\ into the `pars` slot of an
[`om`](https://github.com/protected-species-management/om/reference/om-class.md)
class object.

## Usage

``` r
load_rmax(object, value, ...)

# S4 method for class 'om,distribution'
load_rmax(object, value)

# S4 method for class 'om,missing'
load_rmax(object, value)
```

## Arguments

- object:

  `om` class object.

- value:

  `distribution` class object. If no value is provided, the distribution
  is obtained directly from the life-history parameters stored in the
  object.

- ...:

  arguments for the generic function definition.

## Details

The intrinsic growth rate is assumed to have normal distribution. It is
converted to a zero-truncated normal on assignment because the maximum
growth rate is always assumed to be greater than zero (i.e., \\r\_{max}
\> 0\\).
