# Access slots within an `om` object.

Access information stored in
[`om`](https://github.com/protected-species-management/operating-model/om/reference/om-class.md)
object. The same information can be accessed in raw format using
`object@<function>`.

## Usage

``` r
targets(object, ...)

# S4 method for class 'om'
targets(object)

# S4 method for class 'om'
diagnostics(object)

# S4 method for class 'om'
pst(object)

# S4 method for class 'om'
objectives(object)

# S4 method for class 'om'
pars(object)

# S4 method for class 'om'
settings(object)

# S4 method for class 'om'
numbers(object)
```

## Arguments

- object:

  [`om`](https://github.com/protected-species-management/operating-model/om/reference/om-class.md)
  class object.

- ...:

  arguments for the generic function definition

## Examples

``` r

# error messages are
# generated when applied
# to an empty object
om_object <- om(ages = 0:1, time = 1, samples = 3)

targets(om_object)
#> ✖ '<object>@targets' is empty - run 'shape()' and 'rp()'
objectives(om_object)
#> ✖ '<object>@objectives' is empty - run 'pdyn()'
diagnostics(om_object)
#> ✖ '<object>@diagnostics' is empty - run 'pdyn()'
pst(om_object)
#> ✖ '<object>@pst' is empty - run 'pdyn()'

# an empty object has
# the following settings
# by default
settings(om_object)
#> $ref_points
#>   stochastic iterations time
#> 1      FALSE         NA 1000
#> 
#> $projection
#>   stochastic iterations time
#> 1      FALSE         NA    1
#> 
#> $cv
#>   survivorship birth numbers harvest_rate capture rmax
#> 1            0     0       0            0       0    0
#> 
#> $qn
#>   numbers
#> 1       0
#> 2      NA
#> 
#> $bias
#>   numbers harvest_rate capture rmax
#> 1       1            1       1    1
#> 

# when slots have values
# they can be retrieved
targets(om_hdo)
#> $captures
#> # A tibble: 1 × 2
#>   sample  value
#>    <int>  <dbl>
#> 1      1 0.0153
#> 
#> $harvest_rate
#> # A tibble: 1 × 2
#>   sample  value
#>    <int>  <dbl>
#> 1      1 0.0410
#> 
#> $depletion
#> # A tibble: 1 × 2
#>   sample value
#>    <int> <dbl>
#> 1      1 0.600
#> 
pars(om_hdo)
#> $r
#> distribution object class
#> density: normal
#> pars: 0.04, 0.017
#> values: EMPTY
#> name: intrinsic growth rate
#>  
#> 
#> $rmax
#> distribution object class
#> density: zt-normal
#> pars: 0.04, 0.017
#> values: EMPTY
#> name: max. intrinsic growth rate
#>  
#> 
#> $s
#> distribution object class
#> density: logitnormal
#> pars: 2.962, 0.2
#> values: EMPTY
#> name: adult survivorship
#>  
#> 
#> $l
#> distribution object class
#> density: unspecified
#> pars: NA, NA
#> values: 0.9
#> name: age zero survivorship multiplier
#>  
#> 
#> $b
#> distribution object class
#> density: beta
#> pars: 9.61, 13.86
#> values: EMPTY
#> name: female fecundity
#>  
#> 
#> $m
#> distribution object class
#> density: int-uniform
#> pars: 6, 8
#> values: EMPTY
#> name: age at maturity
#>  
#> 
#> $o
#> distribution object class
#> density: int-uniform
#> pars: 6, 8
#> values: EMPTY
#> name: age at observation
#>  
#> 
#> $v
#> distribution object class
#> density: int-uniform
#> pars: 6, 8
#> values: EMPTY
#> name: age at selectivity
#>  
#> 
#> $K
#> distribution object class
#> density: unspecified
#> pars: NA, NA
#> values: 1
#> name: K1+
#>  
#> 

# some slots are empty
# until a projection 
# has been performed
pst(om_hdo)
#> ✖ '<object>@pst' is empty - run 'pdyn()'
pst(pdyn(om_hdo))
#> ⠙ Projecting dynamics
#> ⠹ Projecting dynamics ...
#> ✔ Projected dynamics [97ms]
#> 
#> # A tibble: 301 × 4
#>    sample iteration  time  value
#>    <chr>      <int> <int>  <dbl>
#>  1 1              1     0 0.0143
#>  2 1              1     1 0.0137
#>  3 1              1     2 0.0132
#>  4 1              1     3 0.0127
#>  5 1              1     4 0.0123
#>  6 1              1     5 0.0119
#>  7 1              1     6 0.0115
#>  8 1              1     7 0.0112
#>  9 1              1     8 0.0110
#> 10 1              1     9 0.0107
#> # ℹ 291 more rows
diagnostics(om_hdo)
#> ✖ '<object>@diagnostics' is empty - run 'pdyn()'
diagnostics(pdyn(om_hdo))
#> ⠙ Projecting dynamics
#> ✔ Projected dynamics [29ms]
#> 
#> $captures
#> # A tibble: 300 × 4
#>    sample iteration  time  value
#>    <chr>      <int> <int>  <dbl>
#>  1 1              1     0 0.0297
#>  2 1              1     1 0.0286
#>  3 1              1     2 0.0276
#>  4 1              1     3 0.0266
#>  5 1              1     4 0.0258
#>  6 1              1     5 0.0251
#>  7 1              1     6 0.0244
#>  8 1              1     7 0.0238
#>  9 1              1     8 0.0233
#> 10 1              1     9 0.0228
#> # ℹ 290 more rows
#> 
#> $depletion
#> # A tibble: 301 × 4
#>    sample iteration  time value
#>    <chr>      <int> <int> <dbl>
#>  1 1              1     0 1    
#>  2 1              1     1 0.972
#>  3 1              1     2 0.948
#>  4 1              1     3 0.926
#>  5 1              1     4 0.907
#>  6 1              1     5 0.890
#>  7 1              1     6 0.874
#>  8 1              1     7 0.859
#>  9 1              1     8 0.845
#> 10 1              1     9 0.833
#> # ℹ 291 more rows
#> 
#> $harvest_rate
#> # A tibble: 300 × 4
#>    sample iteration  time  value
#>    <chr>      <int> <int>  <dbl>
#>  1 1              1     0 0.0410
#>  2 1              1     1 0.0410
#>  3 1              1     2 0.0410
#>  4 1              1     3 0.0410
#>  5 1              1     4 0.0410
#>  6 1              1     5 0.0410
#>  7 1              1     6 0.0410
#>  8 1              1     7 0.0410
#>  9 1              1     8 0.0410
#> 10 1              1     9 0.0410
#> # ℹ 290 more rows
#> 
```
