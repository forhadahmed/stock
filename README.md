stock
-----

Terminal-based stock market monitor using curses.

![Demo](https://raw.githubusercontent.com/forhadahmed/stock/master/demo.gif)

## Installation

```
cp stock /usr/local/bin/
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

## Search Aliases

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

## Features

- Real-time stock quotes
- Interactive braille chart with time navigation
- Configurable columns
- Sortable by any column
- Persistent watchlist and settings
- Market open/closed indicator (US Eastern)
- Color-coded gains/losses

## Requirements

- Python 3
