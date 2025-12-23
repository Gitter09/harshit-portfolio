# Financial Engineering & Institutional Valuation Workbench

![Python](https://img.shields.io/badge/Python-3.9+-3776AB?style=flat&logo=python&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-Web_Framework-000000?style=flat&logo=flask&logoColor=white)
![Financial Engineering](https://img.shields.io/badge/Domain-Stochastic_Calculus_%26_Statistical_Arbitrage-blue)

> **⚠️ Note on Proprietary Source Code:** The core logic for this platform (including the Heston Stochastic Volatility solver, Pairs Trading cointegration engine, and Reverse-LBO solver) is proprietary. This repository serves as a technical documentation hub. **Full source code access is available for audit upon request.**

**Live Demo:** [www.harshit-portfolio.me](https://www.harshit-portfolio.me)

---

## System Architecture: Hybrid Computational Engine
This platform bridges the gap between raw market data and the "Adjusted" reality of institutional finance. It implements asynchronous data lifecycles to solve the latency issues of real-time financial modeling.

![System Architecture Blueprint](architecture_diagram.png)
*Figure 1: High-level architectural data flow from raw API ingestion to automated model generation.*

### Key Architectural Features:
* **Parallel Fetching Engine:** Implements `concurrent.futures.ThreadPoolExecutor` for asynchronous data ingestion, reducing peer-group latency by ~85%.
* **Stateful Manual Overrides:** Custom JS engine allowing real-time overrides of LTM EBITDA and Net Debt with instant valuation bridge recalculation.
* **Audit-Ready Excel Export:** Generates professional models via `XlsxWriter` using live Excel formulas and standard IB formatting conventions.

---

## Proprietary Toolset

### 1. Stochastic Options Lab (Advanced Derivatives)
**The Problem:** Black-Scholes assumes constant volatility, failing to capture the "Volatility Smile."
**The Solution:** A dual-engine workbench that contrasts standard GBM with Stochastic Volatility models.

![Options Analysis Dashboard](new_options_heatmap.png)
*Figure 2: Options Analytics interface featuring real-time Greeks sensitivity and Heston model path simulations.*

* **Heston Model Integration:** Implements the Heston SDE using Euler-Maruyama discretization to model the "Leverage Effect" (negative correlation between price and volatility).
* **Higher Moment Analysis:** Calculates **Skewness** and **Excess Kurtosis** to identify "Fat Tail" risks and non-normal distribution patterns in underlying assets.
* **Monte Carlo Convergence:** Simulates 5,000+ paths to calculate Probability ITM and Fair Value under stochastic conditions.

### 2. Statistical Arbitrage (Pairs Trading) Lab
**The Problem:** Correlation is not Cointegration. Two assets can move together but drift apart forever.
**The Solution:** An econometrics engine that identifies stationary spreads for mean-reversion trading.

![Pairs Trading Interface](INSERT_YOUR_PAIRS_TRADING_IMAGE_HERE)
*Figure 3: Cointegration analysis dashboard showing Z-Score signals and ADF test stationarity metrics.*

* **Cointegration Testing:** Utilizes the **Augmented Dickey-Fuller (ADF) Test** to verify the stationarity of the spread residuals.
* **Dynamic Hedging:** Calculates the Hedge Ratio ($\beta$) via OLS Regression to construct a market-neutral synthetic asset.
* **Z-Score Signal Generation:** Normalizes spread deviations to identify entry/exit points at $\pm2\sigma$ thresholds.

### 3. Leveraged Buyout (LBO) & Valuation Engine
* **Reverse LBO Logic:** Back-solves for the **Sponsor Floor** (Max Entry Price) required to hit specific IRR/MOIC targets.
* **Sensitivity Matrix:** Generates real-time 5x5 heatmaps of Implied Max Entry EV relative to exit multiples and leverage tranches.

![LBO Sensitivity Matrix](lbo_dashboard.png)
*Figure 4: 5x5 Sensitivity Matrix visualizing Sponsor Floor valuation across varied leverage and exit assumptions.*

### 4. NSE Portfolio Optimizer
* **Modern Portfolio Theory (MPT):** Constructs Efficient Frontiers using Mean-Variance Optimization and Hierarchical Risk Parity (HRP).
* **Bayesian Shifting:** Features a Black-Litterman style "User Views" adjustment for historical return distributions to match future expectations.

![Efficient Frontier Visualization](efficient_frontier.png)
*Figure 5: Plotting the Efficient Frontier for NSE stocks to maximize Risk-Adjusted Returns (Sharpe Ratio).*

### 5. Quantitative Risk Estimator (VaR)
![Risk Dashboard](risk_dashboard.png)
*Figure 6: Monte Carlo Simulation (first 50 paths) visualizing tail-risk distribution and Value at Risk (VaR) thresholds.*
* **Tail Risk Metrics:** Calculates **Value at Risk (VaR)** and **Expected Shortfall (CVaR)** at 95% and 99% confidence intervals.
* **Stochastic Stress Testing:** Projects price paths via Monte Carlo to stress-test portfolios against "Black Swan" events.

### 6. Valuation Sandbox
* **Interactive DCF:** Real-time sensitivity sliders for WACC, Terminal Growth, and Revenue projections to test fundamental investment theses.

---

## Tech Stack
* **Backend:** Python (Flask), `statsmodels` (Econometrics), `SciPy` (Stats & Optimization)
* **Computational:** `Pandas`, `NumPy`, `skfolio` (Portfolio Optimization)
* **Visualization:** `Plotly.js` (Interactive Financial Data Visualization)
* **Frontend:** Tailwind CSS, Vanilla JavaScript (Async Data Lifecycle Management)

---

## Academic Foundation & Acknowledgments
This project is built upon foundational principles of Financial Engineering and Quantitative Analysis.

**Special Thanks to:**
* **Prof. Byomakesh Debata** & **Prof. Aditya Sharma** for foundational lectures on **Risk Analysis** and Institutional Valuation.
* **Academic Peer Review:** My deep gratitude for the guidance on Stochastic Processes and Time-Series Econometrics that validated the underlying mathematical models.

## Contact & Professional Inquiries
**Harshit Singh** | [LinkedIn](https://linkedin.com/in/harshit-singh-502246214/) | [Email](mailto:harshitsingh4907@gmail.com)
