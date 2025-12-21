stock
-----

Terminal-based stock market monitor using curses.

![Demo](https://github.com/forhadahmed/stock/releases/download/v1.0/demo-small.gif)

## Installation

```
cp stock /usr/local/bin/
chmod +x /usr/local/bin/stock
```

## Usage

```
stock [symbol1] [symbol2] ...
```

Examples:
```
stock aapl goog msft           # start with these stocks
stock                          # use saved watchlist from ~/.stocks
```

## Keys

### Main View

| Key | Action |
|-----|--------|
| a, / | Search and add stocks |
| d | Delete selected stock |
| Enter | Open intraday chart |
| Tab | Cycle sort column |
| s | Toggle sort direction (none/asc/desc) |
| c | Column settings |
| Up/Down | Navigate stocks |
| PgUp/PgDn | Scroll 10 at a time |
| Home/End | Jump to first/last |
| q, Esc | Quit (or close current panel) |

### Chart View

| Key | Action |
|-----|--------|
| Tab | Cycle period (1D, 5D, 1M, 3M, 1Y, 5Y) |
| Left/Right | Scroll time cursor |
| Up/Down | Switch between stocks |
| q, Esc | Close chart |

## Search

- Single word: prefix search, select from results
- Multiple words: add each as stock symbol directly (e.g., "aapl goog msft")

### Search Aliases

Common names are automatically translated:

| Search | Symbol |
|--------|--------|
| sp500, s&p500, spx | ^GSPC (S&P 500) |
| dow, djia | ^DJI (Dow Jones) |
| nasdaq | ^IXIC |
| russell | ^RUT |
| vix | ^VIX |
| gold | GC=F |
| oil, crude | CL=F |
| btc, bitcoin | BTC-USD |
| eth, ethereum | ETH-USD |

## Chart View

Press Enter on any stock to view an interactive braille line chart.

Features:
- High-resolution braille character rendering
- 6 time periods: 1D, 5D, 1M, 3M, 1Y, 5Y
- Time cursor with price tracking
- Horizontal price grid lines
- Time axis with tick marks
- Live marker when market is open (1D view)
- Color-coded (green=up, red=down)

Chart data is cached to improve performance:
- 5D, 1M: 5 minutes
- 3M: 10 minutes
- 1Y: 1 hour
- 5Y: 2 hours

## Columns

Press `c` to configure visible columns:

- Symbol, Price, Change, Chg %, Volume (default)
- Low, High, Open, PrevCls, 52W Lo, 52W Hi

Settings saved to `~/.stocks`.

## Features

- Real-time stock quotes
- Interactive braille chart with time navigation
- Configurable columns
- Sortable by any column
- Persistent watchlist and settings
- Chart data caching
- Market open/closed indicator (US Eastern)
- Color-coded gains/losses
- Loading spinner on startup

## Files

| File | Purpose |
|------|---------|
| ~/.stocks | Watchlist and settings |
| ~/.stocks_cache | Chart data cache |

## Requirements

- Python 3
- No external dependencies (stdlib only)

## Screenshot

```
+-----------------------------------------------------------------------------+
| Sat Dec 21, 2024 - 10:30:45AM EST - US markets closed     [5 stocks]        |
|                                                                             |
| Symbol      Price       Change      Chg %       Volume                      |
| --------------------------------------------------------------------------- |
| AAPL        $248.52     +$2.34      +0.95%      45.2M                       |
| GOOG        $192.31     -$1.20      -0.62%      12.8M                       |
| MSFT        $438.12     +$5.67      +1.31%      28.4M                       |
| NVDA        $134.25     +$3.45      +2.64%      89.1M                       |
| TSLA        $421.06     -$8.32      -1.94%      67.3M                       |
|                                                                             |
| [a]dd [d]el [enter] chart [tab/s] sort [c]ols [q]uit                        |
+-----------------------------------------------------------------------------+
```

Chart view:
```
+-----------------------------------------------------------------------------+
| AAPL $248.52 (+$2.34, +0.95%) | 14:30 ET $247.85      1D  5D  1M  3M  1Y  5Y |
|                                                                             |
|    $252.00                                                                  |
|            .::..                                                            |
|    $250.00 .....::.                        .::.                             |
|                  '::..                  .::    ::.                          |
|    $248.00           '::.            .:'         ':.            |           |
|                         ':.       .:'               ':.         |           |
|    $246.00                '::...::'                   ':..     .|           |
|                                                           ':::'             |
|            --+----------+----------+----------+----------+--                |
|           09:30      10:30      12:00      13:30      15:00                 |
|                                                                             |
| [up/down] stock  [tab] period  [q] close                                    |
+-----------------------------------------------------------------------------+
```
