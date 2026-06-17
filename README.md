# 🐷 PiggyBank - Trading Bot

![Status](https://img.shields.io/badge/Status-Work%20In%20Progress-yellow)

> ⚠️ **Disclaimer:** This project is for educational purposes only. It does not constitute financial advice. Use at your own risk.

An autonomous AI-powered trading bot built for US stock markets, using a LSTM model to generate buy/sell signals from real-time technical indicators. Originally developed for the RNCP37827 – AI Developer certification ([France Compétences](https://www.francecompetences.fr/recherche/rncp/37827/)).

---

## Description

Started in early 2025, PiggyBank is a self-taught first attempt at building a quantitative trading strategy combining rule-based signal detection and deep learning.

The bot autonomously manages intraday positions on US stocks, using a LSTM model to generate buy signals from real-time technical indicators.

> **Note:** This repository contains the original version submitted for the RNCP37827 certification. A major rewrite is currently in progress as part of a dissertation project.


**Key results (backtested on paper trading):**

| Metric | Rule-based only | With LSTM |
|---|---|---|
| Number of trades | 148 | 702 |
| Win rate | 35.8% | 63.2% |
| Total PnL | -23.61 | +12.28 |
| Max loss | -5.73 | -0.91 |

---

## Model Details

- **Architecture**: LSTM (Long Short-Term Memory)
- **Market**: US stocks (via Alpaca API)
- **Timeframe**: 1-minute bars
- **Input**: 30-minute rolling window of OHLCV + technical indicators (RSI, MACD, EMA50/200, Bollinger %B, ADX, OBV, ATR, CCI, StochRSI)
- **Output**: 3 classes — Buy / Hold / Sell (predicted 3 minutes ahead)
- **Framework**: TensorFlow / Keras

---

# Getting Started

## Dependencies

- Python 3.11
- An [Alpaca Markets](https://alpaca.markets/) account (for live/paper data)

See `requirement.txt` for the full list. Key libraries: `tensorflow`, `pandas`, `numpy`, `pandas-ta`, `scikit-learn`, `sqlalchemy`, `matplotlib`.

---

## Authors

* [@Alexandre Puiseux](https://github.com/AlexandrePuiseux65)

---

# Next Steps

- **Major rewrite** — full rework of the bot architecture as part of a dissertation project (in progress)
- Fix overfitting issues identified in the current LSTM model
- Unlock the full prediction range — the current model was intentionally conservative (BUY signals only, no SELL/SHORT) and misses many potential opportunities

---

# Acknowledgments

## References
> Alpaca Markets — *Market Data API documentation*  
> https://alpaca.markets/

> XTB — *Trading strategy formation*  
> https://www.xtb.com/

> Stack Overflow — Various implementation questions