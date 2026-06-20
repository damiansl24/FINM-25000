# FINM 25000: LECTURE SLIDE NOTES

## Session 1: Introduction to Trading System and Trading Strategy

### Money Exchange

There are always players who need capital, and those who have the funds saved to supply that capital.

Some examples of this exchange of money are:

1. **Debt Capital**

Debt capital is comprised of loans lenders make to borrowers. The borrowers are expected to pay back interest plus principal on the loan.

One example are bonds. Bondholders are creditors of the issuer.

2. **Equity Capital**

Equity capital is unique to corporations. To raise capital, they issue shares of their company (stock, equity) representing ownership interest in the underlying business. 

Investors are entitled to a portion of the profits.

-----

### Markets

Primary Market -> cover sales of securities by issuers to investors (IPO)
- New stock issuance: corporation first sells its stocks and bonds. Issuer receives proceeds from the sale

Secondary Market -> trading markets, trading existing financial instruments, reselling stock/bonds.
- there are two categories: physical trading floors (NYSE), or electronic marketplace (NASDAQ)
- Exchanges (auction market with competing buyers / sellers)
- OTC (negotiated market)

Tertiary Market -> trading in listed securities away from the exchange where they are listed (institutional market)

Quaternary Market -> trades directly between buyers and sellers. 

-----

### Prices and Quotes

**BID** is the highest price a buyer is WTP. Sellers get the bid price. 

**ASK** is the offering price and the lowest price a seller is WTS. Buyers pay the ask price. 

The difference is the bid ask **spread**, quoted in dollars and cents. Actively traded stocks have narrower spreads.

On a chart, the ask is always higher than the bid (individuals always want to buy low and sell high: ask -> sell, bid -> buy). 

#### Positions

Long stock position is bullish, anticipates growth -> buying a security, expecting it to appreciate in the future. 

Short stock position is bearish, anticipate decline -> sale of a borrowed security, expecting value to fall.

-----

### Important measurements:

**Total Stock Return**: \[(P1 - P0) + D\] / P0
- D: divident, P0: initial price, P1: ending price

**P&L, PNL**: Money invested * total stock return

Volatility: Standard deviation of returns

Volume: how much of security is being traded

Alpha: returns in excess of the market

Beta: sensitivity to the market.

----

### Hedging :

Reduce exposure to various risks: insurance to reduce impact of events. 
- Invest in two securities with negative correlation.

----

### Settlement Date:

Date upon which transaction must be cleared: when buyer pays and seller delivers securities. 
- most: regular way settlement. Corp sec 3 biz days, treasuries / otpions next biz day, cash same day.
- Alternatively: Seller's option contract: right to deliver sec in another time period.

-----

### Order Types

**Market orders** do not specify prices: execute at whatever price is available when it reaches the floor. 

**Limit Order** is a wish to buy or sell at a specific price: executed at a specified price or better.
- Buy limit -> below mkt price
- Sell limit -> above mkt price, may not be executed if there is stock ahead (higher priority order and same price)

**Stop order** becomes a market order once a specified price is reached/passed (stop price).
- sell: below mkt price, limit loss / protect profit on long
- buy: above mkt price, limit loss / protect profit on short

**Stop Limit Order** is when the stop price activates the order, but becomes a limit order and is only executed at a specific price or better: the order may not get filled. 
- sell: below mkt price. Limit loss / protect profit on long
- buy: above mkt price. Limit loss / protect profit on short.

All orders adjusted for stock splits and dividends: only orders entered below the market are adjusted for cash dividends.
- sudden artificial price changes do not change the charts (a stock split will make it seem as if the stock price cut in half suddenly)

Stock prices decrease when dividends are distributed
- stocks = claim on assets in a company. When dividends are distributed, cash decreases (dispersed to shareholders). Thus, you (who own the shares) get cash, equivalent to what is distributed while your stock (claim on residual assets, including the remaining cash) depreciates slightly.

Accounting sequence
1. Declaration date: company BoD announces they will pay a dividend (amount per share, record date, and payment date). Create a legal liability, Dividends Payable
2. Night before the drop: Stock closes at $100 PM on Tuesday, and company is paying a $2 dividend on wednesday (ex dividend date, day of the drop). After hours trading (trade normally. Assume it finishes after hours at $100). Midnight reset (overnight, stock exchanges alter previous close from $100 to $98). Baseline reference price pre market trading is $98: if first trade is flat, stock opens at $98.
3. Ex dividend date: If you buy today, you pay lower price but do not get cash. If you owned stock before today and sell today, you get cash and you keep whatever you sell the stock for.
4. Record date: when company looks at list of shareholders, see who legally owned stock.
5. Payment date: Could be after record date, when the company sends dividends out.

