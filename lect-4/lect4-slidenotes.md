# Introduction to High Frequency Trading

Pros:
- increase market efficiency: help stabilize ETF market ensuring price of funds stays close to net asset value of holdings.
- increase liquidity
- allows investors to capitalize on opportunities that only exist for short moments.

Cons:
- difficult to regulate
- market manipulation
- small circle of traders benefit.

### Types of markets

Trading exchanges (NYSE, NASDAQ, BATS, DirectEdge)

Dark Pools (lack of transparency, liquidnet, Chi-X, instinet, smartpool,...)

### Limit Order Books. 

All limit orders available to meet incoming market orders at any given time on a trading venue: **Liquidity**

More limit orders + larger size of orders -> more liquid venue.

Majority of Contemporary exchanges are organized as centralized order books (CLOBS)

#### Importance of matching engines

Most execution venues based on FIFO: Some (CME, CBOE, PHLX, ICE) switched to pro rata execution schedules.

#### aggressive versus passive execution

Passive: traders set a price stock must reach before buying/selling (stop order)

Aggressive: traders execute the order immediately. 

## High frequency data

**tick data** -> records of live market activity. 

Limit and market orders placed in "lot sizes" -> increments of certain number of units (lot)

(FX -> standard trading lot around $5mn USD)
(Equity -> lot could be as low as one share: dark pools may enforce 100 share minimum)

Odd lot -> amount other than integer increment of lot size

### Data recording

-> ticks, arrivals of latest quote, trade price, order size, volume info. 

Tick has: timestamp, bid / ask / available bid or ask size / last trade price / last trade sizes

Tick data is dramatically different from low frequency data -> multitude of possible sampling and
interpolation techniques creates diverse angles for exploration. 

Various methods of organizing and interpreting ticks of data deliver diff statistical properties of the
resulting time series. 

### Summary of properties of HFT

|Properties|Description|Pros|Cons|
|----------|-----------|-----|---|
|Voluminous| Each day of HFT data contains num of observations eq to 30 years of daily data | lots of information | Difficult to handle manually|
|Subject to bid ask bounce|Data carries additionaly supply/demand info | bid/ask quotes varry valuable info about market moves|quotes are separated by spreads. Cont movement introduces a jump process|
|Not normally or lognormally distributed | returns from tick are not normal or lognormal|many tradeable models still to be discovered|Trad asset pricing models do not apply|
|Irregularly spaced in time| Arrivals of tick data are asynchronous|Durations between data arrival carry info| most trad models require regularly spaced data; req HF data to be converted into intervals.|
|Do not include buy or sell trade direction info|lvl 1 and 2 data does not include info abt whether the trade was a result of a market buy or sell order|data are leaner, more difficult for bystanders to extract|info on whether a trade is buyer initiated or seller initiated is desired input in many models.|

## Trading costs

Ideally: markets uniform in structure. Markets consolidated (price is updated instantaneously wherever
instrument is traded)

Prices reflect all fundamental info immediately.

No transaction costs. 

orders of all sizes can be executed immediately. 

Traders have unlimited borrowing power

no short sale constraints

market price invariant to order size. 

**In real life:**

friction exists: prices incorporate info over time, markets differ in structure/depth,
markets can be highly fragmented, issues like transaction costs distort markets away from textbook perfect models. 

Transaction costs -> considerable hurdle. 

Transparent (explicit) 
- broker commission
- exchange fees
- taxes

Latent (implicit)
- bid ask spreads
- slippage / latency costs
- price appreciation
- opportunity costs
- market impact costs

## HFT strategies

1. Market making (facilitate orders, exchanges, rebates for quotes)
2. Event arbitrage (movement creating another one)
3. Statistical arrbitrage (exploit predictable temp deviations from stable statistical relationships among securities)
4. New based trading (anticiapted market movement with news)
5. scalping (large volume, small profit)
6. market ignition (spoofing)

### Examples: statistical arbitrage

