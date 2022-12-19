# ATMS523_Project

This code analyses the fire risk at a location point in Western US. Western US has seen a tremendously increase in the number of forest fires in the last dew decades, this makes it a necessity to analyse the trends in fire risk in Western US and check how well we can predict the fire risk. 

# Location 

We select the city of San Diego for our study. It is a city located in Southern California and is perfect with the goal of our study. 

# Method 

To analyse and quantiy the fire weather risk we use the Canadian Forest Fire Weather Index (FWI). It is an numerical index calculated using the fuel moisture codes and climate data and gives an extend of how prone a location to forest fires, higher the FWI: higher is the risk of forest fires. The FWI is calculated using the followinf climate parameters:
1) Temperature 
2) 24-hour precipitation
3) Relative humidity 
4) Wind speed

# Data 

We use the Global Meteorological Forcing Dataset from year 1990 to 2014 (DOI: 10.5065/JV89-AH11). This dataset has been downloaded in Keeling. \
We use the daily GMFD data to get the daily FWI values from 1990 to 2014. We use the 25 year timeseries of FWI values to see how the fire risk is varied monthly and daily. It is noted from the intial plots that the average FWI value is highest for the months of September, October, November, and December. The yearly timeseries plots also us a seasonal pattern in FWI values and shows an increasing trend over the years. 

# FWI Prediction 

We use different models and different data setup to check which model predicts the forest risk the best. We use a 80-20% split for training and testing data and use root mean square error and R^2 values as the measures of prediction accuracy. We different the following machine learning models: 
1) Multilinear regression
2) Polynomial regression 
3) K-Nearest Neighbour regression 
4) Random Forest regression

The different set-ups used are: 
1) FWI timeseries as the target variable
2) Standardised FWI timeseries as the target variable 
3) FWI timeseries as target variable and one hot encoding for the month parameter

The polynomial regression model was not fit for the third setup (with one hot encoding for month parameter). The RMSE and R^2 metrics for all the models for all the model setups were recorded and compared. Comparing the prediction accuracy metrics, random forest regression with the third setup (with one hot encoding for month parameter) gives the lowest RMSE and R^2 values. The model explains about 75% of the variation in the target variable and gives an RMSE of about 5.6. 

# Feature Importance 

The Random Forest models were used to check the feature importances to see which climate parameter is the most important in predicting fire risk. Feature importance was checked for all the three data set-ups. From all the feature importance plots it can be seen that the humidity is the most important feature while wind the least important feature. The feature importance plot with one hot encoding shows that the months do not affect the target variable much and not important. 
