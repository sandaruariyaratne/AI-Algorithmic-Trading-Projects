# Quantitative Trading & Machine Learning Systems

A portfolio of production-grade algorithmic trading systems, quantitative research frameworks, and machine learning models engineered for cryptocurrency and financial markets.

Featuring event-driven asynchronous architectures, regime-specialized ensemble learning, dynamic volatility-adjusted risk governance (Triple Barrier Method), and exchange integrations via CCXT.

---

## 🚀 Projects Overview

| Project | Primary Model | Market Focus | Key Highlights |
| :--- | :--- | :--- | :--- |
| **[3Trend Trader](#1-3trend-trader--multi-regime-event-driven-trading-engine)** | LightGBM Ensemble | Crypto (1m Klines) | Multi-regime routing (ADX/DI), Triple Barrier Method, AsyncIO Event Bus, GCP/Docker |
| **[ATR Trader LightGBM](#2-atr-trader--volatility-adaptive-lightgbm-system)** | LightGBM Classifier | Crypto / Equities | Volatility-adaptive ATR barriers, walk-forward validation, dynamic risk-to-reward |
| **[TradingBot XGBoost](#3-tradingbot-xgboost--automated-ml-signal-engine)** | XGBoost Gradient Boosting | Spot / Futures | Indicator engineering, Bayesian hyperparameter tuning, probability-calibrated signals |

---

## 📌 Projects

### 1. 3Trend Trader — Multi-Regime Event-Driven Trading Engine

An asynchronous, low-latency algorithmic trading platform engineered for 1-minute cryptocurrency markets on Binance. The system addresses non-stationarity in financial time-series by dynamically decomposing market states into distinct regimes and routing inference to specialized machine learning models.

* **Multi-Regime Routing**: Real-time Wilder's ADX ($ADX_{14, 21}$) and Directional Movement ($\pm DI$) classify market states into **Uptrend**, **Downtrend**, or **Sideways**, dispatching features to regime-specialized LightGBM classifiers.
* **Microstructure Feature Pipeline**: Scale-invariant feature synthesis extracting Taker Order Flow Imbalance (TOFI), Tick Volume Imbalance (TVI), Whale Participation Factor, multi-horizon rolling VWAP deviations, and candle geometry without look-ahead bias.
* **Triple Barrier Risk Governance (TBM)**: Implements Marcos López de Prado’s Volatility-Adjusted Triple Barrier Method with dynamic $k \times \text{ATR}$ take-profit/stop-loss boundaries, a strict **15-candle vertical time horizon exit**, and realistic intra-bar wick breach modeling including 10 bps fee deductions.
* **Architecture & Infrastructure**: AsyncIO-based typed FIFO pub/sub event bus decoupling market data ingestion, feature extraction, inference, and execution. Fully containerized with Docker Compose for automated deployment to Google Cloud Compute Engine.

🔗 **[View GitHub Repository](https://github.com/sandaruariyaratne/3Trend_trader)**

```
Tech Stack: Python 3.10+ • LightGBM • AsyncIO • CCXT • Docker • GCP • Structlog • Pydantic
```

---

### 2. ATR Trader — Volatility-Adaptive LightGBM System

A quantitative algorithmic trading strategy that integrates Average True Range (ATR) dynamic barrier mechanics with LightGBM gradient boosting to achieve volatility-adaptive signal generation and position sizing.

* **Volatility-Adaptive Thresholds**: Replaces rigid static price targets with dynamic ATR-normalized bands that expand during volatile expansions and contract during low-volatility consolidations, preventing false-breakout whipsaws.
* **Machine Learning Classification**: Supervised LightGBM classifier trained on multi-timeframe momentum, trend acceleration, and volatility expansion features to predict the probability of positive forward barrier touches.
* **Robust Walk-Forward Backtesting**: Vectorized backtesting framework incorporating walk-forward out-of-sample cross-validation, transaction fee modeling, and slippage simulation to eliminate survivorship and data-snooping biases.
* **Disciplined Risk Management**: Dynamic position sizing adjusted inversely to ATR volatility to maintain equal portfolio dollar-risk per trade regardless of market regime.

🔗 **[View GitHub Repository](https://github.com/sandaruariyaratne/ATR_Trader_LightGBM)**

```
Tech Stack: Python • LightGBM • Scikit-learn • Pandas • NumPy • Matplotlib • Backtesting
```

---

### 3. TradingBot XGBoost — Automated ML Signal Engine

An end-to-end automated machine learning trading bot powered by Extreme Gradient Boosting (XGBoost) for directional trend forecasting, feature importance interpretation, and automated order execution.

* **Technical Feature Engineering**: Comprehensive technical analysis pipeline extracting features from moving average convergences, Relative Strength Index (RSI), MACD histograms, Bollinger Band widths, and normalized price returns.
* **XGBoost Inference & Calibration**: Bayesian-optimized XGBoost model outputting calibrated class probabilities. High-confidence trade signals are filtered through rigorous entry probability thresholds to maximize win rate and profit factor.
* **Automated Order Management**: Modular execution layer with automated stop-loss and take-profit calculation, tracking open trade lifecycles and logging execution telemetry.
* **Performance Analytics**: Quantitative evaluation suite generating trade-by-trade metrics including Sharpe Ratio, Sortino Ratio, Maximum Drawdown (MDD), Profit Factor, and equity curve visualizations.

🔗 **[View GitHub Repository](https://github.com/sandaruariyaratne/TradingBot_XGBoost)**

```
Tech Stack: Python • XGBoost • TA-Lib / Pandas-TA • Scikit-learn • CCXT • Seaborn
```

---

## 🛠️ Core Competencies Highlighted

* **Quantitative Research**: Regime detection, Triple Barrier labeling, order flow imbalance, stationary time-series feature engineering.
* **Machine Learning**: Gradient boosted decision trees (LightGBM, XGBoost), probability calibration, cross-validation, hyperparameter tuning.
* **Software Engineering**: Asynchronous event-driven systems (`asyncio`), typed data pipelines, thread-safe state management, Docker, GCP cloud hosting.
* **Risk & Portfolio Management**: ATR-based dynamic stops, vertical time timeouts, Kelly criterion, drawdown circuit breakers, slippage/fee accounting.

---

## 📬 Contact & Connect

- **GitHub**: [@sandaruariyaratne](https://github.com/sandaruariyaratne)
- **LinkedIn**: [Sandaru Ariyaratne](https://www.linkedin.com/in/sandaru-ariyaratne)
