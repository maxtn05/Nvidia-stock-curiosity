# Nvidia-stock-curiosity
Do the last 5 days of NVDA returns help predict tomorrow’s return?
## Data
- Source: Yahoo Finance, using the yfinance Python package
- Stock: NVDA (Nvidia)
- Dates: Jan 2000 – Dec 2025 
- Downloaded: [date]
## Method
1/ Returns: Turned daily prices into daily log returns (prices trend up over time, returns don't).
2/ Explored: Plots, histogram, ACF plot, ADF test.
3/ Features:
- Returns from the last 5 days
- 20-day volatility (how much the price moved recently)
- 20-day trend (sum of the last 20 returns)
4/ Split by time (no random split, to avoid using the future):
- Train 2000-2015: fitting model
- Validation: Choosing the best model
- Test (2024-2025): final score, used once
- 
