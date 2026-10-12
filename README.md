# Electricity_Demand_and_Price_forecasting

# Objective: 

The focal point of this project revolves around time series forecasting, encompassing the integration of two separate datasets comprising energy and weather data. By amalgamating energy consumption and weather-related metrics from multiple cities in Spain, the project endeavors to tackle a multivariate time series forecasting challenge.

The project employs a diverse array of forecasting models, including the XGboost Regressor, GRU (Gated Recurrent Unit), LSTM (Long Short-Term Memory), CNN (Convolutional Neural Network), CNN-LSTM, and LSTM-Attention. Additionally, hybrid models like GRU-XGBoost and LSTM-Attention-XGBoost are employed, harnessing the strength of multiple techniques through ensembling.

This project seeks to harness the power of these forecasting methodologies to derive accurate predictions for electricity demand and pricing in a time-dependent context, thereby contributing to the advancement of energy forecasting and enhancing decision-making within the energy sector. 
 

## About the Dataset:
The dataset includes a four-year record of weather data <a href="https://openweathermap.org/api">https://openweathermap.org/api</a> 
electrical consumption, pricing, and generation data for Spain <a href="https://transparency.entsoe.eu/dashboard/show">ENTOSE website</a> . The public ENTSOE portal was used to retrieve the consumption and generation data, while 
the Spanish TSO Red Electric España was used to obtain the settlement prices <a href="https://www.esios.ree.es/en/market-and-prices?date=27-03-2023#">TSO website</a>. 

# Method 
The code consists of 4 main parts:

- Data loading and feature exploartion: This part uses os and pandas to load, process the data into a dataframe, plotting correlation matrix on both the dataset. 
- Preprocessing: Involves getting rid of Null values, selecting features required hour,weekday, month, year from the data and plotting visualization, followed by normalizing and reshaping the data follwed by using The Dickey-Fuller test to check if thr data us stationary
- Model building and training: This part using PCA to select the features necessary,normalizing target variables and then building forecasting models With XGBoost, GRU, LSTM, CNN, CNN-LSTM,LSTM attention, GRU-XGboost, LSTM attention-XGboost.
- We plot the train an validation Mean Absolute Error for each case and also compare the scores across the different models towards the end. 

## Models used : 

#### 1. Machine learning : 
 * XGboost Regressor
#### 2. Deep learning/Stacked models :
* GRU 
* LSTM 
* CNN 
* CNN-LSTM 
* LSTM-Attention 
#### 3. Hybrid methods:   
* GRU-XGBoost 
* LSTM-Attention-XGBoost 

## Results
The MAE (Mean Absolute Error) is used to report the results for the normalized test set:
* TSO prediction : 0.070
* XGboost : 0.016
* GRU : 0.015
* LSTM : 0.018
* CNN : 0.025
* CNN-LSTM : 0.019
* LSTM-Attention : 0.015
* Hybrid GRU-XGBoost : 0.014
* Hybrid LSTM-Attention-XGBoost : 0.015