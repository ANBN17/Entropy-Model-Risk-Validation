# Entropy-Based Model Risk Validation (Stress Testing) — 2020–2025

This repo contains an independent **Model Risk / Model Validation** exercise that tests an **entropy-based (exponential tilting)** framework for robust stress measurement on **credit spread proxy losses** (HYG–LQD).  
The goal is to evaluate **theoretical behavior, sensitivity to the robustness parameter (θ), stability across regimes, and forward-looking conservatism** (backtest) — aligned with typical **MRM validation** expectations.

---

## 1) What this project does

Using daily market proxies (Yahoo Finance):

- **Credit stress proxy:** `HYG - LQD` (HY underperformance vs IG during stress)
- **Equity proxy:** `SPY`
- **Rates proxy:** `TLT`
- **Vol proxy (optional):** `^VIX`

We compute loss series (positive = worse) and apply **entropy tilting**:

\[
E_\theta[L] = \frac{\sum_i L_i e^{\theta L_i}}{\sum_i e^{\theta L_i}}
\]

where:
- `L` = loss observations
- `θ` = robustness parameter (higher θ → more tail emphasis)

---

## 2) Validation questions answered (MRM style)

This repo demonstrates:

- **Benchmarking:** How entropy-adjusted loss compares to **Mean / VaR(99%) / CVaR(99%)**
- **Sensitivity & Fragility:** How loss grows with θ and where amplification becomes nonlinear
- **Regime Stability:** Whether results are stable across macro subperiods (2020–21, 2022–23, 2024–25)
- **Backtesting:** Whether entropy estimates are conservative vs realized forward stress (rolling 2Y train → 1M test)

---

## 3) Key outputs (charts)

The code produces the following PNG charts in `figures/`:

1. `entropy_vs_theta.png`  
   **Entropy-Tilted Expected Loss vs θ** (shows convex amplification)

2. `entropy_vs_var_cvar.png`  
   **Entropy vs Mean / VaR(99%) / CVaR(99%)** (benchmark comparison)

3. `stability_across_regimes.png`  
   **Regime stability** across subperiods

4. `backtest_entropy_vs_realized.png`  
   **Backtest:** entropy prediction vs realized next-month maximum loss

5. `rolling_corr_vs_spy.png` *(optional)*  
   **Rolling correlation regime shifts** vs SPY

---

## 4) Repository structure

Recommended structure:

