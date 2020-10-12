# Capstone_Project2
Houston vs Chicago_House_Price

Introduction: The purpose of this project is to evaluate the house price difference between Houston and Chicago. Zillow provided Zillow Home Value Index (ZHVI) as a smoothed, seasonally adjusted measure of the typical home value across a given region and housing type. I focused on single-family residences for my research.

Section 1: Data Wrangling

1.1 Load House price data

Downloaded house price data from following webpage, https://www.zillow.com/research/data/. I used ZHVI Single-Family Homes Time Series in Metro & U.S from 1996-2020. The downloaded file name is called "Metro_zhvi_uc_sfr_tier_0.33_0.67_sm_sa_mon.csv".

1.2 Extract population data
Load population data. The data was downloaded from https://www.census.gov/data/datasets/time-series/demo/popest/2010s-total-cities-and-towns.html. Data is in Excel format and has headers.

1.3 Extract GDP data
Pull out GDP data from the BEA (US Bureau of Economic Analysis) API. BEA published economic statistics using industry-standard methods and procedures.

1.4 Extract Employment data
Pull GDP and Employment data from the BEA (US Bureau of Economic Analysis) API. BEA published economic statistics using industry-standard methods and procedures.

Section 2: Data Exploratory Analysis

2.1 Check the house price data

2.2 Check population data

Section 3: Linear Regression Model

3.1 Preprocessing data
As GDP, employment data, population data are recorded on yearly basis, I resample the house price to every year for following linear regression analysis. Merge data and clean data.

3.2 Data Exploratory Analysis

3.3 Linear Regression Model for Houston
Houston House price has very high correlation with GDP, total employment and population, then I build a linear regression model between Houston House price and GDP, population and employment.
House Price = -38699.16*GDP+61567.69*Total_Employment-1527.66*Population
GDP, total employment and population has very high correlation with each other, so we can drop features like total employment and population, decrease the prediction model order to one.
For Linear Regression model both multi-variable and single variable models are tested.
HOUSE PRICE = 0.00042*GDP-695.3363
Single variable model has better fit.

3.4 Linear Regression Model for Chicago
Chicago house price has very low correlation with GDP, total employment and population. GDP has very high correlation with total employment, GDP has negative relationship with population
HOUSE PRICE = -11176.31*GDP+12039.75*TOTAL_EMPLOYMENT-9225.55*POPULATION

Section 4 house price time series analysis

4.1 Two separate time series for Chicago and Houston house price house_c and house_h has been created earlier. 

4.2 Check house price time series is stationary or not.

4.3 Make Houston house price time series stationary.

4.4 Calculate ACF, PACF to determine the parameter AR(p), I(d), MA(q) for ARIMA model.

4. 5 Final ARIMA model for Houston house. Considering our time series is univariate time series with trend and without seasonal components, decided to use ARIMA (1,1,1) model on the original data.

4.6 Repeat same process for Chicago house price time series.