Orders below market are adjusted for cash dividends (i.e. stop loss isn't automatically triggered). 

**Day order**Cancel at EOD if not executed

**Good Till Cancelled (GTC) or open order** remain in effect until executed or cancelled

**At opening** Order at opening price

**At close** order at closing price

**Not held** gives floor broker discretion about time/price on order

**immediate or cancel (IOC)** as much of the order executed immediately: portion not executed immediately is cancelled. 

Adjustments based on splits / dividends are adjustments on market orders. When a stock splits, divide original order price by the split, and multiply the number of stocks requested in order by the split. 

----

## Trading Instruments

### Stocks

Largest market. Information includes Dividends, Splits, News, and Corporate reports / earnings.

Preferred and Common stocks

#### Common
- authorized shares (allowed number of shares)
- Issued shares (amount of stock sold)
- Treasury stock (shares issued, and owned by company)
- outstanding stock (number of shares issued to the public)
- Issued stock - treasury stock = outstanding shock.

These shares include, right of vote / right to receive dividends / right of inspection / right of transfer. 

#### Preferred stocks 
- Behaves more like debt
- Fixed, predictable dividends (fixed as a percentage of par value)
- Preference in dividends and liquidation: If company runs into financial trouble, preferred shareholders stand ahead of common shareholders in line for money. Company must pay preferred before common: but preferred shareholders are lower in prioroity than bondholders and creditors.
- No voting rights (usually)
- Limited capital appreciation: market price behaves like a bond, narrow range and sensitive to interest rate changes rather than company growth.

- If company misses a preferred dividend payment, it accumulates as an "arrearage." Company must pay back all missed preferred dividends from past before they pay common shareholders.
- Company can buy stock back at a set price after a certain date: Companies can call preferred stock to reissue new ones.
- Convertible: you can swap preferred shares for a specific number of common shares.

#### Types of stock
- Blue chip - high grade / major companies / stable track record of earnings/dividends.
- Growth stocks - fast growing new companies, no or small dividends
- Defensive stocks - recession resistant
- Income stocks - Dividends stock
- Cyclical stocks - earningsfluctuate with business cylce
- Seasonal stocsk - earnings fluctuate with time of year
- American Depositay Receipts (ADRs). 

### Bonds

Investor lends money to issuer, who promises to pay back at maturity + interest on loan (coupon).

bond returns
- Nominal yield (stated rate of interest)
- Current yield (annual interest pmt / current market price) -> does not consider price appreciation on discount bound / vice versa.
- YTM (total overall return: called yield or basis).
- Yield to call (cash flow through first call date)

Par bonds: nom = curr = YTM

Discount bonds: nom < curr < YTM

Premium bonds: nominal > curr > YTM.

Real interest rate = nom rate - inflation rate

### Options

Buyer: holder of option, pays for right to exercise contract: long

Seller: writer, gets money, fulfills obligation. Short option. 

Types:
- call: right to buy security at a fixed price
- put: right to sell security at a fixed price.

Difference with warrants: warrants issued by company

Difference with futures: Futures force buyer to purchase asset (and vice versa)

#### Components
- underlying security
- Expiration month
- Exercise (strike) price
- type of option
- Premium (buyer pays to seller: influenced by relationship b/w curr mkt price of stock and strike price, time remaining til expiration, volatility, dividends paid on underlying stock, rate of return available on other instruments)

Option premium = intrinsic value + time value. 

"in the money" - market price > strike price

"at the money" - Market price = strike price

"out the money" - market price < strike price

#### Option events
- position needs to be closed
- **Liquidate** can sell contract on secondary mkt
- **exercise** seller would be assigned the exercise, has to fulfill obligation
- **Expiration** can be worthless if it's out the money.

#### Option strategies

**Buying calls**
- breakeven when p of stock = strike price + premium. Profit is above
- max gain unlimited
- max loss is premium paid

**Selling calls**:
- max gain is premium
- breakeven is strik price + premium
- If call write uncovered: unlimited potential loss
- Breakeven is same for buyer and seller.

**Buying puts**
- breakeven when price of stock = strike price - premium
- max gain (strike - premium) * 100 shares
- max loss is premium paid

**Selling puts**
- premium is max gain
- max potential loss: exercise price - premium for selling
- breakeven if price declines by amount = to premium.

#### basic hedging strategies
- long stock short call (covered call writing), breakeven is stock price - income from option premium. limits max gain on stock position.
- Long stock long put (protective put): long put is insurance against decline in stock. Protect gain on long position
- Short stock long call (protective call). Insurance against increase in short stock position. Loss limited to cost to exercise call - net short sale proceeds
- Short stock and short put (covered put writing). Investors increase return on portfolios, hedge short position against rising prices. Breakeven is short sale price + premium, max loss unlimited.

#### Multiple option Strategies

**Straddles**
- buy call and put, or sell call and put with same underlying security, exercise price, and date. Buying is long, writing is short. Speculate volatility of stock.
- Long straddles: profit if it goes up / down. Breakeven: strike price +/- total premium. Max gain: unlimited. Max loss: total premium paid.
- Short straddles: neither bullish nor bearish. Expects little fluctuation in market. breakeven same. max gain: profit, as long as market stays between breakeven points. Max loss: unlimited.

### Other trading instruments

Commodities

ETF

Forex

Index

Mutual funds.

-----
## Exchange and Trading System

