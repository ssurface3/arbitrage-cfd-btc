# arbitrage-cfd-btc
Tried my best to achieve infinite money glitch in real life- failed miserably
Cfd vs underlying assset
by Anatolii Frolov

Let's explore all the points we need to adress in this project:

We need to scoop up the data
BTC/USD data with the 1s delays
It's easy but requires the api key ( it was ruined , so just downloaded it)
BTC/USD cfd data from dukascopy brokerage
Here we needed to adress the problem of max one day data extraction
It's solved by a library that was written by one guy https://github.com/algogenetic/dukascopy-1
We need to convert with pct_change to be not iid but to contain that sweet mean-reversion that we need
We need to adress the problem of CFD been traded on Swiss trading hours
We can use the unused hours to calculate the volatility for period using variation of garch(preferably t-garch as I want this to be riskless strategy with initial payoff of zero)
We can just delete the extra(unused hours)
We need to introduce the points of entry for the model and exits
Rsi for example (implementation in the document)
MACD https://www.quantifiedstrategies.com/python-and-macd-trading-strategy/
ATR https://www.quantifiedstrategies.com/average-true-range-trading-strategy-in-python/
Teaching the regression on best combo of this two ways of buying -> setting up weights
Backtesting the model on 2018 - 2021
Results
