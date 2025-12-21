stock
-----

Terminal-based stock market monitor using curses and Yahoo Finance API.

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

| Key | Action |
|-----|--------|
| a, / | Search and add stocks |
| d | Delete selected stock |
| Tab | Cycle sort column |
| Enter | Toggle sort direction (none/asc/desc) |
| c | Column settings |
| Up/Down | Navigate stocks |
| PgUp/PgDn | Scroll 10 at a time |
| Home/End | Jump to first/last |
| q, Esc | Quit (or close current panel) |

## Search

- Single word: prefix search via Yahoo Finance API, select from results
- Multiple words: add each as stock symbol directly (e.g., "aapl goog msft")

## Columns

Press `c` to configure visible columns:

- Symbol, Price, Change, Chg %, Volume (default)
- Low, High, Open, PrevCls, 52W Lo, 52W Hi

Settings saved to `~/.stocks`.

## Features

- Real-time quotes from Yahoo Finance
- Configurable columns
- Sortable by any column
- Persistent watchlist and settings
- Market open/closed indicator (US Eastern)
- Color-coded gains/losses

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
| [a]dd [d]el [tab] sort [c]ols [q]uit                                        |
+-----------------------------------------------------------------------------+
```
