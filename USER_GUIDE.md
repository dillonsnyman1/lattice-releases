# Lattice Terminal - User Guide

---

## Table of Contents

1. [Getting Started](#getting-started)
2. [The Command Line](#the-command-line)
3. [Watchlist](#watchlist)
4. [Quotes and Charts](#quotes-and-charts)
5. [Company Profile](#company-profile)
6. [Financial Statements](#financial-statements)
7. [Estimates and Earnings](#estimates-and-earnings)
8. [SEC Filings](#sec-filings)
9. [Options Analytics](#options-analytics)
10. [Portfolio](#portfolio)
11. [Bond Analytics](#bond-analytics)
12. [FX Rates](#fx-rates)
13. [Commodities](#commodities)
14. [Equity Screener](#equity-screener)
15. [Macro and Rates](#macro-and-rates)
16. [Geographic Intelligence Map](#geographic-intelligence-map)
17. [OANDA FX Trading](#oanda-fx-trading)
18. [AI Assistant](#ai-assistant)
19. [Backtesting](#backtesting)
20. [Alerts](#alerts)
21. [Workspace](#workspace)
22. [Configuration](#configuration)
23. [Keyboard Reference](#keyboard-reference)

---

## Getting Started

Lattice is a keyboard-first financial terminal. The fastest way to navigate is to type a symbol or function code into the command line at the top of the screen and press Enter.

To load a security, type its ticker:

```
AAPL
MSFT
SPY
BTC-USD
^GSPC
```

To jump directly to a function for that security, combine them:

```
AAPL DES        (company profile for Apple)
MSFT FA         (financial statements for Microsoft)
SPY OPT         (options chain for SPY)
```

You can also type a function code alone for panels that don't require a symbol:

```
MACRO           (Treasury yield curve)
ECAL            (earnings calendar)
SCRN            (equity screener)
PORT            (portfolio)
BMAP            (geographic intelligence map)
```

---

## The Command Line

The command line at the top of the screen accepts both tickers and function codes. Press Enter to execute, Escape to clear, and use the Up/Down arrow keys to cycle through recent commands.

**Syntax**

```
[TICKER] [QUALIFIER] [FUNCTION]
```

Qualifiers like `US`, `EQUITY`, `CORP` are stripped automatically, so `AAPL US EQUITY DES` works the same as `AAPL DES`.

**Function codes**

| Code | What it does |
|---|---|
| `QR` / `GP` | Quote and price chart |
| `DES` | Company description and profile |
| `FA` | Financial statements |
| `EE` / `ERN` | Estimates and earnings |
| `OPT` / `OMON` | Options chain |
| `VOLS` / `OVDV` | Implied volatility surface |
| `FILINGS` / `CF` / `EDGAR` | SEC filings |
| `NI` / `N` | News |
| `MACRO` / `YC` | Treasury yield curve and macro |
| `ECAL` / `EARN` | Earnings calendar |
| `SCRN` / `SCREEN` / `EQS` | Equity screener |
| `PORT` / `PRTU` | Portfolio |
| `BOND` / `YAS` / `FI` | Bond price/yield calculator and curve overlay |
| `FX` / `FXGO` | FX rates, cross-rate matrix, and CIP forward calculator |
| `CMDTY` / `COMM` | Commodity spot prices, forward curves, and spread analytics |
| `TRADE` / `OANDA` / `ACCT` | OANDA FX trading |
| `CHAT` / `AI` / `NLP` | AI assistant |
| `BT` / `BACKTEST` | Strategy backtester |
| `API` / `LAPI` | Local REST API |
| `BMAP` / `GMAP` | Geographic intelligence globe |
| `HELP` | Function directory |
| `CFG` | Settings |

Type `HELP` to see the full function directory with descriptions.

---

## Watchlist

The watchlist runs down the left side. Click any symbol to load it, or type the ticker into the command line.

**Adding symbols**

Type a ticker into the search box at the top of the watchlist and press Enter or click the result.

**Reordering**

Drag symbols up or down to reorder them. The order is saved automatically.

**Group by type**

Toggle the group button at the top of the watchlist to group symbols by asset class (stocks, ETFs, indices, FX, crypto, futures). Each group has a sticky subheading.

**Asset type badges**

Each symbol shows a small badge: `STK`, `ETF`, `IDX`, `FX`, `CRYP`, `FUND`, or `FUT`.

**Removing symbols**

Hover over a symbol and click the X that appears on the right.

---

## Quotes and Charts

**Loading a quote**

Type a ticker and press Enter, or type `AAPL QR`. The quote panel shows:

- Last price, change, and change %
- Bid and ask
- Day high and low
- Volume and average volume
- 52-week high and low
- Market cap
- Market state (open, closed, pre-market, post-market)
- Data source and timestamp

**Price chart**

Type `GP` or `AAPL GP` to load the chart. Use the interval buttons across the top to switch between intraday and daily/weekly/monthly bars. Use the range buttons to zoom from 1 day to max history.

The chart supports candlesticks with volume bars, a crosshair with OHLCV tooltip, and scroll/pinch-to-zoom.

**Data sources**

If a Polygon.io API key is configured, quotes and charts use Polygon for real-time or delayed data. Without a key the app falls back to Yahoo Finance. The source and timestamp appear at the bottom of every panel.

---

## Company Profile

Type `DES` with a symbol loaded to open the company profile. It has three sub-tabs.

**PROFILE**

- Company logo, name, and exchange
- Sector, industry, and SIC code
- Full business description
- Employee count and homepage

**MGMT**

- Key executives with name, title, age, and total compensation

**HOLDERS**

- Top fund and ETF holders with % held, value, and report date

---

## Financial Statements

Type `FA` to open financial statements. Use the sub-tab buttons to switch between statements.

**INCOME**

Income statement for the last four fiscal years: revenue, cost of revenue, gross profit, gross margin, R&D, SG&A, operating income, EBITDA, net income, net margin.

**BALANCE**

Balance sheet for the last four fiscal years: cash, investments, receivables, inventory, PP&E, goodwill, total assets, short-term and long-term debt, total liabilities, stockholders' equity.

**CASH FLOW**

Cash flow for the last four fiscal years: operating cash flow, capex, free cash flow, investing and financing activities, net change in cash.

**RATIOS**

Valuation and profitability ratios: P/E, forward P/E, P/B, P/S, EV/EBITDA, beta, dividend yield, gross margin, net margin, ROE, ROA, debt/equity, current ratio.

---

## Estimates and Earnings

Type `EE` or `ERN` to open the estimates and earnings panel. It has four sub-tabs.

**ESTIMATES**

Analyst consensus for EPS and revenue across four periods (current quarter, next quarter, current year, next year): average, low, and high estimates, analyst count, and year-over-year growth.

**HISTORY**

Historical EPS results: actual vs estimated EPS, surprise amount and %, and a BEAT or MISS badge for each quarter.

**OWNERSHIP**

Institutional holders: organization name, % held, shares, value, date reported, and quarter-over-quarter change. The top of the panel shows % held by institutions and % held by insiders.

**INSIDERS**

Recent insider transactions: filer name and relation to company, transaction type, shares, value, and direct/indirect ownership flag.

**TRANSCRIPT**

Fetches the most recent earnings-related 8-K from SEC EDGAR and runs an AI structured analysis. Click FETCH LATEST TRANSCRIPT to start.

The panel shows: executive summary, EPS actual vs estimate and revenue, beat/miss/in-line result, guidance statements from management, key themes, risks mentioned, overall sentiment (BULLISH / NEUTRAL / BEARISH), and notable management quotes verbatim.

After the analysis loads, the ASK THE TRANSCRIPT input lets you ask free-text questions about the call. Answers are grounded in the transcript text. Click the refresh icon to re-fetch and re-analyze.

**Earnings Calendar**

Type `ECAL` or `EARN` to open the earnings calendar. It shows upcoming earnings dates for all symbols in your watchlist, grouped by date. Each entry shows the EPS estimate with low/high range and revenue estimate. Click any entry to load that symbol. The calendar covers the next 90 days plus the prior two days.

---

## SEC Filings

Type `FILINGS` or `CF` to open the filings panel.

**Browsing filings**

The left pane lists filings from SEC EDGAR. Use the form type filter buttons to narrow to 10-K, 10-Q, 8-K, proxy, or S-1 filings.

**Viewing a filing**

Click any row to load the document in the right pane. The viewer renders the filing directly in the app with dark-mode styling. If the document fails to load, click "Open in browser" in the toolbar to open it externally.

**Document Q&A**

With a filing open, type a question in the input at the bottom of the viewer and press Enter or click ASK. The AI reads the filing text and answers the question directly. Useful for pulling specific numbers, dates, management statements, or risk factors from long documents without reading them in full. The Q&A clears automatically when you open a different filing.

**Filing alerts**

Click ALERTS in the header to open the alert panel. Select a form type and click "+ WATCH [SYMBOL]" to be notified when a new filing of that type is published. Alerts are checked every 30 minutes. You'll get an in-app toast notification when a new filing is detected. Hover any alert chip and click X to remove it.

---

## Options Analytics

Type `OPT` to open the options chain. It has three sub-tabs.

**CHAIN**

Calls on the left, puts on the right, for the selected expiration. Use the expiry buttons in the header to switch dates.

Columns: strike, last price, bid, ask, volume, open interest, implied volatility, and greeks (delta, gamma, vega, theta) computed with Black-Scholes at r = 4.5%.

In-the-money options are highlighted. Hover any row and click the + button to add that contract to the payoff diagram.

**FLOW**

Options flow across all expirations:

- Put/call volume and OI ratios with a bullish/bearish signal tile
- Unusual activity: contracts with volume >= 50 and vol/OI >= 2x, sorted by ratio
- Most active: top 20 contracts by volume

**PAYOFF**

Multi-leg payoff diagram:

1. Add legs from the CHAIN tab using the + button on any row
2. Toggle each leg between LONG and SHORT
3. Adjust quantity if needed
4. The chart shows P&L at expiration across a price range

The stats bar shows max profit, max loss, and breakeven prices. Click CLEAR ALL to reset.

**Implied Volatility Surface**

Type `VOLS` to open the 3D implied volatility surface. It plots IV across strikes and expirations as a 3D mesh, showing term structure and skew.

---

## Portfolio

Type `PORT` or `PRTU` to open the portfolio panel. It has four sub-tabs.

### POSITIONS

The main holdings table. Columns: shares, cost per share, current price, market value, unrealised P&L, P&L%, and portfolio weight.

The summary bar shows total market value, total cost, total unrealised P&L, and overall return.

**Adding a position**

Use the form at the bottom of the panel: enter the ticker, number of shares, and average cost per share, then click ADD.

**CSV import**

Click IMPORT CSV to load a CSV file. Format:

```
SYMBOL,SHARES,COST_BASIS
AAPL,100,142.50
MSFT,50,280.00
```

A header row is required and is skipped. All positions in the file are added.

**Removing a position**

Hover any row and click the X on the right.

**Refreshing quotes**

Prices are fetched automatically when the panel loads. Click the refresh button in the top right to get updated quotes.

### PERF

Performance attribution:

- Contribution by position: weight, P&L, P&L%, and contribution to total portfolio return for each holding
- Bar chart scaled to the largest absolute P&L
- Sector exposure table: market value, weight, and P&L grouped by sector

### RISK

Click LOAD RISK DATA to fetch one year of daily price history for all positions. This takes a few seconds and is loaded on demand.

- Portfolio beta: weighted average of individual position betas
- 1-day historical VaR at 95% confidence: the 5th percentile of simulated daily portfolio returns over the past year
- Correlation matrix: Pearson correlations between all positions from daily log-returns, shown as a colour heatmap (green = positive correlation, blue = negative)
- Per-position table: beta, weighted beta contribution, 52-week change, dividend yield

### SCENARIO

What-if analysis with no data fetching required:

1. Drag the global shock slider to apply a uniform price move to all positions (-50% to +50%)
2. Type a custom % in any row to override that position individually
3. Scenario market value, P&L impact in dollars, and impact % update in real-time

Click RESET to go back to current prices.

---

## Bond Analytics

Type `BOND`, `YAS`, or `FI` to open the bond analytics panel. No market data feed is required — all calculations run locally from your inputs.

### CALC

**Inputs (left panel)**

| Field | Description |
|---|---|
| Face value | Par amount (default 1,000) |
| Coupon % | Annual coupon rate |
| Frequency | Coupon payments per year (1 = annual, 2 = semi-annual, 4 = quarterly) |
| Periods | Total number of coupon periods remaining |
| Solve for | Choose YIELD (enter price to solve for YTM) or PRICE (enter yield to solve for clean price) |
| Price / YTM | The known value; the panel solves for the other |

**Analytics (right panel)**

| Metric | Description |
|---|---|
| Clean price | Bond price as % of face value |
| Yield to maturity | Internal rate of return to maturity |
| Accrued interest | Coupon accrued since last payment (simplified) |
| Macaulay duration | Weighted average time to cash flows, in periods |
| Modified duration | Price sensitivity per 100 bps change in yield |
| Convexity | Second-order price sensitivity (numerical) |
| DV01 | Dollar value of 1 bp per $1M face value |

The yield solver uses Newton-Raphson iteration with a numerical derivative and converges to within 1e-10 in under 300 iterations for any realistic bond.

**Cash flow table**

Lists every coupon payment and the final principal repayment, with discount factors and present values.

**Sensitivity table**

Shows clean price, change in price, and DV01 at nine yield shocks: -200, -100, -50, -25, 0, +25, +50, +100, +200 basis points. Positive shocks are highlighted in red (prices fall as yields rise).

### CURVE

Plots the bond as an amber dot on the live US Treasury yield curve. The X position is the bond's maturity in years (periods divided by frequency); the Y position is the bond's YTM.

Treasury data loads from FRED via the `MACRO` panel. If it has not been loaded in the current session, the CURVE tab triggers it automatically.

The price-yield sensitivity chart below the curve shows how the bond price changes across a continuous yield range from -200 bps to +200 bps relative to current YTM.

---

## FX Rates

Type `FX` or `FXGO` to open the FX panel. Rates load automatically on open and can be refreshed with the REFRESH button.

### RATES

Grid of 12 currency pairs grouped by tier:

- G3: EUR/USD, GBP/USD, USD/JPY
- Majors: USD/CHF, AUD/USD, USD/CAD, NZD/USD
- EM: USD/CNH, USD/MXN, USD/BRL, USD/INR, USD/SGD

Each card shows the current rate and percentage change. Click any pair to load it as the active symbol and jump to the quote panel.

### MATRIX

Cross-rate table for G8 currencies: USD, EUR, GBP, JPY, CHF, AUD, CAD, NZD.

The value at row R, column C is how many units of C you get for 1 unit of R. All cross rates are derived from the live Yahoo Finance spot rates via USD as the pivot currency.

### FORWARDS

Outright forward rates for seven G10 pairs across five tenors using covered interest rate parity.

**Formula**

```
F = S x (1 + r_quote x T) / (1 + r_base x T)
```

Where S is the spot rate, r_base and r_quote are annualised policy rates, and T is the tenor in years.

**Rate inputs**

The top section shows an editable rate for each currency. Defaults are set to approximate current central bank policy rates (USD 4.25%, EUR 2.50%, GBP 4.00%, JPY 0.50%, CHF 0.75%, AUD 3.85%, CAD 3.50%, NZD 3.75%). Edit any rate to reprice all forwards in real-time.

**Tenors**

1 week, 1 month, 3 months, 6 months, 1 year.

**Forward pips**

The pip column shows the forward premium or discount in pips. For pairs quoted to 4 or 5 decimal places (EUR/USD, GBP/USD) pips are 0.0001; for JPY pairs pips are 0.01.

A positive pip value means the base currency is at a forward premium (higher yield in quote currency or lower yield in base). A negative value means the base is at a forward discount.

---

## Commodities

Type `CMDTY` or `COMM` to open the commodities panel.

### SPOT

Table of 15 front-month futures contracts grouped by sector:

- Energy: WTI crude (CL=F), Brent crude (BZ=F), natural gas (NG=F), heating oil (HO=F), RBOB gasoline (RB=F)
- Metals: gold (GC=F), silver (SI=F), copper (HG=F), platinum (PL=F)
- Agriculture: corn (ZC=F), wheat (ZW=F), soybeans (ZS=F), coffee (KC=F), cotton (CT=F), sugar (SB=F)

Columns: contract name, ticker, price, change, change%, unit. Click any row to load the contract symbol.

Grain and soft commodity prices are in cents per bushel or pound, which is standard futures market convention.

### CURVES

Forward term structure for a selected commodity.

1. Choose a commodity from the dropdown (WTI crude, natural gas, gold, corn, wheat, soybeans)
2. Click LOAD CURVE
3. The panel fetches the next 12 monthly dated contracts and plots available prices

The chart shows price on the Y axis and delivery month on the X axis. A green label means contango (later months more expensive than front), amber means backwardation (later months cheaper). The table below the chart shows each contract price and its premium or discount versus the front month.

Not every monthly contract exists on Yahoo Finance for every commodity. Gold for example trades in fewer months than crude. Unavailable contracts are skipped and the curve is drawn from what is available.

### ANALYTICS

Cross-commodity spread analytics computed from the live SPOT prices. No additional data fetches are needed.

| Spread | Formula | Unit |
|---|---|---|
| 3-2-1 crack spread | (2 x RBOB + 1 x Heating Oil - 3 x WTI) / 3 | $/bbl |
| WTI-Brent spread | WTI - Brent | $/bbl |
| Oil/gas ratio | WTI per boe / Natural gas per boe | ratio |
| Gold/silver ratio | Gold price / Silver price | oz gold per oz silver |
| Gold/copper ratio | Gold price / Copper price | ratio |
| Corn/wheat ratio | Corn (cents/bu) / Wheat (cents/bu) | ratio |
| Soybean-corn spread | Soybeans - Corn | cents/bu |

The 3-2-1 crack spread is the standard refinery margin proxy: 3 barrels of crude oil processed to yield 2 barrels of gasoline and 1 barrel of heating oil. A positive value means refining is profitable at current prompt prices.

RBOB and heating oil prices are converted from cents per gallon to dollars per barrel (multiply by 42) before the formula is applied.

The oil/gas ratio uses a BTU equivalence of 5.8 MMBtu per barrel to convert natural gas from $/MMBtu to a barrel-equivalent.

---

## Equity Screener

Type `SCRN` or `SCREEN` to open the screener.

**Running a screen**

Leave the SYMBOLS field blank to screen your entire watchlist, or enter a comma-separated list of tickers. Fill in any filter fields you want and click RUN SCREEN.

**Filters**

| Filter | Description |
|---|---|
| MKT CAP MIN/MAX ($B) | Market cap range in billions |
| P/E MIN/MAX | Trailing P/E ratio range |
| REV GROWTH MIN (%) | Minimum revenue growth |
| NET MARGIN MIN (%) | Minimum net profit margin |
| D/E MAX | Maximum debt-to-equity ratio |
| ROE MIN (%) | Minimum return on equity |
| BETA MIN/MAX | Beta range |
| SECTOR | Partial sector name match (e.g. "Technology") |

Leave any field blank to skip that filter.

**Results**

Click any column header to sort. Click any row to load that symbol. Filters are applied client-side so you can adjust them without refetching.

**AI screener**

Click the AI button in the header to open the natural-language input. Type a description of the stocks you want — for example "profitable large-cap technology with low debt and 15%+ revenue growth" — and press Enter or click SCREEN. The AI converts the description into filter values and applies them to the criteria grid. A summary of the applied filters appears below the input so you can verify the interpretation. You can edit individual fields manually after the AI sets them.

**Saving a screen**

Click SAVED to open the saved screens panel. Enter a name and click SAVE to store the current criteria. Click any saved screen name to reload it. Hover and click X to delete.

---

## Macro and Rates

Type `MACRO` or `YC` to open the macro panel.

**CURVE**

US Treasury yield curve from FRED:

- Current curve with data point markers
- One year ago curve overlaid for comparison
- Maturities from 1 month to 30 years
- Current yield and change vs prior year for each point

**CALENDAR**

Global economic calendar from ForexFactory:

- Event name, country, release time
- Actual vs consensus vs previous
- Surprise score (deviation from consensus)
- Impact level: low, medium, or high
- Filter by country, impact, and date range

**COUNTRIES**

Country macro profiles from the World Bank: GDP growth, CPI, unemployment, GDP per capita (PPP), current account, and government debt. Type a country name or click from the list.

**SHIPPING**

Baltic Dry Index chart via Yahoo Finance (`^BDIY`): 1-year daily chart, current BDI level, and peak price annotation.

---

## Geographic Intelligence Map

Type `BMAP` or `GMAP` to open the globe.

Drag to rotate, scroll to zoom, double-click to reset.

**Macro layers**

Click the layer buttons on the right panel to colour countries by a macroeconomic indicator: GDP growth, CPI, unemployment, real interest rate, government debt/GDP, current account/GDP, CO2 per capita, or internet users. Data is from the World Bank.

**Country profiles**

Click any country to open its macro profile. Shift-click a second country to compare two countries side by side.

**Earthquakes**

USGS 7-day M2.5+ events shown with felt-radius rings and ShakeMap intensity colours. Click any marker for details including magnitude, depth, and location.

**Tropical storms**

NOAA NHC active storms with Saffir-Simpson colour scale, 5-day forecast track, and wind radii at 34, 50, and 64 knots. Click a storm marker for the detail panel.

**Historic storm tracks**

HURDAT2 Atlantic and East Pacific tracks plus IBTrACS global basin tracks back several decades. Colour-coded by intensity with animated particles along the track. Use the year buttons and category filters to explore.

**Natural events**

NASA EONET active and historic wildfires, volcanoes, and floods. Active events use animated markers; historic events use dimmer static markers. The unified event search overlay lets you search and filter across all event types.

**Power plants**

WRI global database, plants >= 100 MW. Colour-coded by fuel type (coal, gas, hydro, wind, solar, nuclear, oil, other). Size scales logarithmically with capacity. Click a marker for name, type, capacity, and country.

**Ports**

~3,800 ports from the World Port Index. Each port shows harbour size, type, UN/LOCODE, MarineTraffic and Google Maps links, and a list of nearby ports within 200 km.

**Vessel tracking**

Click VESSEL SEARCH in the ASSETS sidebar. Enter an MMSI or IMO number to look up a vessel, or switch to NAME mode to search by name. The vessel appears on the globe with a triangle marker rotated to its course heading. The detail panel shows name, type, flag, speed, destination, and ETA. A dashed arc shows the vessel's recent track history.

Vessel tracking requires a MyShipTracking API key and secret. Configure them in CFG.

**Correlation network**

Click the CORR sub-tab to switch to the equity correlation globe. Shows 18 country ETFs connected by arcs coloured and sized by their 1-year daily return correlation.

---

## OANDA CFD Trading

Type `TRADE`, `OANDA`, or `ACCT` to open the trading panel, or press F8. Before using this panel, configure your OANDA API token in CFG.

The panel supports all instrument types available to your OANDA account: FX pairs, index CFDs (SPX500_USD, NAS100_USD, UK100_GBP, GER40_EUR, etc.), commodity CFDs (WTICO_USD, XAUUSD, etc.), bond CFDs, and individual stock CFDs where your account has access.

**Account selector**

If your token has access to more than one account (e.g. a practice account and a live account, or multiple subaccounts), a dropdown appears in the panel header showing each account's alias, ID, currency, and NAV. Select a different account to switch immediately — the selection persists across sessions. If you have only one account it is selected automatically and shown as a compact label.

The panel has five tabs.

### ACCOUNT

Live account snapshot, refreshed every 10 seconds:

- NAV (net asset value)
- Unrealised P&L
- Margin available and margin used
- Margin closeout % (turns red above 80%)
- Open position count, open trade count, pending order count
- Realised P&L for the session

A PRACTICE or LIVE badge appears in the header indicating which environment is active.

### MONITOR

Live view of all open trades, updated every few seconds. Each trade card shows the instrument, direction, entry price, live P&L, and price move. Click any trade card to open an interactive candlestick chart for that instrument.

**AI signal detection**

The chart automatically detects trading signals on every candle update:

| Signal | Condition | Severity |
|---|---|---|
| RSI Overbought | RSI > 70 on a long position | Urgent |
| RSI Oversold | RSI < 30 on a short position | Urgent |
| EMA Cross | EMA20 crosses below EMA50 on a long | Caution |
| Near Stop Loss | > 80% of SL distance consumed | Urgent |
| Near Take Profit | > 80% of TP distance reached | Caution |
| Big Move | > 50 units of pip size in the trade direction | Info |

Active signals appear in a strip between the chart header and the price pane. Click **AI Read** to request an AI assessment. The AI responds with a recommendation (Close, Hold, Move SL to Breakeven, or Take Partial), a confidence level, and a one-sentence reason. Click the action button to execute immediately.

Trade cards show a coloured badge with the number of active signals.

### POSITIONS

Open positions aggregated by instrument. Each row shows long units and average long entry price, short units and average short entry price, and combined unrealised P&L.

To close a position, click LONG or SHORT on the relevant row. A YES / NO confirmation appears inline.

### TRADES

The TRADES tab shows four sections.

**Pending Orders**

All orders sitting on OANDA waiting to trigger — stop losses, take profits, limit orders, and stop orders placed from the ORDER tab. Each row shows the order ID, type, instrument, units, trigger price, and linked trade ID. Click CANCEL to remove an order immediately.

**Trade History**

The last 100 trades (open and closed), newest first. Columns: trade ID, instrument, initial units (sign = direction), entry price, close price, P&L, status, and open timestamp. Closed trades are dimmed. P&L shows unrealised for open trades and realised for closed trades.

**Fill History**

All ORDER_FILL transactions from the last ~500 OANDA transactions, fetched from the transactions endpoint. This is the only view that shows partial closes and reduces — trades modified in OANDA's netting mode do not appear as new entries in the trade history but are visible here. Columns: transaction ID, instrument, units, fill price, P&L (if any), fill type (OPEN / CLOSE / REDUCE), and timestamp.

**Order Log**

A local SQLite record of every order submitted from this terminal, persisted across sessions. Columns: timestamp, instrument, direction and order type, units, price (fill price for MARKET orders; limit/stop price for LIMIT/STOP orders), and status (FILLED or PENDING). The log is independent of OANDA's own transaction history — it is written at submission time and is never affected by account or environment switches.

Click the refresh button (↺) on any section header to reload that section.

### ORDER

**Instrument** — a searchable picker loaded from your account's available instruments. Type a name (e.g. `EUR`) or a display name (e.g. `Gold`) to filter. Press Enter or click a result to select. The instrument's display name, type (CURRENCY / CFD / METAL), and minimum trade size are shown below the picker.

**Direction** — click BUY or SELL.

**Order type** — three options:

| Type | Behaviour |
|---|---|
| MARKET | Fill immediately at the best available price. |
| LIMIT | Resting order at a specific price. Buys at or below; sells at or above. Useful for fading moves. |
| STOP | Triggers once price reaches the level. Buys at or above; sells at or below. Useful for breakout entries. |

LIMIT and STOP orders are placed as Good Till Cancelled (GTC) and appear in the Pending Orders section until filled or cancelled.

**LIMIT / STOP price** — visible when the order type is LIMIT or STOP. Enter the exact price level. A hint shows the current market price and the distance to the specified level.

**Units and position sizing** — enter the number of units directly, or use the risk sizing tool. Once a stop loss price is set, a suggestion appears next to the UNITS label:

```
units = floor( NAV × risk% ÷ |entry price − stop loss| )
```

The risk percentage input (default 1%) sits inline with the units field. Click the suggestion to fill in the units automatically. For non-account-currency instruments the result is an approximation; adjust as needed.

**Stop Loss / Take Profit** — both are optional. Enter the price level, not a distance. Direction is validated before submitting:

- MARKET orders: SL/TP checked against the current live bid or ask.
- LIMIT/STOP orders: SL/TP checked against the limit/stop price.

An error is shown immediately if values are on the wrong side — the order is not sent to OANDA.

**Live price** — current bid and ask update every 3 seconds. For FX and metals the spread is shown in pips; for index and commodity CFDs it is shown as a raw price difference.

**AI Trade Idea**

Click **Generate** to get an AI-powered trade idea. The AI considers all instrument types available to your account (FX, indices, commodities, bonds), receives live prices for all monitored instruments and the current account state, and returns a single setup with instrument, direction, units, stop loss, take profit, rationale, confidence, and risk summary. Click **Load into Order Form** to pre-fill all fields. SL and TP values are validated against live prices before loading.

**Placing an order**

1. Fill in the form and click REVIEW ORDER.
2. A confirmation screen shows the order type, price (or approximate fill price for market orders), and environment.
3. Live orders show a warning that real funds will be used.
4. Click CONFIRM to place the order, or CANCEL to go back.
5. On success: MARKET orders show the fill price and trade ID; LIMIT and STOP orders show ORDER PENDING with the requested price. The order is logged locally regardless of type.

If OANDA rejects or cancels the order (for example because the stop loss would immediately trigger), an error message shows the specific cancellation reason.

**Live trading**

Live trading is off by default. To enable it, go to CFG, check "Enable live trading", and save. The panel shows a LIVE badge when live mode is active.

---

## AI Assistant

Type `CHAT`, `AI`, or `NLP` to open the AI assistant, or press F9.

The assistant receives live market data as context on every message: the current quote, fundamentals, recent news headlines, and your portfolio positions. Context chips in the panel header show what is loaded and from which sources.

**Providers**

Configure the provider in CFG under AI ASSISTANT.

- OpenAI-compatible: enter a base URL (e.g. `http://localhost:11434` for Ollama) and a model name. An API key is optional if your endpoint does not require one.
- Claude (Anthropic): select a model from the dropdown and enter your Anthropic API key.

Click TEST in CFG to verify the connection before saving.

**Using the chat**

Type a question and press Enter or click SEND. Example prompts appear in the panel — click any to populate the input.

The context is reset and the conversation is cleared when you load a new symbol.

Click CLEAR to start a fresh conversation without switching symbols.

API keys are stored on device and never sent to the browser.

---

## Backtesting

Type `BT` or `BACKTEST` to open the backtesting panel.

Select a symbol, date range, and strategy, then click RUN.

**Strategies**

- SMA Crossover: long when the fast moving average crosses above the slow; exit when it crosses back.
- RSI Mean-Reversion: buy when RSI drops below the oversold threshold; sell when it rises above the overbought threshold.
- Bollinger Band Mean-Reversion: buy when price closes below the lower band; sell when price closes back above the middle band.

Each strategy has configurable parameters shown below the selector.

**Results**

The equity curve shows the strategy return indexed to 100 with buy (green triangle up) and sell (red triangle down) markers. The buy-and-hold benchmark is overlaid for comparison.

Statistics below the chart: CAGR, Sharpe ratio (annualised, 4% risk-free rate), max drawdown, win rate, alpha vs buy-and-hold, and trade count.

The trade log below the statistics shows every trade with entry and exit dates and prices, return %, holding period in days, and a WIN or LOSS badge.

---

## Alerts

### Price Alerts

Load a quote, then click ADD ALERT in the alert panel (bell icon in the header). Set a direction (above or below) and a price threshold. The app checks all active alerts every 60 seconds and fires a toast notification when the condition is met. Fired alerts are deactivated automatically.

Click the bell icon to manage alerts. You can delete any alert from the list.

### Filing Alerts

In the FILINGS panel, click ALERTS and add a watch for any symbol and form type. You'll be notified when a new filing of that type appears on EDGAR. Checks run every 30 minutes.

---

## Workspace

**Multi-panel layout**

Drag the divider between panels to resize. Press Alt+Z to maximise the active panel. Press Alt+Z again or Alt+X to restore. Press Alt+S to toggle between horizontal and vertical split.

**Detaching panels**

Click the pop-out icon in the top right of any panel to open it in a separate window. You can have multiple panels open across monitors simultaneously.

**Tab bar**

The tab bar below the command line shows all available panels. Click any tab to switch, or type the function code.

---

## Configuration

Type `CFG` to open settings.

**Polygon.io API key**

Required for real-time and delayed quotes, charts, news, and instrument search. Without a key, the app falls back to Yahoo Finance.

Sign up at [polygon.io](https://polygon.io) for a free key (delayed data). Paste it in and click SAVE.

**AI Assistant**

Connect to any OpenAI-compatible endpoint or Claude (Anthropic). Select the provider using the toggle, enter the required fields, and click TEST to verify, then SAVE.

For OpenAI-compatible endpoints (Ollama, LM Studio, vLLM, OpenAI): enter the base URL and model name. An API key is only needed if your endpoint requires one.

For Claude: select a model from the dropdown and enter your Anthropic API key.

**OANDA CFD Trading**

Connect to your OANDA account for CFD trading. No account ID is needed — all accounts linked to your token are discovered automatically.

1. Set the environment (PRACTICE or LIVE).
2. Enter your practice API token and/or live API token (found in your OANDA dashboard under Manage API Access).
3. If you want to enable live order placement, check "Enable live trading".
4. Click TEST to verify connectivity — all accounts found on the token will be listed with their IDs, currency, and NAV.
5. Click SAVE.

Once configured, open the TRADE panel. Your accounts appear in a dropdown in the panel header. Select the one you want to trade on. Practice and live tokens are stored separately and do not interfere with each other.

**MyShipTracking**

Required for vessel tracking on the BMAP globe. You need both a key and a secret from [myshiptracking.com](https://myshiptracking.com).

**Provider status**

Shows which data provider is active and whether configured keys have been detected.

---

## Keyboard Reference

| Key | Action |
|---|---|
| Enter | Execute command |
| Escape | Clear command line |
| Up / Down | Cycle command history |
| F1 | HELP panel |
| F2 | Quote (QR) |
| F3 | Company profile (DES) |
| F4 | Financial statements (FA) |
| F5 | News (NI) |
| F6 | Options chain (OPT) |
| F7 | Portfolio (PORT) |
| F8 | OANDA FX Trading (TRADE) |
| F9 | AI Assistant (CHAT) |
| F10 | Macro / yield curve (MACRO) |
| Alt+Z | Maximise active panel |
| Alt+X | Expand chart fullscreen |
| Alt+S | Toggle split direction (H/V) |
