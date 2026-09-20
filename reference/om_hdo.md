# Hector's dolphin

An
[`om`](https://github.com/protected-species-management/operating-model/om/reference/om-class.md)
class object containing life-history data and reference points for
Hector's dolphin assuming that the depletion at Maximum Net Productivity
Level is \\D\_{MNPL} = 0.6\\.

## Usage

``` r
om_hdo
```

## Format

See
[`om`](https://github.com/protected-species-management/operating-model/om/reference/om-class.md),
[`pars`](https://github.com/protected-species-management/operating-model/om/reference/targets.md),
[`distribution`](https://github.com/protected-species-management/operating-model/om/reference/distribution-class.md)

## Author

J.O. Roberts and C.T.T. Edwards

## Examples

``` r
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
```
