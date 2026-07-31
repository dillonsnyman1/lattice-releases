# Changelog

## v1.2.0 — 2026-07-31

### Quant Notebook
- New `NB` / `NOTEBOOK` / `NBOOK` panel: interactive Python notebook and C++ script runner wired to Lattice data
- Python kernel runs as a persistent subprocess managed in Rust — variables accumulate across cells, no Jupyter dependency required
- Matplotlib figures are captured automatically and rendered as inline PNG images below each cell
- pandas DataFrames are rendered as styled HTML tables
- Pre-injected globals in every session: `lattice` (pointed at the local API), `pd`, `np`, `plt`
- `Shift+Enter` runs a cell and advances to the next; `Ctrl/Cmd+Enter` runs in place
- Toolbar: Run All, interrupt (■ STOP), add cell, clear outputs, save, restart kernel
- Kernel status badge: off / starting / idle / busy / dead
- Notebooks persist to SQLite with 1.5-second auto-save; sidebar for create and delete
- C++ tab: single-file script runner compiled with `clang++` or `g++`; `lattice.hpp` is available automatically with no include path setup required

### Local REST API
- Three new endpoints: `GET /v1/screener?symbols=AAPL,MSFT,...` (bulk fundamental data for up to 60 symbols in parallel), `GET /v1/macro` (US Treasury yield curve 3M → 30Y), `GET /v1/oanda/account` (NAV, margin, P&L for the active OANDA account), `GET /v1/oanda/positions` (open positions with units, average price, and unrealised P&L)
- OANDA endpoints proxy through the token and account already configured in CFG — no additional setup needed

### Python SDK (`sdk/lattice.py`)
- `history(symbol, range, interval)` — returns a pandas DataFrame with a UTC DatetimeIndex and numeric-typed OHLCV columns; zero boilerplate in notebooks
- `screen(sector, min_market_cap, max_pe, min_net_margin, ...)` — criteria-based screener across a built-in ~120-symbol US large/mid-cap universe; market cap in $B, margins and growth as fractions
- `oanda_account()` — OANDA account summary (NAV, balance, unrealised P&L, margin)
- `oanda_positions()` — OANDA open positions (instrument, units, average price, unrealised P&L)

---

## v1.1.0 — 2026-07-23

### News
- Finnhub added as an optional secondary news source. Configure a free API key in CFG. When active, results from both sources are merged and deduplicated automatically.
- AI SUMMARY button in the news panel synthesises the latest headlines into a 3-4 sentence narrative. Requires an AI provider configured in CFG.

### Fundamentals
- New THESIS tab in the fundamentals panel. Generates a bull case, bear case, sentiment verdict, summary, and key risks from the loaded fundamental data. Powered by your configured AI provider.

---

## v1.0.0 — 2026-07-22

First public release.

### Market Data and Quotes
- Real-time and delayed quotes with price, change, bid/ask, volume, and 52-week range
- Candlestick charts with interval and range controls, dynamic Y-axis rescaling, and smart price formatting
- Per-symbol news feed

### Instrument and Company
- Universal search with autocomplete
- Company profiles: logo, description, sector, employees, exchange
- Key executives table
- Related securities and top fund holders

### Fundamentals
- Valuation ratios, TTM margins, and balance sheet snapshot
- Income statement, balance sheet, and cash flow — 4-year annual tables

### Estimates and Earnings
- EPS and revenue consensus estimates with analyst count and growth forecasts
- Earnings history with actual vs estimated EPS, surprise %, and beat/miss badge
- Earnings calendar for watchlist symbols grouped by date
- Institutional ownership and insider transactions
- Earnings transcript analysis: fetches the latest 8-K from SEC EDGAR and returns a structured AI breakdown covering summary, guidance, key themes, risks, sentiment, and notable quotes. Free-text Q&A against the transcript is available after analysis loads

