# y-intercept_coding-test

This repository contains solution for the Zhiyun's coding test as part of the summer internship recruitment process.


## 1. How to use
### 1.1 Setup
```
conda create -n test python=3.6
source activate test
pip install -r requirements.txt
```


## 2. Methodology
### 2.1 Data Processing
* Correlation analysis on log daily return 
* Cointegration test for pairs trading strategy
* Technical indicators construction
  - VWAP
  - Bollinger Bands
  - Stochastic Oscillator
  - MACD
  - Momentum
  
### 2.2 Model 
The trading action is modelled as a classification problem - whether we should enter a buy/sell position on a certain security on each day, given the trading indicators constructed from the time-series price and volume data. Here, the scalable, high performance gradient boosting model - CatBoost, is implemented for the classification problem.


## 3. Implementation
### 3.1 Modules and Repository Structure
- Full implementation of the trading strategy is included in a Jupyter notebook under the `code` module
- The stock data used is separated into the `data` module
