# LSTM Stock Predictor

## Background

Due to the volatility of cryptocurrency speculation, investors will often try to incorporate sentiment from social media and news articles to help guide their trading strategies. One such indicator is the Crypto Fear and Greed Index (FNG) which attempts to use a variety of data sources to produce a daily FNG value for cryptocurrency. Here we build deep learning models using both the FNG values and simple closing prices to determine if the FNG indicator provides a better signal for cryptocurrencies than the normal closing price data.

For this peoject, I used deep learning recurrent neural networks to model bitcoin closing prices. 

With the first notebook, lstm_stock_predictor_fng.ipynb, I built a model that uses the FNG indicators to predict the closing price while the second model, found within the  stm_stock_predictor_closing.ipynb notebook, uses a  window of closing prices to predict the nth closing price.

### Data Preperation, training and testing 

The model will use a rolling 10 day window to predict the 11th day closing price.

*  Here we use the window_data function to generate the X and y values for the model.
* The data is split 70% for training and 30% for testing
* The data is then scaled by applying the MinMaxScaler to the X and y values
* Finally the we reshape the X_train and X_test data for the model, this way we are able to model's requirement of samples, time steps, and features.

In each notebook we built the same LSTM RNN architecture. In one notebook, we fit the data using the FNG values. In the second notebook, we fit the data using only closing prices.

Please note that the same parameters and training steps for each model.


* number_units = 30
* dropout_fraction = 0.2
* epochs = 15
* batch size = 3


### Evaluation 

The closing price model had a lower loss than the FNG model.

The closing price model also did a much better job with tracking the values over time. 

Lastly I found that a window of size 1 performs  best for each model. 


***This project was entirely built within google colab. The csv files were added to my google drive and the drive mount for an easy import. Additionally I have added the necessary csv files to this repo.***
