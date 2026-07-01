# Module 2: Introduction to Trading System and Trading Strategy

## Technical Analysis

Simple Moving Average (SMA)

Average price of a stock over a rolling window. 

Sum of prices from time period i - 1 to time period N, divided by number of prices added together or number of time periods. 

Exponential Moving Average
- places more weight on the most recent price observation. 

EMA = P * mu + (1 - mu) * EMA{old}
P = current price of investment
EMA{old} = EMA value prior to the current price observation
mu = smoothing constant: most commonly 2/(n+1)
N number of time periods (similar to SMA)

**Absolute Price Oscillator**

Finding difference between a fast exponential moving average and a slow exponential moving average. 

Measure how far the more reactive EMA is deviating from the more stable EMA; large difference means either instrument prices are starting to trend or break out, or instrument prices are far away from their equilibrium prices (overbought / oversold)

Moving average convergence divergence 

Smoothing exponential moving average to the MACD value to get final signal output from MACD indicator; may have to look at difference between MACD values and EMA of the MACD values, visualizing as a histograme. Similar to absolute price oscillator

MACD smooths out security's recent price movements, and compares it to medium term trend line to another trend line showing its more recent price changes. 

## Resistance and Support

When price breaks out of a trading range, can signal potential for a new trend in price. 

Bollinger bands
- computes moving average of prices (can use SMA / EMA). 
- also computes deviation of prices in lookback period, treating MA as mean price.
- Creates upper band (MA + multiple of std price deviations) -> expected price volatility, treat MA as reference. 
- Creates lower band (MA - multiple of std price deviations)

When prices move outside these bands, can be interpreted as a breakout / trend signal or an overbought / sold mean reversion signal. 

The bands help quantify and capture the time when breakouts happen. 

Relative strength indicator (RSI)

based on price changes over periods to capture strength / magnitude of price moves. 

- look back period (compute magnitude of avg gains / price increases, and magnitude of average losses / price decreases)

RSI value normalizes signal to stay between 0 and 100. Attempts to capture if there have been many more gains to losses, or losses to gains. 

RSI > 50% -> uptrend and vv. 

For the last n periods, the following applies:

Price > Prev Price => AbsoluteLossOverPeriod = 0.

Else, 

AbsoluteLossOverPeriod = previousPrice - Price

Price < Previous Price => absolute gain over period = 0

Else,

Absolute gain over period = price - previous price

RS = sum (gains over last n periods) / sum (losses over last n periods) -> take magnitudes.

RSI = 100 - 100 / (1 + RS)

stdev -> price volatility.

Momentum (MOM) -> speed and magnitude of price moves. Difference between curr price and price of some fixed time periods in the past. POS momentum continuously implies uptrend; conversely downtrend. 

Seasonality

Data points in time series are time dependent; financial products follow trends and seasonality during different seasons. 
1. find a pattern
2. Stationarity y/n
3. Dickey Fuller test - study p value
4. last step:

forecast time series. 

Strictly stationary series w/o dependencies among values -> regular linear regression

Series w/ dependencies among values -> other statistical models

Aut regression integrated moving averages (ARIMA) model
1. autoregressive (AR) term (p): lags of dependent variables. 
2. Moving average (MA) term q: lags for errors in prediction. 
3. Differentiation (d): d number of occasions where we apply differentiation between values. If d = 1, proceed with diff between two consecutive values. 

## Trading strategies driven by humans

Reminder: momentum strategies

Moving average crossover: Detect when price moves from one side of a moving average to the other (curr price intersects moving average, there is change in momentum). 

Dual moving average crossover (short versus long term). Momentum shifts in direction of ST MA -> when STMA crosses LTMA and value of STMA > LTMA, positive momentim. 

Turtle trading: having a number of specific days, either high or low. 

Pair correlation strategy
- creating trading strategies operating on linearly correlated groups of trading instruments. 

Correlation -> move in same direction

Cointegration -> spread is stable over time. 

## Adapting to market participants and conditions

Impact of backtester dislocations
- signal validation

Ensure that the timeline / synchronization of historical data playback software aligns and are accurate; else signal predictions and performance are not realized in live trading.

- Strategy validation

Needs a backtester that can simulate the behavior and performance of a trading strategy over historical data as if it were trading in live markets, performing matching like an exchange would. 

- Risk estiamtes

Build a backtester that can simulate the behavior / performance of a trading strategy over historical data as if it were trading in live markets, by performing matching.

Causes of simulation dislocations
- slippage

Expected price != actual trade prices in live trading. 

Could be due to historical market data playback issues, underlying assumptions about latencies within trading strategy / between strat and exchange. 

- fees

Important to understand and accoutn for fees in strategy analysis, especially for shares / future contract / options contracts. 

- operational issues

Execute the strategy in live markets as close to simulation conditions as possible. Realize the performance observed in backtesting / sims in a live market.

Manual interruption may be necessary, but could be bad if they are shut down too early. 

Causes of simulation dislocations
- market data issues
- latency variance
- place in line estiamtes (matching algorithms)
- market impact

Response to live trading
- historical data accuracy
- measuring and modeling latencies
- adjusting expected performance for backtester bias
- analytics on live trading strategies (contd)

Post trade analytics (PTA) -> dig through strategy action records, classify winning / losing positions and statistics on strategy actions leading to those positions. Can be used to guide development and improvement of the strategy. 

Profit decay in algo trading
- lack of optimization
- absence of leading participants
- signal discovery by other participants
- profit decay due to exit of losing participants
- profit decay due to changes in underlying assumptions / relationships
- seasonality

To do list:
1. building trading signals dictionary / database
2. optimizing trading signals
3. Optimizing prediction models (strat params, new signals, expand to new strat)
4. portfolio optimization (uniform risk allocation, PnL based risk, PnL sharpe based risk, markowitz, regime predictive allocation)