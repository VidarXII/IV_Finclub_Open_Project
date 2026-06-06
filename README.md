# IV_Finclub_Open_Project

Implied volatility is the pricing language of the options market. Incorrect fair-value estimates for
implied volatility can materially affect option pricing, risk management, hedging decisions, and
trading strategies. The challenge is to build a model that can accurately predict missing values
in an implied volatility surface using the available option data across strikes and timestamps.

In doing this project, I tested robust cleaning+clamp, cubic splines, cubic causal 2d kernels, var pchip for clean cells, temporal functions, convex regression, isotonic call wings, linear wing extrapolation, linear map everywhere, linear map + linear map extrapolation for wings, linear map only for atm and flexible boundaries. After all these, with all the ups and downs in my mse score, this is what remains. Parametric SVI //SSVI/SABR did not work, power law, lightgbm, xgboost were all useless. Most of the outliers were all on the expiry day, and hence we needed to separate the way we treated this day from how we treated other normal days. On the expiry day, the smile changed from a U towards the start to a sharp v at the end. There was also a consistent notch at ATM. With all these tried and tested validation methods, this is what remains.
