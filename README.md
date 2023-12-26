# Forecast Norway Fishery Production using Time Series Techniques

*This is a project that my team and I accomplished when studying the subject of **Business Analytics** at UIT. My primary responsibilities are to dive deep into **descriptive statistics** and **2 machine learning algorithms** (ARIMA and RF)*.

## Memebers
| Full Name | Email | Github|Role| 
|--------------|-------|------|------|
| Thai Minh Triet | 19522397@gm.uit.edu.vn |https://github.com/triet2397 |Leader | 
| Nguyen Ngoc Hien | 20520496@gm.uit.edu.vn |https://github.com/ngochien1007 |Member | 
| Nguyen To Duc Tai | 20520743@gm.uit.edu.vn |https://github.com/DucTai0909|Member | 
| Nguyen Thi Kim Lien | 20520909@gm.uit.edu.vn | | Member | 
| Tran Ngoc Linh | 20521538@gm.uit.edu.vn | | Member | 

## Problem Statement

Forecasting fishery production of three species: Northeast Arctic cod, Northeast Arctic haddock, and Atlantic halibut using time series analysis techniques. The project studied and applied **10 algorithms** mentioned below:
- Autoregressive Integrated Moving Average (ARIMA) 
- Exponential Smoothing (ETS)
- Linear Regression (LR)
- Random Forest (RF)
- K-Nearest Neighbor (KNN)
- Recurrent Neural Network (RNN) 
- Long Short Term Memory (LSTM)
- Gated Recurrent Unit (GRU) 
- Sequence-to-Sequence Network (2Seq2)
- Temporal Convolutional Network (TCN)

## Dataset

The data used for forecasting in this study was taken from **2000** to **2023** on the catch of three common fish species in the region: **Northeast Arctic cod**, **Northeast Arctic haddock**, and **Atlantic halibut**. These species were chosen because they are common, have good data coverage, and are economically important. The development of forecasting models for these species will be valuable for fishermen.


- Source: [here](https://www.fiskeridir.no/Tall-og-analyse/AApne-data/Fangstdata-seddel-koblet-med-fartoeydata)

## Method


![pipeline](https://github.com/ngochien1007/forecast-fishery-production-using-time-series/assets/154615929/ff2738e4-a877-4c50-8faa-b8e5dba239a2)


#### Data Collection and Preprocessing

The dataset has 133 attributes containing important data, however, after identifying appropriate species, we selected **4 attributes** that meet the requirements of our Problem Statement:

- **Last Catch Date**
- Gross Weight
- Round Weight
- **Product Weight**

Since a fish species can be caught multiple times in a day by different boats, the group approached the problem by grouping and calculating **the daily total production**. To facilitate calculation and presentation in the report, the value of the production was converted **from kilograms (kg) to tons**.

After that, the missing data points are processed using **linear interpolation** to minimize unwanted effects on the shape of the time series.

**Result**: Each specie has **a Dataframe of 8568 rows** containing complete information about the fishing time and production on a daily basis.
  
#### Data Preparation

#### Experimental Setup

#### Model Development

#### Evaluation


## Result

![Results](https://github.com/ngochien1007/forecast-fishery-production-using-time-series/assets/154615929/c3386674-d297-4d32-a236-a04facb64b40)

## Conclusion



  

