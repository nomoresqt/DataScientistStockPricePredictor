# Data Scientist Capston Project Financial Asset price Predictor

###
1.1. Project Overview
The modern financial market consumers and generates enormous amount of data on the daily basis. More than 50%-70 of the daily trading volume of the major stock exchanges are conducted by computer programs and algorithms. Machine learning and deep learning have become an essential tool for automate complicated trading decision making and trade execution process. Many financial institutions and professional trader are using the ML and AI to create models that consume real-time data as input and rank stocks or other financial instruments and identify profitable trading and investment opportunities
In this project, I will use Long-Short Term Model (LSTM) to predict financial assets prices by using historical time series data (historical prices) to build and train the model. All dataset of this project were download by using the library Yfinance. Yfinance is a library that download financial data via Yahoo API, even though Yahoo has deprecated its’ old API, yfinance can still download without any issues. With this library, users can download End-Of-Day(daily) price or intraday prices of different interval such as: 1 hour and 15 minutes. For more information, please visit yfinance homepage https://pypi.org/project/yfinance/
The dataset contains 6 columns, and the timestamp as the index
Open,: the price at the open of a trading day
2. Close: the price at the close of a trading day
3. Adj Close: The adjusted closing price amends a stock’s closing price to reflect that stock’s value after accounting for any corporate actions. Such as stock splits.
4. High, the highest price of a trading day
5. Low, the lowest price of a trading day
6. Volume, trading volume
I chose Exchange Traded Index Funds (ETF): Invsco QQQ’s pricing data as the input of model training. The Index includes the 100 largest non-financial companies listed on the Nasdaq based on market cap.” More information see: Inveso QQQ homepage

### The Blog Post of this project can be found via the following link
https://medium.com/@qsong2610/use-lstm-to-predict-financial-asset-price-af751d2db3c4

### Libraries used in this project

* yfinance 
* pandas 
* numpy 
* datetime 
* matplotlib
* math 
* sklearn
* tensorflow 
* plotly
* cufflinks

### Data Source 

Yahoo Finance API, downloaded via yfiance library 
Note: Yahoo has deprecated their API, but you can still download data via yfinance 
yfinance documentation: https://pypi.org/project/yfinance/

### In this Repository 

* a Jupiternotebook file which contians all the code
* model.h5: trained model 
* downloadedDataMulti.csv
* downloaded_data.csv: the orignal dataset that I've downloaded via yfinance

### Plot the data in Candle chart

![performance of Simple Moving Average Strategy](https://miro.medium.com/max/1400/1*4qhAmYQJWnRZ4lh2uAorJg.png)



### The main conclusion in this project 
#### SMA strategy performance: 
* Blue Line: the cumulative return of the defined time period ( A simple buy and hold strategy)
* Orange Line: Simple Moving Average(SMA)strategy's return
* As you can see below, Given almost the same annulized volatilities, SMA strategy outperformed the "buy and hold" benchmark.
![performance of Simple Moving Average Strategy](https://miro.medium.com/max/1400/1*scbsDoqfjrIvHC2QPYx0NQ.png)



#### LSTM model prediciton
The R — Square score is 0.914 which is rather satisfactory. RMSE is 23.336 which is way smaller than the mean (243.92) of testing data. At this stage, I’m comfortable with the performance of the model.
I also plotted the actual price and predicted price (see the plot below).The blue line: training data.The orange line is the actual price.The green line is the prediction that LSTM model made. In most of the time, our predicted price runs slightly higher than the actual price, since the half of 2020, the differences between actual price and predication is getting bigger.


![Model Predicition](https://miro.medium.com/max/1400/1*uHj9ToZOwMpLd4zWlesaww.png)


#### ONCLUSION AND POSSIBLE IMPROVEMENTS



REFERENCE
* Python for finance by Yves Hilpisch https://www.oreilly.com/library/view/python-for-finance/9781492024323/

* Time Series - LSTM Model https://www.tutorialspoint.com/time_series/time_series_lstm_model.htm

* Short-term stock market price trend prediction using a comprehensive deep learning system by Jingyi Shen & M. Omair Shafiq https://journalofbigdata.springeropen.com/articles/10.1186/s40537-020-00333-6

* P516, Hands-on Machine Learning with Scikit-Learn, Keras & TensorFlow by Aurelien Geron 
