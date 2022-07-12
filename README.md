# **DISCLAIMER!**
#### **This content is for informational purposes only, you should not construe any such information or other material as investment, financial, or other advice. Nothing contained within this repo constitutes a solicitation, recommendation or endorsement.**
# Project-2 Machine Learning

---

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
By developing a strong and accurate Machine Learning model, it can assist in making profitable trades that are based off of Technical Analysis rather than the biased emotional decisions of a human trader. A Machine Learning model that makes automated trades is also much fasterand efficient than a human trader could ever be.
##### Our Goal
To begin this project we established a goal of creating a sophisticated Machine Learning model that gives accurate and profitable trading signals. Using this Data we aimed to determine which sectors in he US stock market are the most profitable during the current economic downturn. 
##### The Process
After deciding on our goal for this project we:
 - Collected all required data using yfinance api. We collected data on the 25 US market sector ETF's.
 - Created a target datset that consisted of a 'Signal', buy or sell. This 'Signal' was determined using an EMA cross strategy with optimisation of the parameters and lag to produce the most optimal points to buy and sell.
 - We engineered our features data by adding some trading indicators that are commonly used in the world of technical analysis. This was completed using a new library we have not covered in class called, TA-lib (Technical Analysis Library). To keep things simple we decided to only include, [CCI](https://www.investopedia.com/terms/c/commoditychannelindex.asp) (Commodity Channel Index), [ATR](https://www.investopedia.com/terms/a/atr.asp#:~:text=The%20average%20true%20range%20(ATR)%20is%20a%20market%20volatility%20indicator,to%20all%20types%20of%20securities.) (Average True Range), [RSI](https://www.investopedia.com/terms/r/rsi.asp) (Relative Strength Index) and [MACD](https://www.investopedia.com/terms/m/macd.asp) (Moving average convergence divergence)
 - Built our 2 models using our refined feature and target datasets.
 - Created a dashboard that contains evaluation metrics of both models and compare how they performed.
##### Troubles Experienced
Throughout this project some troubles we experienced were:
 - Implementing limited historical data into our machine learning models.
 - Working with a multi level dataframe.
 - Delegating and completing tasks within a short and restricted time frame.
 - Finding a new model that is simple enough to understand and implement within the time period given for this project

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
##### Adjust To Your Needs
To use this Project you will need to access the 'internal_metrics_pulling.ipynb' and adjust the tickers to meet your requirements. Then you will need to run the following code ipynb's in order:
1. internal_metrics_pulling.ipynb
2. feature_engineering.ipynb
3. Returns_Optimiser.ipynb
4. [Matt's Model]
5. [Anita's Model]
6. dashboard.ipynb

---

### Conclusion
##### How Well Did The Model Perform?
TO BE COMPLETED
##### Things We Could Improve on Given Time
1. Create a more streamlined approach as to how our code works by creating a single .ipynb that will run through all of our seperate code and give outputs accordingly
2. Given time we could look at implementing an automated trading bot based on our machine learning models. This could have been accomplished by creating an SQL database that can be fed real time data and indicators on given data when the trader would like to run their bot. Which from this database feeds a machine learning model to give a signal to, buy sell or hold, based on the most recently given data.

---
