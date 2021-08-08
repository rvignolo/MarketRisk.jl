**MarketRisk.jl** is a Julia library wich provides high performance differentiable market risk measures for your portfolio. The library currently supports:

-  [Value at Risk (VaR)](https://en.wikipedia.org/wiki/Value_at_risk): Most popular market risk measure which gives maximum possible loss given a confidence level and a time horizon.
- [Expected Tail Loss (ETL or CVaR)](https://en.wikipedia.org/wiki/Expected_shortfall): A more complete risk measure than VaR.


# Examples

**VaR:**

```Julia 
using MarketRisk

μ = 0.1
Σ = 0.2
ν = 4.13
N = Normal()

var = ValueAtRisk(μ, Σ, N)

compute(var, 10, 0.1)
```

**ETL:**

```Julia 
using MarketRisk

μ = 0.0
Σ = 0.3 ^ 2

ν = 4.13

h = 10 / 250
α = 0.01

T = TDist(ν)

t_etl = ExpectedTailLoss(μ, Σ, T)

compute(t_etl, h, α)
```

# Installation
# Authors
# License