Equities -> pairs trading / diff equity classes of same issuer / risk arbitrage / liquidity arbitrage

FX -> triangular arbitrage, uncovered interest parity arbitrage

Indices/ETFs -> index comp arbitrage

Options -> volatility curve arbitrage

Cross-asset -> futures / etf arbitrage

## Execution algorithms 

Help traders acuumulate or liquidate large positions by breaking orders into pieces, reducing market impact and visibility of orders. 

Order routing
- min execution cost
- obtain best price
- max execution speed
- max trading size
- min trade footprint

TWAP -> break large order into equally sized parcels, sent out at equally spaced time intervals

VWAP -> breaks large orders such that VWAP child orders are larger when trading volume is higher, and smaller when trading volume is lower. 

## 3 Ps

Performance 
-

Return, volatility, drawdawn,  win ratio (50%), avg gain/loss, correlation, alpha/beta, skewness
(tendency to deliver pos or neg returns: positive skewness -> more likely to post pos returns), 
kurtosis (likelihood of extreme occurrences, pos or neg returns, relative to normal returns). 

sharpe ratio -> expected return - risk free rate over volatility of asset. 

For HFT: sharpe ignores RFR (assumes = 0). 

Treynor ratio: sharpe, but divided by beta (regression coefficient of trading returns on returns of investor's reference portfolio, i.e. market portfolio.

Jensens's alpha: expected - rfr - beta(r_m - rfr) (CAPM pricing model)

Omega: average return in excess of benchmark rate, over LPM of benchmark + 1

Sortino ratio: average return in excess of benchmark rate over the root of LPM of benchmark

Upside potential ratio (HPM of benchmark over root LMP of benchmark)

Kappa 3: excess returns over benchmark over LPM of benchmark to the cube root. 

HPM -> higher partial movement, LPM -> lower partial movement. 

HPM(r) = 1/T \sum (from 1 to T) max [r - benchmark, 0] ^ n

Calmar ratio: Excess returns over risk free rate over negative maximum drawdown. 

Sterling ratio: excess returns over rfr over average maximum drawdown. 

Burke ratio: excess returns over rfr over variance of maximum drawdown (geo average of maximum drawdowns)

Modified sharpe ratio: expected returns over rfr over MvAR. I don't want to type out the equation for MVaR. 

Productivity 
-
Precision
-

### Capacity evaluation

HFT strategies dominated with limit orders: execution for market orders is close to 1, probability 
of limit order execution is not known for certainty. Must become best available price (top of book) and
matched with or crossed by market order or aggressive limit order. 

Prob of execution of limit orders depends on:
- distance of limit order price from market price
- market volatility
- num other limit orders available at same price or closer to market
- size of limit order
- rate of arrival of same side limit orders
- rate of arrival of opposing market orders and aggressive limit orders.

Eval period:

6months to 2years. Some, 6 years. Any backtest period is correct if properly matched with
sharpe ratio intended to verify: higher sharpe, shorter strategy eval period needed to ascertain
validity of 

Alpha decay -> observed due to latency estimated as dist of market impact costs in a fin instrument
in a finite period of time after trading decisions were made. 

## Business of HFT

High cost: technology / technologist, data (at least 2 years of instrument of choice to generate initial trading models)

Conenctivitity, colocation, custody and clearing, admin and legal costs. 

Profitability of strategy w live capital - valuation

cost structure of trading op

sharpe ratio, max drawdown.

"The low transparency of fast and complex algo decisions requires diligent risk management and monitoring processes, and constant human supervision.

### Risks and regulations

Risk: HFT with no control can result in big losses.

Other risk:
- reg and legal
- credit and counterparty
- market
- liquidity
- operational

reg considerations
- jurisdiction
- stability of systems
- investor protection
- efficient trade matching
- market structure

# Hardware/software

Critical path is gateway in -> book builder, and order manager -> gateway out. 

Algo looks at multiple exchanges for updates, then processes thru an algorithm to determine buy/sell.
