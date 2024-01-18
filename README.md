# Predictive Time Series Modelling for Real Estate Investment using Zillow Research Data
<p align="center">
  <img width="600" src="https://github.com/MWENDA1999/Predictive-Modeling-Time-Series-Forecasting-G9DSF-FT06-P4/blob/main/Cover.jpg" alt="Predictive Time Series Modelling for Real Estate Investment">
</p>

This repository contains the code and analysis for developing a predictive time series model for real estate investment using Zillow research data. The project's goal is to provide Naruto Investment firm with solid recommendations for the top 5 best zip codes to invest in.

## 1. Introduction
Real estate is a significant component of most people's wealth, and this is especially true for American homeowners. However, the real estate market is influenced by various variables that can make it challenging for investors to choose the right investment opportunities. To help investors in this process, Naruto Consultants aims to develop a predictive time series model.

## 2. Business Understanding
Real estate comprises of land, buildings, and physical properties, with applications in residential, commercial, industrial, and agricultural sectors. It plays a pivotal role in the global economy, contributing significantly to the Gross Domestic Product (GDP).

Real Estate in the USA: With a population exceeding 330 million, the US real estate industry holds substantial economic importance, constituting around 6% of the GDP. The sector includes residential and commercial real estate, real estate development, property management, and real estate investment trusts (REITs).

This time series forecasting project is tailored to meet the specific needs of Zamara real estate investment firm. The primary objective is to empower their investment decisions by predicting future trends in real estate prices across various zip codes.

### Problem Statement
Real estate, a major component of individuals' wealth, faces complexities driven by various variables. We seek to streamline investment decisions by creating a predictive time series model. The primary goal is to recommend the top five zip codes for investment, considering factors like government policies, demographics, affordability, housing access, location, cash flow, and economic climate.
###  Objectives
Main Objective: Develop a time series model predicting the top five zip codes for real estate investment.

Specific Objectives:
* Identify and understand seasonal patterns influencing real estate prices in different zip codes.
* Evaluate which city exhibits the most promising real estate investment opportunities.
* Forecast property values over the short and long term, aiming to identify the most favorable zip codes for investment.
Metric of Success
The model's success will be measured by achieving a Root Mean Squared Error (RMSE) of less than 5%, coupled with the identification of the zip codes yielding the highest Return on Investment (ROI).

## 3. Notebook Structure
The Python notebook is structured as follows:
- Data cleaning
- External Data Validation
- Exploratory Data Analysis
- Data Preprocessing
- Data Modelling and Evaluation
- Conclusion and Recommendations

## 4. Data Understanding
The Data
The dataset is sourced from Zillow Research, a reputable and widely used platform for real estate market data. The dataset is stored in the file zillow_data.csv within the project repository. The dataset contains 14723 rows and 272 columns.
The Zillow dataset provides detailed real estate data, with each row representing a unique zip code. Here's an overview of the dataset structure:
* RegionID: A unique identifier for each region.
* RegionName: The zip code for the region.
* City: The city where the region is located.
* State: The state where the region is located.
* Metro: The metropolitan area associated with the region.
* CountyName: The name of the county where the region is located.
* SizeRank: A ranking of the region based on size.
* Monthly Price Data: Starting from April 1996 to April 2018, this dataset includes monthly real estate prices for each zip code.

## 5. Data Preparation
In order to prapare our data for modelling we :
1. Reshaped the data from wide to long format. Looking at the format of the data in zillow_data.csv, we noticed that the actual Time Series values are stored as separate columns.
     This is a wide format which makes the dataframe intuitive and easy to read. However, there are problems with this format when it comes to actually learning from the data, because the data only makes sense if you know the name of the column that the data can be found it. In order to pass this data to our model, we'll reshape our dataset to long format. Our dataframe now appears as shown below:
2. We coverted the ‘Date’ column to datetime format to enable easy manipulation of date and time information.
3. Slicing the data. We sliced our DataFrame to remain with the most recent data which is relevant for our analysis. This is because it reflects the current trends and market conditions more accurately. By focusing on the last 10 years, we can analyze data that is more representative of current market forces.
4. Perform Feature Engineering- We created a column with the Return On Investment(ROI), we will use this to determine the best county to choose zipcodes from.m
5. Check for missing values and handle them. Checking the dataframe info, we find that we have missing values in the ‘Metro’ and ‘Price’ columns. We fill the ‘Metro’ column with ‘missing’ and fill the missing price values using linear interpolation.

## 6. Exploratory Data Analysis and Data Preprocessing
* We performed trend analysis to identify and understand the underlying trends of the time series data.
* We also examined the stationarity of the time series. In time series modeling, it's commonly assumed that the data exhibits stationarity. This means that the statistical properties such as mean, variance, and autocorrelation of the series remain constant over time. Stationary data simplifies the modeling process significantly. 
* To verify if the time series data is stationary, techniques like the Dickey-Fuller test were employed along with examining the rolling mean. 
* Since the data turned out to be non-stationary, a method known as differencing was applied. Differencing helped in transforming the data into a stationary form, which is more conducive for time series modeling.
* ROI stands for Return on Investment, which is a measure of how much profit or loss a business makes from its investment. A higher ROI means a higher profit and a lower ROI means a lower profit or a loss.
* Monthly ROI is the ROI calculated for each month, based on the difference between the property value at the beginning and the end of the month, divided by the initial value, and the graph is plotted as shown below:
## 7. Data Preprocessing
During EDA, we noticed that the dataset as provided by Zillow comes in "wide format" and for our time series models to run, we had to convert it to "long format." A function was provided to do this. The top 5 zip codes based on %ROI were filtered, and data was grouped by date and zipcode, calculating the mean price for each group selecting from 2012. Home prices and monthly returns of each zipcode were plotted.
## 7. Data Modelling and Evaluation
The data was modeled using statistical time series models, such as ARIMA and SARIMA. The model's performance was evaluated using several metrics, such as Mean Squared Error (MSE) and Return on Investment (ROI).
## 8. Conclusion and Recommendations
The ARIMA and SARIMA models were evaluated using MSE and ROI%, and the top 5 zip codes to invest in were identified. The findings of this project can be used by Naruto Investments to make informed investment decisions in the real estate market.
