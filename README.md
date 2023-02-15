# Playground project

This repository is a small study on basic technical indicators for generating trading signals.


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


## 4. Future Work
### 4.1 Hyperparameter tuning

The model overfits by demonstrating a lower error score (0.283) in training stage and a higher error score (0.440) in testing. For handling overfitting and model tuning, we can leverage Optuna, a hyperparameter optimization framework to get the best model.

Unfortunately, as my limited computing resources do not allow me to run with Optuna, the model hyperparameter was only tuned manually. With more computing resources and model tuning, we should expect to handle overfitting better and get a more optimal trading strategy.


### 4.2 Categorical Features

CatBoost supports categorical, text and embedding features. As we obtain more financial metrics of each companies, we can further include categorical features to the model and further improve its predictability.

Reference: https://catboost.ai/en/docs/features/categorical-features
