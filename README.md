# Multi-Asset Regime and Strategy Backtest

This project presents a notebook-based multi-asset regime and strategy backtest across crypto, equities, gold, and rates. It covers regime detection, portfolio construction, backtesting, stress handling, and AI usage transparency in a clean and readable format.


## What Is Included

This repository covers:

- Part 1: Market regime analysis
- Part 2: Strategy design and historical simulation
- Part 3: Stress scenario response
- Part 4: AI usage transparency

## Files

- [multi_asset_strategy_crypto.ipynb] : main notebook with analysis, charts, and backtest
- [BTCUSDT_2020_2025.csv]
- [ETHUSDT_2020_2025.csv]
- [OANDA_XAUUSD_2020_2025.csv]
- [SP500_2020_2025.csv]
- [US10Y_2020_2025.csv]

## Data Coverage

- Date range: `2020-01-01` to `2025-12-31`
- Frequency: daily
- Number of rows per asset: `2,192`

## Instruments Used

- `BTCUSDT`: Bitcoin
- `ETHUSDT`: Ethereum
- `XAUUSD`: Gold
- `SP500`: S&P 500
- `US10Y`: US 10-Year Treasury Yield

## What The Notebook Does

### 1. Regime Detection

The notebook computes:

- daily log returns
- rolling 20-day realized volatility
- rolling BTC/SP500 correlation
- crypto breadth across BTC and ETH
- Gold relative strength versus equities

Market regimes are then classified into:

- `Risk-On Momentum`
- `Transition`
- `Defensive Risk-Off`
- `Liquidity Stress`

The regime thresholds are driven using sample quantiles instead of arbitrary fixed cutoffs.

### 2. Position Sizing

Portfolio weights are also **data-driven**.

- computes momentum-style signals for BTC, ETH, Gold, and SP500
- adjusts those signals using inverse volatility
- normalizes them into portfolio weights
- scales exposure to a target volatility level
- applies correlation and drawdown-based risk overlays


### 3. Strategy Variants

The project compares two versions of the strategy:

- `Balanced`: stronger participation and higher return
- `High Sharpe`: more defensive, lower volatility, cleaner risk-adjusted profile

## Results

### Balanced

- Cumulative return: `165.86%`
- Annualized return: `11.90%`
- Annualized volatility: `4.33%`
- Sharpe ratio: `2.75`
- Maximum drawdown: `-5.08%`

### High Sharpe

- Cumulative return: `42.05%`
- Annualized return: `4.12%`
- Annualized volatility: `1.46%`
- Sharpe ratio: `2.83`
- Maximum drawdown: `-0.96%`

## Stress Scenario Section

The project also includes a stress-response section for a systemic selloff scenario involving:

- BTC down `18%`
- ETH down about `28%`
- simultaneous weakness in Gold and equities
- volatility spikes across asset classes

The response is structured around:

- immediate exposure reduction
- liquidity protection
- re-entry discipline
- actions deliberately avoided during market panic

## Why This Project Is Useful To Review

Someone reading only the notebook or this README should still be able to understand:

- what data is used
- how regimes are defined
- how the strategy allocates capital
- how risk is controlled
- what the backtest results look like
- how the framework behaves under stress

## How To Open

Open the notebook directly:

- [multi_asset_strategy_crypto.ipynb]


## Summary

This repository presents a clean multi-asset regime and portfolio Backtest framework built on daily data from 2020 through 2025. The regime rules and asset weights are both driven by computed statistics, and the results are presented in a way that is readable without digging through the underlying code.
