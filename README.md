# Institutional USD/SGD Cross-Currency Basis & Synthetic Funding Engine

A production-grade, multi-curve quantitative structuring toolkit designed to evaluate cross-currency basis arbitrage between USD (SOFR) and SGD (SORA). Built for institutional Treasury advisory, front-office structuring, and desk-level risk diagnostics.

## 🚀 Key Architectural Features

1. **QuantLib Piecewise Yield Curves**: 
   - Constructs true piecewise log-linear discount curves using OIS rate helpers, deposit helpers, and swap rate helpers across liquid maturity pillars (1M to 5Y).
   - Eliminates legacy flat-rate approximations in favor of rigorous multi-curve discounting mechanics.

2. **Instrument-Level Cash-Flow Schedule Pricing**: 
   - Instantiates formal QuantLib swap schedules and prices forward-starting cross-currency basis swaps via `DiscountingSwapEngine`.
   - Projects cash flows and discount factors directly from bootstrapped term structures.

3. **Counterparty Credit Risk (CVA) & Frictions**: 
   - Incorporates Credit Value Adjustment (CVA) modeling based on expected positive exposure (EPE) profiles and counterparty probability of default (PD).
   - Accounts for execution frictions, dealer bid-ask spreads, and amortized structuring fees.

4. **Mark-to-Market (MTM) Stress Testing**: 
   - Simulates portfolio MTM impact under sudden basis-widening shocks (e.g., +15 to +30 bps) to evaluate collateral requirements and daily variation margin (VM) risks under ISDA/CSA bilateral agreements.

---

## 🛠️ Tech Stack
* **QuantLib (Python Bindings)**: Core quantitative finance engine for curve bootstrapping and instrument pricing.
* **Streamlit**: High-performance interactive web dashboard for front-office analytics.
* **Plotly**: Dynamic multi-curve term structure visualization.
* **Pandas / NumPy**: Vectorized financial calculations and structuring memo generation.

---

## 💻 Local Installation & Execution

1. **Clone the repository**:
   ```bash
   git clone [https://github.com/FinanceGeek-Creator/usdsgd-basis-calculator.git](https://github.com/FinanceGeek-Creator/usdsgd-basis-calculator.git)
   cd usdsgd-basis-calculator