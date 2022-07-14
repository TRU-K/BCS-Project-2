# **DISCLAIMER!**
#### **This content is for informational purposes only, you should not construe any such information or other material as investment, financial, or other advice. Nothing contained within this repo constitutes a solicitation, recommendation or endorsement.**
# Project-2 Machine Learning

---
## ALGO TRADING PROJECT
![Heading](https://user-images.githubusercontent.com/101629699/178955542-78f4b763-140f-4d06-b07b-a26e7bac8d18.PNG)
### Table of Contents
- [Group Members](#Group-Members)
- [Introduction](#Introduction)
    * [Why Use Machine Learning For Trading?](#Why-Use-Machine-Learning-For-Trading?)
    * [Our Goal](#Our-Goal)
    * [The Process](#The-Process)
- [How To Use This Project](#How-To-Use-This-Project)
   * [Dependencies/Libraries](#Dependencies/Libraries)
   * [Adjust To Your Needs](#Adjust-To-Your-Needs)
- [Conclusion](#Conclusion)
   * [How Well Did The Model Perform?](#How-Well-Did-The-Model-Perform?)
   * [Things We Could Improve on Given Time](#Things-We-Could-Improve-on-Given-Time)
---
### Group Members
 - Kurt Cullerton - @TRU-K
 - Anita Januszek - @Mleczkow71
 - Matthew Lewis - @ML789

---

### Introduction
##### Why Use Machine Learning For Trading?
By developing a strong and accurate Machine Learning model, it can assist in making profitable trades that are based off of objective Technical Analysis rather than the biased emotional decisions of a human trader. A Machine Learning model that makes automated trades is also much fasterand efficient than a human trader could ever be. It provides an oppotunity to fine tune the approach based on set of variables (external macro : economic condition or internal related to the market behaviour), simulation runs and model scenario outputs or standard metrics ROCE, Sharpe or Sortino Ratios. 
##### Our Goal
To begin this project we established a goal of creating a sophisticated Machine Learning model that gives accurate and profitable trading signals. Using this Data we aimed to determine which sectors in he US stock market are the most profitable during the current economic downturn, hence provide a hedge against infaltionary / volatile condistion. 
##### The Process
(![Flow chart](https://raw.githubusercontent.com/TRU-K/Project-2/main/Images/Updated_Flow_chart.png)
After deciding on our goal for this project we:
 - Collected all required data using yfinance api. We collected data on the 25 US market sector ETF's.
 - Created a target datset that consisted of a 'Signal', buy or sell. We have experimented with various modles, focusing on Bollinger bands and EMA. In the end EMA produced more accurate results, hence for the futher modelling we used EMA. 
 - This 'Signal' was determined using an EMA cross strategy with optimisation of the parameters and lag to produce the most optimal points to buy and sell.
 - We engineered our features data by adding some trading indicators that are commonly used in the world of technical analysis. This was completed using a new library we have not covered in class called, TA-lib (Technical Analysis Library). To keep things simple we decided to only include, [CCI](https://www.investopedia.com/terms/c/commoditychannelindex.asp) (Commodity Channel Index), [ATR](https://www.investopedia.com/terms/a/atr.asp#:~:text=The%20average%20true%20range%20(ATR)%20is%20a%20market%20volatility%20indicator,to%20all%20types%20of%20securities.) (Average True Range), [RSI](https://www.investopedia.com/terms/r/rsi.asp) (Relative Strength Index) and [MACD](https://www.investopedia.com/terms/m/macd.asp) (Moving average convergence divergence)
 - Built our 2 models using our refined feature and target datasets.
 - Created a dashboard that contains evaluation metrics of both models and compare how they performed.
##### Troubles Experienced
Throughout this project some troubles we experienced were:
 - Implementing limited historical data into our machine learning models.
 - Working with a multi level dataframe, i.e. nested columns.
 - Delegating and completing tasks within a short and restricted time frame.
 - Finding a new model that is simple enough to understand and implement within the time period given for this project.

---

### How To Use This Project
##### Dependencies/Libraries
TO be able to implement and use this code there are some dependencies that will first need  to be installed. These include:
 - TA-lib which can be installed using, conda install -c conda-forge ta-lib, in anaconda prompt (This cannot be !pip installed)
 - plotly (!pip install plotly)
 - panel (!pip install panel)
 - yfinance (!pip install yfinance)
 - hvplot (!pip install hvplot)
 - sklearn (!pip install sklearn)
 - tensorflow (!pip install tensorflow)
 - numpy (!pip install numpy)
 - BernoulliNB Classifier from Naive Bayes library
##### Adjust To Your Needs
To use this Project you will need to access the 'internal_metrics_pulling.ipynb' and adjust the tickers to meet your requirements. Then you will need to run the following code ipynb's in order:
1. internal_metrics_pulling.ipynb
2. feature_engineering.ipynb
3. Returns_Optimiser.ipynb
4. ML_model_code.ipynb
6. dashboard.ipynb

---
### Results 
- EMA provided better returns vs. comparable classifiers models, particularly Naive Bayes
![Return](https://user-images.githubusercontent.com/101629699/178720888-69370567-40cf-4855-8427-a4a1285f09a3.png)
![Random Forest vs Naive Bayes](https://user-images.githubusercontent.com/101629699/178721232-2533883d-93cb-4e5c-9cc9-32b18bd8d12a.png)
![balanced accuracy score](https://user-images.githubusercontent.com/101629699/178723281-15b31a2b-8cac-4e73-a957-143d13844226.png)

![Bollinger Bands Outputs](https://user-images.githubusercontent.com/101629699/178721808-2917b2a2-3e9b-490c-a816-90efd45e6cdf.PNG)
![EMA Outputs](https://user-images.githubusercontent.com/101629699/178722062-5441fc0d-b2c4-4d92-9e1f-ac1a996a741c.PNG)

### Conclusion
##### How Well Did The Model Perform?
- On the agrregate level the model has produced high accuracy score of 0.90. This has less pronounced on individual index levels , with number of smaller indexed producing less accurate results. 
- Precission: out of two ML models, random forest has proven to be more relaible: producing both higher precission  and recall .

SWOT analysis illutrates the final conclussions. 

![SWOT](https://user-images.githubusercontent.com/101629699/178719336-e83d8c7c-b034-4ad9-85a4-4857d6218555.PNG)


##### Things We Could Improve on Given Time
1. Create a more streamlined approach as to how our code works by creating a single .ipynb that will run through all of our seperate code and give outputs accordingly
2. Given time we could look at implementing an automated trading bot based on our machine learning models. This could have been accomplished by creating an SQL database that can be fed real time data and indicators on given data when the trader would like to run their bot. Which from this database feeds a machine learning model to give a signal to, buy sell or hold, based on the most recently given data.

#### Dashboard 
For easy result references
![Dashboard](https://user-images.githubusercontent.com/101629699/178955890-327e94a5-da16-44a5-b6ec-3ebfbb97b2e9.PNG)

### Prediction capabilities
- we have explore predictive appliction of the simulation s/ models used. 
One option is applying time series , second an example below: 
This is a code that predicts next day price , hence future buy / sell signals. 
![Predictions_Code](https://user-images.githubusercontent.com/101629699/178956333-7cd55ea0-cbd8-43af-9958-b3ac81e07c76.PNG)

---
