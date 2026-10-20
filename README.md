# Nvidia-stock-curiosity
A time series project in Python that tests whether NVDA's last 5 days of returns can predict tomorrow's return.
## Data
- Source: Yahoo Finance, using the yfinance Python package
- Stock: NVDA (Nvidia)
- Dates: Jan 2000 – Dec 2025 
- Downloaded: [date]
## Method
1/ Returns: Turned daily prices into daily log returns (prices trend up over time, returns don't).

2/ Explored: Plots, histogram, ACF plot, ADF test, % of up days.

3/ Features:
- Returns from the last 5 days
- 20-day volatility (how much the price moved recently)
- 20-day trend (sum of the last 20 returns)

4/ Target:
- Number: tomorrow's return
- Up/down: 1 if tomorrow's return > 0, else 0

5/ Split by time (no random split, to avoid using the future):
- Train 2000-2015: fitting model
- Validation: Choosing the best model
- Test (2024-2025): final score, used once

6/ Model:
- Baseline: always 0 (always up)
- Linear regression (OLS): Logistic regression (up=1, down=0)
- AR model:
  + K-nearest neighbors (KNN)

  + Support vector machine (SVM)
  
  + Random forest
  
7/ Limits: 
- Only uses past prices. No news, earnings, or other data.
- Daily returns are very noisy, so small results may be luck.
- Many models were tried on the validation set, so the best one may look better than it really is. The test set is the honest score.
- No trading costs included.
- The AI boom changed how NVDA behaves, so the past may not match the future

8/ Structure:

├── data/

│   └── NVDA.csv

├── images/

│   └── model_vs_baseline.png

├── notebooks/

│   └── nvda_returns.ipynb

├── PLAN.md

└── README.md