### SEC Filings
- EDGAR filing search across 10-K, 10-Q, 8-K, proxy, and S-1 filings
- In-app filing viewer with dark-mode styling and sandboxed rendering
- Filing alerts with 30-minute background polling and in-app notifications
- Document Q&A: ask plain-English questions about the open filing and get answers grounded in the document text

### Equity Screener
- Screen up to 60 symbols across 12 filter dimensions: market cap, P/E, revenue growth, net margin, D/E, ROE, beta, and sector
- Sortable 15-column results table
- Named saved screens with one-click reload
- Natural-language screener: describe the stocks you want in plain English and the AI sets the filters automatically

### Options Analytics
- Full options chain with calls, puts, IV, open interest, and greeks (Black-Scholes)
- Options flow with put/call ratios, unusual activity detection, and most active by volume
- 3D implied volatility surface across strikes and expirations
- Multi-leg payoff diagram with breakeven markers and max profit/loss

### Portfolio and Risk
- Position entry with mark-to-market P&L, weights, and portfolio summary
- Performance attribution with contribution table, sector breakdown, and bar chart
- Risk metrics: portfolio beta, 1-day historical VaR at 95% confidence, and Pearson correlation heatmap
- Scenario analysis with a global shock slider and per-position overrides
- CSV import

### Bond Analytics
- Price/yield calculator with Newton-Raphson solver
- Macaulay duration, modified duration, convexity, DV01, and accrued interest
- Cash flow schedule and sensitivity table across nine yield shock scenarios
- Bond overlaid on live US Treasury yield curve

### FX
- Live spot rates for 12 major pairs with a full G8 cross-rate matrix
- Covered interest rate parity forward calculator across five tenors

### Commodities
- Spot prices for energy, metals, and agriculture
- Forward curve charts with contango/backwardation indicator
- Spread analytics: crack spread, WTI/Brent, gold/silver, and more

### Macro and Rates
- US Treasury yield curve (current vs one year ago overlay)
- Global economic calendar with consensus vs actual and surprise scoring
- Country profiles via World Bank

### Geographic Intelligence
- D3 orthographic globe with choropleth macro layers (GDP, CPI, unemployment, and more)
- USGS earthquake layer: 7-day M2.5+ with animated seismic pulse rings
- NOAA active tropical storms with 5-day forecast tracks and wind radii
- Historic storm tracks from HURDAT2 and IBTrACS across all basins
- NASA EONET active and historic wildfires, volcanoes, and floods
- WRI global power plants and World Port Index
- Vessel tracking via MyShipTracking API
- Equity correlation network across 18 country ETFs

### OANDA CFD Trading
- Full trading integration via OANDA REST API
- Supports FX pairs, index CFDs, commodity CFDs, and bond CFDs
- Multi-account support with automatic account discovery
- Practice and live environments with a clear toggle
- Market, limit, and stop order entry with two-step review and confirm
- Position sizing tool: enter a stop loss and risk %, get the exact unit count
- Pending orders, trade history, fill history, and local order audit log
- AI trade idea generator and signal detection in the trade chart

### AI Assistant
- Conversational financial analyst with full market data context
- Supports OpenAI-compatible providers (Ollama, LM Studio, OpenAI) and Claude (Anthropic)
- Active symbol quote, fundamentals, news, and portfolio positions included in every message

### Backtesting
- SMA crossover, RSI mean-reversion, and Bollinger Band strategies
- Equity curve with buy/sell markers and buy-and-hold benchmark overlay
- CAGR, Sharpe ratio, max drawdown, win rate, alpha, and scrollable trade log

### Developer Tools
- Local REST API on localhost:7842 with key management
- Python and C++ SDKs

### Workspace
- Resizable multi-panel workspace with horizontal and vertical splits
- Detachable panels into separate windows
- Persistent watchlist with drag-to-reorder and asset-type badges
- Bloomberg-style command line
- Automatic updates via in-app chip in the top bar
