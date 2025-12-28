# stock

[![Python 3.6+](https://img.shields.io/badge/python-3.6+-blue.svg)](https://www.python.org/downloads/)

**A fast, terminal-based stock market monitor and portfolio tracker.** Real-time quotes, interactive braille charts, and persistent watchlists - all in your terminal with zero dependencies.

## Features

- **Real-time stock quotes** - Live price updates from Yahoo Finance
- **Interactive braille charts** - Historical price charts with keyboard navigation
- **Customizable watchlist** - Add/remove symbols, persisted to `~/.stocks`
- **Sortable columns** - Click any column header to sort
- **Market status indicator** - Shows market open/closed (US Eastern)
- **Color-coded display** - Green for gains, red for losses
- **Zero dependencies** - Single Python script, uses only standard library

## Installation

```bash
curl -O https://raw.githubusercontent.com/forhadahmed/stock/master/stock
chmod +x stock
sudo mv stock /usr/local/bin/
```

Or clone the repository:

```bash
git clone https://github.com/forhadahmed/stock.git
cd stock
chmod +x stock
./stock
```

## Usage

```bash
stock [symbol1] [symbol2] ...
```

### Examples

```bash
stock aapl goog msft           # Monitor specific stocks
stock                          # Use saved watchlist from ~/.stocks
stock btc eth                  # Track cryptocurrencies
stock sp500 dow nasdaq         # Track major indices
```

## Search Aliases

Built-in aliases for common symbols:

| Alias | Symbol | Description |
|-------|--------|-------------|
| `sp500`, `s&p500`, `spx` | ^GSPC | S&P 500 Index |
| `dow`, `djia` | ^DJI | Dow Jones Industrial Average |
| `nasdaq` | ^IXIC | NASDAQ Composite |
| `russell` | ^RUT | Russell 2000 |
| `vix` | ^VIX | Volatility Index |
| `gold` | GC=F | Gold Futures |
| `oil`, `crude` | CL=F | Crude Oil Futures |
| `btc`, `bitcoin` | BTC-USD | Bitcoin |
| `eth`, `ethereum` | ETH-USD | Ethereum |

## Keyboard Shortcuts

| Key | Action |
|-----|--------|
| `a` | Add symbol to watchlist |
| `d` | Delete symbol from watchlist |
| `r` | Refresh quotes |
| `q` | Quit |
| `←` `→` | Navigate chart time range |
| `↑` `↓` | Select stock |

## Requirements

- Python 3.6+
- Terminal with Unicode support (for braille charts)
