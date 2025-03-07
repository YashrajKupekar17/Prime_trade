# Binance Trade Data Analysis

## Overview
This project analyzes Binance trade data over a **90-day period** to evaluate the performance of **150 unique trading accounts**. By computing key financial metrics and employing advanced feature engineering and ranking algorithms, we identify the **top 20 accounts** based on their trading performance.

## Objectives
- Assess Binance trading accounts using key performance metrics.
- Rank accounts based on **Return on Investment (ROI), Profit and Loss (PnL), Sharpe Ratio, Maximum Drawdown (MDD), Win Rate, and Win Positions**.
- Provide insights into trading behavior and risk management.
- Deliver actionable recommendations for portfolio optimization.

## Dataset
The dataset consists of trade histories for **150 unique Port_IDs**. It includes details like:
- **Trade_History** (timestamps, symbols, trade sides, and positions)
- **Price & Quantity** (trade values, realized profits, fees)
- **Timestamps** (tracking market trends over time)

## Key Metrics Computed
1. **Return on Investment (ROI)** – Measures profitability relative to initial investment.
2. **Profit and Loss (PnL)** – Total realized gains and losses.
3. **Sharpe Ratio** – Risk-adjusted return measure.
4. **Maximum Drawdown (MDD)** – Largest drop from peak equity.
5. **Win Rate** – Proportion of profitable trades.
6. **Win Positions** – Number of winning trades.
7. **Total Positions** – Total trades executed.

## Methodology
The analysis is divided into four phases:

### 1. Data Exploration and Cleaning
- Loaded trade history data as a Pandas DataFrame.
- Checked and filled missing values appropriately (mean imputation for price/quantity, zero for fees and profits).
- Converted timestamps to datetime format and sorted data chronologically.

### 2. Exploratory Data Analysis (EDA)
- **Descriptive Statistics:** Mean, median, and standard deviation of key attributes.
- **Price Distribution:** Histograms and KDE plots.
- **Trend Analysis:** Trading activity fluctuations over time.
- **Correlation Analysis:** Identified relationships between trade features using a heatmap.

### 3. Feature Engineering
New features were created to enhance analysis:
- **trade_type**: Categorized trades into `BUY_LONG`, `SELL_SHORT`, etc.
- **trade_value**: Computed as `price × quantity`.
- **Portfolio Metrics:** Total volume, avg. trade profit, Sharpe Ratio, MDD, and win rate.

### 4. Ranking Algorithm
- **Normalization:** Standardized metrics using `StandardScaler`.
- **Scoring System:** Composite score using weighted metrics.
  - `total_volume`: 40%
  - `win_positions`: 10%
  - `avg_trade_profit`: 10%
- **Ranking:** Accounts were sorted in descending order of the composite score.

## Key Findings
- **Market Trends:** Activity spikes correlate with market events.
- **Top-performing accounts:** High Sharpe ratios, low MDD, and win rates >70%.
- **Feature Importance:** `total_volume`, `win_positions`, and `avg_trade_profit` are the strongest predictors of ROI.

## Future Improvements
- **Optimize Score Weights:** Adjust ranking methodology based on further validation.
- **Expand Analysis:** Apply methodology to longer timeframes or additional datasets.
- **Real-Time Monitoring:** Build dashboards for dynamic tracking of trading performance.

## Deliverables
1. **Jupyter Notebook** – Full scripts for data cleaning, analysis, and ranking.
2. **portfolio_metrics.csv** – Detailed account metrics.
3. **top_20_accounts.csv** – Ranked list of the top trading accounts.
4. **Report** – Comprehensive document summarizing the analysis.

## Installation & Usage
1. Clone the repository:
   ```sh
   git clone https://github.com/yourusername/binance-trade-analysis.git
   ```
2. Install dependencies:
   ```sh
   pip install -r requirements.txt
   ```
3. Run the analysis:
   ```sh
   jupyter notebook
   ```
4. Open `binance_trade_analysis.ipynb` and execute cells.

## Contributing
Contributions are welcome! Feel free to submit issues or pull requests.

## License
This project is licensed under the MIT License.

---
*For further details, check out the full report in this repository.*

