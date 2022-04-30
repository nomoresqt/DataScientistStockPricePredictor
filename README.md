# Data Scientist Capston Project Financial Asset price Predictor

###
This project is the capstone project of Udacity Data Scientist nano-degree. For this project, I built a model to predict financial assets  prices(stock, ETF, Digital currency .etc). My personal professional background is in Finance and Investments. One of the reasons why I’m learning Data Science is to utility this powerful tool in the financial sector. The modern  Financial sectors consumers and generate enormous amount of date on daily basis. More than 90% of the daily trading volume of the major stock exchanges are conducted by computer program and algorithms. Machine learning and deep learning have become an essential tool for automate complicated trading decision making and trade execution process.  

In this project, I’m using LSTM model to predict stocks/ asset price a day in the future. Long short-term memory model( LSTM) is a RNN ( Recurrent Neural Networks) architecture. How RNNs works are analogous to the learning process of humans, just like us, it remembers some useful information from the past (feedback connection) and forget some none important information. RNNs can only loop back and get previous information from the recent timeframe,  but LSTMs can retains past information from the longer timeframe. Thus, LSTMs are extremely effective tool for sequence prediction problems. Since LTSM has feedback connection, it’s good at processing sequential of  historical data, such as : historical financial asset prices.


### The Blog Post of this project can be found via the following link
https://lululastudio.com/stockpricepredictor/2021/12/28/stock-price-predictor-udacity-data-scientist-capstone-project

### Libraries used in this project

* yfinance 
* pandas 
* numpy 
* datetime 
* matplotlib
* math 
* sklearn
* tensorflow 

### Data Source 

Yahoo Finance API, downloaded via yfiance library 
Note: Yahoo has deprecated their API, but you can still download data via yfinance 
yfinance documentation: https://pypi.org/project/yfinance/

### In this Repository 

* a Jupiternotebook file which contians all the code
* model.h5: trained model 
* model_updated.h5: updated model after adding 50 more neurons
* downloaded_data.csv: the orignal dataset that I've downloaded via yfinance
* final_prediction.csv: the final dataset that contians model prediction

### Sections in this project 

* DOWNLOAD AND CLEAN THE DATA
* DATA EXPLORATION AND SIMPLE MOVING AVERAGE STRATEGY 
* BUILD AND TRAIN  LONG SHORT-TERM MEMORY MODEL 
* EVALUATE THE MODEL’S ROBUSTNESS AND  PREDICT OTHER  FINANCIAL ASSET PRICE



### The main conclusion in this project 
#### SMA strategy performance: 
* Blue Line: the cumulative return of the defined time period ( A simple buy and hold strategy)
* Orange Line: Simple Moving Average(SMA)strategy's return
* As you can see below, Given almost the same annulized volatilities, SMA strategy outperformed the "buy and hold" benchmark.
![performance of Simple Moving Average Strategy](https://images.squarespace-cdn.com/content/v1/5c193daf2971144ee8c71ea6/04db2290-2d18-4426-9200-89ba4355218a/download+%281%29.png?format=2500w)



#### LSTM model prediciton

The following plot showed the trained model and its prediction. The blue line is training data, and prediction is in green line. The actual price that we used for validation is in color orange.  As we can see from the plot below, our model works reasonable fine. The predicted price followed actual price rather well, only slightly higher in most of the cases. The value of RMSE is : 16.0173.
![performance of model](https://images.squarespace-cdn.com/content/v1/5c193daf2971144ee8c71ea6/163d4c52-74a4-42f7-b4a7-2ad0779c47ec/download+%284%29.png?format=2500w)


#### ONCLUSION AND POSSIBLE IMPROVEMENTS

THe model does reasonably well when predicting the financial instruments in the same asset class and sector, that is : tech stock (equity).  

The model does not perform well when predicting the price of Bitcoin which is a in totally different asset class. In financial sector, there are many assets classes, such as Fixed Income( Bonds), Equity(stocks), Currency(Forex), Digital Assets.  Different asset classed exhibit different price movements patterns, due to the fact that prices of those assets are determined on different factors. If you are trading or invest in one particular financial instrument , it’s better to train the model consistently with the same asset class and re-train the model if you wish to predict the price of another instrument from different sector or assets class. 

To summaries, the LTSM  along is just too simply to forecast stock price, and trader&investor should definitely not trade according to the predictions. Financial market is an extremely complicated system, forecasting price movements is as difficult as forecasting weather. There are many factors can introduce dramatic changes of stock price. Use one model to predict and generate single for trading or investment decision is rather dangerous. Sometimes, It’s better to combine the results of different models. For example, utilize NLP sentiment analysis to evaluate the market sentiment, if the market sentiment is bearish and LTSM prediction also shows price drop, then we short-selling the stock; if the market sentiment is bullish and LTSM prediction also shows price increase, then we long the stock. 


REFERENCE
* Python for finance by Yves Hilpisch https://www.oreilly.com/library/view/python-for-finance/9781492024323/

* Time Series - LSTM Model https://www.tutorialspoint.com/time_series/time_series_lstm_model.htm

* Short-term stock market price trend prediction using a comprehensive deep learning system by Jingyi Shen & M. Omair Shafiq https://journalofbigdata.springeropen.com/articles/10.1186/s40537-020-00333-6

* P516, Hands-on Machine Learning with Scikit-Learn, Keras & TensorFlow by Aurelien Geron 
