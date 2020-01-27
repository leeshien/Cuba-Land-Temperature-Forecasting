# Cuba-Land-Temperature-Forecasting
### 1. Dataset Description 
  * Monthly average land temperature from Jan 1823 - Sept 2013
  
### 2. Split dataset to train-test set
  
### 3. Analysis
  * Check for existing of trend by plotting the original time series and ACF 
  * Check for existing of seasonality by plotting ACF
  
A) The following ACF plot shows strong seasonality with 12 months period.  

![alt text](https://raw.githubusercontent.com/leeshien/Cuba-Land-Temperature-Forecasting/master/Cuba_plot/ACF_ori_cuba.JPG)

B) Below is the ACF/PACF plot after applying 12-period seasonal differencing. The ACF plot indicates setting Q to 1 while the PACF plot indicates setting P to 1.

![alt text](https://raw.githubusercontent.com/leeshien/Cuba-Land-Temperature-Forecasting/master/Cuba_plot/ACF_PACF_differencing(12).JPG)

C) Below is the ACF/PACF plot for residuals of SARIMAX (0,0,0)(1,1,1,12). The decaying pattern of ACF plot shows underdifferencing, therefore regular differencing is necessary and a new model will be built with parameter d set to 1.

![alt text](https://raw.githubusercontent.com/leeshien/Cuba-Land-Temperature-Forecasting/master/Cuba_plot/ACF_PACF_differencing(12)_00011112.JPG)

D) Below is the ACF/PACF plot after applying first-differencing followed by 12-period seasonal differencing. The ACF plot indicates setting Q to 2 or 1 while the PACF plot indicates setting P to 0.

![alt text](https://raw.githubusercontent.com/leeshien/Cuba-Land-Temperature-Forecasting/master/Cuba_plot/ACF_PACF_differencing(1,12).JPG)

E) Below is the ACF/PACF plot for residuals of SARIMAX (1,1,1)(0,1,1,12). Most of the residuals are within 95% confidence interval. Therefore the model fits the data well.
  
![alt text](https://raw.githubusercontent.com/leeshien/Cuba-Land-Temperature-Forecasting/master/Cuba_plot/ACF_PACF_differencing(1,12)_11101112.JPG)

F) The forecasting is plotted as followed:

![alt text](https://raw.githubusercontent.com/leeshien/Cuba-Land-Temperature-Forecasting/master/Cuba_plot/forecast_11101112.JPG)
  


