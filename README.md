# Project-2: Algorithmic Trading (Ethereum)
## Team 2 members: Alpha, Dmitry, Justin, Ravi
---

# Summary of Project:
The project we chose to do was a machine learning trading bot that uses various forms of technical analysis as well as supervised and unsupervised learning to attempt to generate a profitable trading strategy. The goal was to see which person would be able to create the most profitable strategies. We ran these strategies on Ethereum and to begin we first had to get the open, high, low, close, and volume data (ohlcv). To do this, we used the Binance API and created a for loop that appended each data point into its own list and then turned those lists into seperate dataframes and concatenated them.

---
# Justin's Strategy:
Justin's strategy made use of the technical analysis library finta and used the AO function which is called the 'awesome oscillator' which is a type of momentum indicator. The strategy was relatively simple with whenever the AO indicator went negative - showing downward momentum, we would sell ETH and whenever it went positive, we would buy ETH. The data was then split into training and testing data with the AO data being the feature(x) and the trading signal being the label (y). A logistic Regression model was used and after getting our predictions, we were left with an accuracy score of 96%. The annualized return of the strategy was 86%, and with a starting capital of $200,000 the strategy ended with a portfolio total of $1,150,515.

---
# Alpha's Strategy:
Alpha's strategy made use of unsupervised learning to decide his buy/sell signals. Alpha constructed an elbow plot and created a Kmeans model on the data using the closing prices, volume, and pct change. After running the model, it showd that a drawdown of ~2% was higher than only 25% of the distribution of returns, and a increase of ~3% was higher than 75% of the distribution of returns. The trading strategy was then formed to be contrarian, with a buy signal whenever there was a drawdown >2% and a sell signal whenever there was an increase in price >3%. Backtesting the strategy revealed a total portfolio value of $2,672,060 after a $200,000 investment originally. A logistic regression model was then used along with a Deceision tree which both yielded accuracy scores of 99%.

---
# Dmitry's Strategy:
Dmitry's strategy used a 4 day short window and 200 day long window of moving averages. The signal to buy and sell was based on positive and negative returns daily. After seperating the training and testing data, a support vector machine model was used to create predictions. The accuracy of these predictions was 45% compared to the signals created. Overall, this strategy ended up losing money from the initial $200,000 investment.

---
# Ravi's Strategy:
Ravi ran a model that was based on using unsupervised learning and a Kmeans model. The model was fitted using the closing prices and pct change. The strategy was similar to Alpha's with a buy signal when ETH went down >2% and a sell signal when it went up more than 2.8%. This strategy produced a 2.5x return roughly. A second strategy was created using the 50 day and 200 day moving average. If the 50 day MA crossed over the 200 day MA and the price change was positive that day, it indicated a buy signal. This provided a cumulative return of nearly 5x. 

---
# Summary
Overall, we were able to create some profitable strategies using both supervised and unsupervised learning as well as techincal analysis. The most profitable strategies were Ravi's 5x strategy and Alphas strategy based on using unsupervised learning percentiles for buy/sell signals. 

