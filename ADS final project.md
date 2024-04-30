# Explainable Options Pricing Modeling

## Overview
This project implements explainable models focusing on the pricing of financial derivatives, specifically various types of options. The key features of this project include handling American exercise rights, dividends, stochastic volatility, and types of exotic options. 

Before getting into specific details, it's important to understand the basics: 

## What is an Option?
An option is a financial derivative that gives the buyer the right, but not the obligation, to buy (in the case of a call option) or sell (in the case of a put option) an underlying asset at a predetermined price (called the Strike price) on (European option) or anytime before (American option) an expiry date. Options are used for hedging against risks, speculating on future price movements, or enhancing investment income.

## Option class
The `Option` class, which is very simple, encapsulates all the necessary attributes required to price an option:
- **$S_0$ (float)**: Current price of the underlying asset.
- **$K$ (float)**: Strike price of the option.
- **$R$ (float)**: Time to expiration of the option, measured in years.
- **vol $(\sigma)$ (float)**: Volatility of the underlying asset.
- **div (float)**: Dividend yield of the underlying asset, defaulting to 0 if not provided.
- **is_call (bool)**: A boolean indicating if the option is a call (True) or a put (False).
- **barrier (float)**: The barrier level for barrier options, applicable only if the option is a barrier type.
- **option_type (str)**: The type of the option e.g. "European".

## Objectives
- **Enhance Interpretability**: By providing detailed explanations and comparisons of different pricing models, this project aims to make the pricing of options more understandable rather than just using esoteric closed formulas (though we do use these as a benchmark).
- **Expand Core Binomial Model**: Enhance the core binomial model to accommodate real-world complexities such as dividend-paying stocks, American options, and stochastic volatility. This enhancement addresses limitations of the basic model and improves accuracy by reflecting more realistic market conditions. Incorporating dividends ensures that the model accurately captures the impact of cash payouts to shareholders on option prices. Integrating American options capability enables the pricing of options with early exercise features, which is crucial for accurately valuing options in markets with uncertain future volatility. Additionally, incorporating stochastic volatility models allows for better representation of the volatility dynamics observed in real markets, leading to more accurate pricing predictions.
- **Price Complex Exotics**: Develop models capable of pricing complex exotic options. These options often possess intricate payoff structures and features, making them challenging to price accurately. By developing models that can accurately price these exotic options while maintaining interpretability, this project aims to simplify the understanding of complex option pricing and reduce the complexity involved in explaining the details of their pricing mechanisms.

## Methodology
1. **Binomial Model Enhancements**: Implements a binomial model that supports dividends and American options, providing early exercise features which are crucial for accurate option pricing.
2. **Stochastic Volatility Modeling**: Uses the Heston model to simulate paths with stochastic volatility, addressing the limitations of the Black-Scholes model in environments where volatility is not constant.
3. **Barrier and Digital Options**: Incorporates pricing for barrier and digital options using Monte Carlo methods.
4. **Explicit Formulas**: Wherever possible, uses explicit formulas for validation and comparison to ensure the reliability of the simulation-based methods.
5. **Visualizations**: Include visualizations that allow for the visual representation and explanation of the complex options pricing models.