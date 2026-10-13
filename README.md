# Daily SMA Candidate Scanner

A TradingView Pine Script indicator for screening a watchlist for symbols trading near their daily 50, 100, 150, or 200-period simple moving averages (SMAs).

## Features

- Calculates the distance between the closing price and each daily SMA.
- Detects when a daily candle's range intersects an SMA.
- Identifies how many SMAs are within a configurable proximity threshold.
- Produces a priority score from 0 to 100 for ranking candidates in TradingView's Pine Screener.
- Supports scanning stocks, ETFs, and ratio symbols with available price history.

## Priority Score

The score combines three components:

| Component | Maximum points | Description |
|---|---:|---|
| Proximity | 50 | Higher score when price is closer to its nearest SMA |
| Interaction | 30 | Awarded when the daily candle touches at least one SMA |
| Confluence | 20 | Awarded when multiple SMAs are within the proximity threshold |
| **Total** | **100** | |

The score is a screening heuristic, not a probability of a successful trade or a standalone trading signal.

## Installation

1. Open TradingView and launch Pine Editor.
2. Copy the contents of `daily-sma-candidate-scanner.pine` into the editor.
3. Save the script and add it to the chart.
4. Open Pine Screener and select the indicator and desired watchlist.
5. Filter `Nearest SMA Distance %` to your desired threshold, such as 3%.
6. Sort `Priority Score` in descending order to rank candidates.

## Notes

- By default, the indicator uses the last completed daily candle.
- The proximity threshold is configurable.
- A candle intersecting an SMA does not necessarily mean that support or resistance held.
- Review shortlisted charts for trend, price action, volume, and risk/reward before entering a trade.