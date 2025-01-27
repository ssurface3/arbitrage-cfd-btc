Arbitrage CFD-BTC: Exploring the Infinite Money Glitch
Author: Anatolii Frolov
Project Goal: To explore the potential for arbitrage between Bitcoin (BTC/USD) and its CFD (Contract for Difference) by analyzing price discrepancies and developing a trading strategy.

Project Overview
This project aims to identify and exploit arbitrage opportunities between Bitcoin (BTC/USD) and its CFD counterpart. The goal is to create a riskless strategy with an initial payoff of zero, leveraging mean-reversion and volatility-based models.

Key Steps and Challenges
1. Data Collection
BTC/USD Spot Data:
Collected with 1-second delays using an API. Due to API key issues, the data was manually downloaded.

BTC/USD CFD Data:
Sourced from Dukascopy brokerage. A limitation was the maximum one-day data extraction, which was resolved using a custom library: algogenetic/dukascopy-1.

2. Data Preprocessing
Transformation:
Applied pct_change to the data to introduce mean-reversion properties, which are crucial for the strategy.

Trading Hours Adjustment:
CFDs are traded during Swiss trading hours. Non-trading hours were used to calculate volatility using a variation of T-GARCH (preferred for its risk-neutral properties).

Data Cleaning:
Removed unused hours to align the datasets.

3. Strategy Development
Entry and Exit Points:
Identified using technical indicators:

RSI (Relative Strength Index): Implementation details are provided in the document.

MACD (Moving Average Convergence Divergence): Python and MACD Trading Strategy.

ATR (Average True Range): ATR Trading Strategy in Python.

Model Training:
Used regression to determine the optimal combination of indicators and assigned weights to each.

4. Backtesting
Timeframe:
The model was backtested on data from 2018 to 2021.

Results:
The performance of the strategy was evaluated, and insights were documented.

Tools and Libraries Used
Data Collection:

Dukascopy API wrapper: algogenetic/dukascopy-1.

Data Analysis:

Python libraries: pandas, numpy, statsmodels (for GARCH models).

Technical Indicators:

Custom implementations of RSI, MACD, and ATR.

Backtesting:

Custom backtesting framework.

Results and Insights
The project successfully identified potential arbitrage opportunities, but the "infinite money glitch" remained elusive. Key takeaways include:

The importance of aligning trading hours and adjusting for volatility.

The effectiveness of combining multiple technical indicators for entry and exit signals.

The challenges of achieving a truly riskless strategy in real-world conditions.

Future Work
Expand the dataset to include more recent years.

Explore additional indicators and machine learning models for improved predictions.

Optimize the strategy for lower transaction costs and slippage.

How to Use This Repository
Clone the repository:

bash
Copy
git clone https://github.com/your-username/arbitrage-cfd-btc.git
Install the required dependencies:

bash
Copy
pip install -r requirements.txt
Run the scripts to preprocess data, train the model, and backtest the strategy.
