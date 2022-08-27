# American Bond Option

A valuation model is presented for pricing an American style call option on the yield of Treasury bond. The payoff is positive if the yield exceeds a predetermined strike level. The model assumes the yield of an American Treasury bond to be a log-normally distributed stochastic process and uses Monte-Carlo simulation to price the deal as a European call option. Bond price can be computed like https://finpricing.com/lib/FiBond.html

The model builds a trinomial tree for the yield process to price the deal as an American option. The time slices of the tree are evenly spaced. Node transition probabilities and the time interval between slices are determined by matching the first four moments of the underlying Brownian motion. The option is priced using the backward induction.

Since the considered option is analogous to an American call option on a stock without dividends, its pricing as a European call is justified by the arbitrage argument: the value of today’s exercise is S-X, while the present value of the exercise at  maturity is  at least S-Xexp(-rT), which is higher. This approach is also verified by our testing.

Since the term of the option is less than half of year,  which is much less than the term of the underlying bond, it also acceptable to treat the bond’s yield as a lognormally distributed stochastic process with a constant volatility.

The payoff of the option is a discontinuous function of yield, which technically represents the primary security. As a result, the delta is not defined for the intrinsic case, and it is poorly defined for small volatilities. Therefore, the use of delta is not recommended for volatilities less than 5% or for time to maturity less than 10 days.

Since the underlying security (“stock”) is represented by a discrete grid, the payoff function is also distorted and represented by a step–wise line. The option price is roughly determined by the area under both the payoff function and the Gaussian curve. One can see that relative error introduced by the discretization may be the largest for medium variance of the Gaussian distribution.

References:

https://osf.io/dt69v/download
