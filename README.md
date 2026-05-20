# TradingView WebSocket Tools

A collection of Python tools for connecting to TradingView's WebSocket API — live price streaming, multi-market dashboards, and connection stress testing.

## Contents

### Scripts
| File | Description |
|------|-------------|
| `ws_connection_stress_test.py` | Tests N parallel WebSocket connections, measures rate limits, latency, and data integrity |

### Notebooks
| File | Description |
|------|-------------|
| `notebooks/multi_market_live_dashboard.ipynb` | Live dashboard for 10 tickers across US, Arab, and crypto markets with interactive dropdown |
| `notebooks/live_candlestick_chart.ipynb` | Real-time candlestick chart with Plotly — updates every 3 seconds |
| `notebooks/parallel_price_monitor.ipynb` | Monitors 1000 symbols across 10 parallel connections |

## Setup

```bash
pip install websocket-client plotly pandas ipywidgets
```

## Usage

### Stress test
```bash
python ws_connection_stress_test.py
```
Configure `N_PARALLEL`, `SYMBOL`, and `RUN_SECONDS` at the top of the file.

### Live dashboard
Open `notebooks/multi_market_live_dashboard.ipynb` in Jupyter and run all cells.

Supported markets out of the box: `NASDAQ`, `BINANCE`, `EGX`, `TADAWUL`, `ADX`, `KSE`

## How it works

TradingView exposes a WebSocket endpoint at `wss://data.tradingview.com/socket.io/websocket`.
These tools implement the full protocol: session creation, symbol resolution, historical data fetch, and live update streaming — without requiring a TradingView account.

## Notes

- Uses `unauthorized_user_token` — public access, no account needed
- All connections are read-only
- No API keys required
