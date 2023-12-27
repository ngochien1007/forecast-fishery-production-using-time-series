# Forecast Norway Fishery Production using Time Series Techniques

## Preface

This is a project that my team and I accomplished when studying the subject of **Business Analytics** at UIT. My primary responsibilities are to dive deep into **descriptive statistics** and **2 machine learning algorithms** (ARIMA and RF).

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


### Data Collection and Preprocessing

The dataset has 133 attributes containing important data, however, after identifying appropriate species, we selected **4 attributes** that meet the requirements of our Problem Statement:

- **Last Catch Date**
- Gross Weight
- Round Weight
- **Product Weight**

Since a fish species can be caught multiple times in a day by different boats, the group approached the problem by grouping and calculating **the daily total production**. To facilitate calculation and presentation in the report, the value of the production was converted **from kilograms (kg) to tons**.

After that, the missing data points are processed using **linear interpolation** to minimize unwanted effects on the shape of the time series.

**Result**: Each specie has **a Dataframe of 8568 rows** containing complete information about the fishing time and production on a daily basis.
  
### Data Preparation

The dataset was divided into three subsets: train, validation, and test with 2 ratio **(7:1:2 and 6:2:2)**. Interestingly, regardless of the ratio used, the **test set** covered the period **from October 7 2018 to June 16 2023**. 

To improve the performance of our experiments and optimize computational costs, we normalized the data to have **a mean of 0** and **a standard deviation of 1**. 

Moreover, we modeled the problem as **an autoregressive model** to forecast multiple days in the future, where past values are used to train the model and predict production. In this study, for each ratio and each type of seafood, we **used the production values from the most recent 90 days to predict the next 30 days**.

### Experimental Setup

The data preparation approach presented in the previous section was used in most experimental processes of time series forecasting models, except for LR, ETS, and ARIMA. For Machine Learning models, we set and fine-tuned the model parameters to achieve the best performance on the validation set.

In terms of Deep Learning models, these are trained with batch size 64 for 5 epochs using Adam optimizer and MSE loss function. RNN, LSTM, and GRU models had 2 layers of 32 neurons and used tanh activation function. Sequence-to-Sequence model had 2 LSTM layers of 64 neurons in both encoder and decoder. TCN model had 3x3 kernel size with number of layers and filters tuned in experiment for real data stability.

### Model Development

**Tools**: 
- Jupyter Notebook
- Google Colaboratory

**Libraries**: 

- pandas, numpy, matplotlib, sklearn, statsmodels, keras,...: Process data, analyze, and build forecasting models.
- bigdl, json: Train models and process Big Data.

### Evaluation

The following metrics are used to evaluate models:

- MSE
- RMSE
- MAE
- MAPE
- R2

## Result

In general, **deep learning models** show superior performance over traditional machine learning-based time series forecasting models. Besides Linear Regression, the standard ARIMA model shows the lowest experimental performance in all 5 metrics due to its seasonal features, so the forecast line is only a straight one. Based on RMSE, the forecasts of the models using **a 7:1:2 ratio** for the experiment usually show better performance than when using a 6:2:1 ratio.

![Results](https://github.com/ngochien1007/forecast-fishery-production-using-time-series/assets/154615929/c3386674-d297-4d32-a236-a04facb64b40)

## Conclusion

After identifying the two best models for each experimental ratio for each marine species, we applied them to forecast the production of these species in **the next 30 days from June 17 2023**, and visualize the forecast results in the form of a graph, containing information about the production in the most recent 90 days for the last 30-day forecast, the results of the last 30-day forecast and actual values, and finally, the results of the next 30-day forecast in the future.

- **Northeast Arctic cod**
  - GRU, Random Forest (7:1:2 and 6:2:2)
- **Northeast Arctic haddock**
  - RNN, LSTM (7:1:2)
  - GRU, Seq2Seq (6:2:2) 
- **Atlantic halibut**
  - GRU, ETS (7:1:2)
  - TCN, ETS (6:2:2) 

## Acknowledgement

I would like to express my sincere gratitude to my leader, **Triet**, for his guidance, support and feedback through the tough semester. Also, I would like to thank my teammates, **Tai**, **Lien**, and **Linh** for their helpful discussions and compainionship.

