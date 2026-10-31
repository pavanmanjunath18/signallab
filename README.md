# SignalLab

![status](https://img.shields.io/badge/status-building-orange)

Cross-asset signal research with honest backtests.

**Stack:** Python, Polars, pandas, NumPy, SciPy, pytest

> **Status: Building.** Launching soon.

## Highlights

- Parquet data layer over ETFs, FX, rates, and VIX, with data-quality tests that fail loudly on gaps, stale prints, and duplicate dates
- Four signal families: momentum, carry, value, and dispersion, each lagged so no signal sees data it could not have had
- Walk-forward backtester with a 5 bps transaction cost model, volatility targeting, turnover, drawdown, and exposure reporting
- Deflated Sharpe ratio that discounts results for the number of strategies tried
- Purged k-fold cross-validation with an embargo, so overlapping labels do not leak between train and test
- Reproducible bench scripts that write `bench/results/*.json`, and every README number comes from those files
- pytest suite that runs offline against fixture data, no network or API keys

Benchmarks will be published here once measured.

## Layout

```
src/signallab/   data layer, signals, backtester, overfitting statistics
tests/           data-quality, signal, and backtest tests (offline fixtures)
bench/           benchmark scripts and results/*.json
docs/            design notes, overfitting.md (deflated Sharpe and purging)
```

## Roadmap

- [ ] Week 1: data layer (Parquet, Polars, data-quality tests)
- [ ] Week 2: signals and walk-forward backtester
- [ ] Week 3: deflated Sharpe, purged k-fold CV, bench scripts, published benchmarks
