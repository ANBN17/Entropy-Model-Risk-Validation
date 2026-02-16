# Entropy-Model-Risk-Validation

Entropy-Based Model Risk Validation
Credit Spread Stress Testing (2020–2025)

This repository contains an independent validation of a relative-entropy (exponential tilting) framework applied to credit spread proxy losses (HYG–LQD differential).

Objective

To evaluate:

Theoretical soundness of entropy-based robustness

Sensitivity to robustness parameter (θ)

Empirical behavior across macro regimes

Forward-looking conservatism via backtesting

Governance implications for Model Risk Management (MRM)

Key Findings

Entropy interpolates smoothly between mean and tail risk.

Around θ ≈ 9–10, losses approximate CVaR behavior.

Static θ underestimates forward stress.

Dynamic calibration and governance controls are essential.

Charts Included

Entropy-Tilted Expected Loss vs Theta

Entropy vs VaR vs CVaR

Rolling Backtest: Entropy vs Realized Stress

Tools Used

Python (NumPy, Pandas, Matplotlib)

Market data (Yahoo Finance proxies)

Rolling backtesting methodology
