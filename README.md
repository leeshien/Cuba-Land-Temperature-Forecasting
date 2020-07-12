# Cuba-Land-Temperature-Forecasting
## 1. Dataset Description 
  * Monthly average land temperature from Jan 1823 - Sept 2013
  
## 2. Split dataset to train-test set
  
## 3. Analysis and Forecasting
  * Check for existance of trend by plotting the original time series and ACF 
  * Check for existance of seasonality by plotting ACF
  
### SARIMAX (Statistical model)
A) The following ACF plot shows strong seasonality with 12 months period.  

![alt text](https://raw.githubusercontent.com/leeshien/Cuba-Land-Temperature-Forecasting/master/Cuba_plot/ACF_ori_cuba.JPG)

B) Below is the ACF/PACF plot after applying 12-period seasonal differencing. The ACF plot indicates setting Q to 1 while the PACF plot indicates setting P to 1.

![alt text](https://raw.githubusercontent.com/leeshien/Cuba-Land-Temperature-Forecasting/master/Cuba_plot/ACF_PACF_differencing(12).JPG)

C) Below is the ACF/PACF plot of residuals for SARIMAX (0,0,0)(1,1,1,12). The decaying pattern of ACF plot shows the data is underdifferenced, a regular differencing might help to forecast better thus a new model will be built with parameter d set to 1.

![alt text](https://raw.githubusercontent.com/leeshien/Cuba-Land-Temperature-Forecasting/master/Cuba_plot/ACF_PACF_differencing(12)_00011112.JPG)

D) Below is the ACF/PACF plot of residuals for SARIMAX (0,1,0)(1,1,1,12). The ACF plot shows that q should be set to 1 while the PACF plot shows that p should be set to 1 too. 


E) Based on analysis from previous model, a new model, SARIMAX (1,1,1)(0,1,1,12) has been trained and below is the ACF/PACF plot of residuals for the model. Most of the residuals are within 95% confidence interval. Therefore it can be concluded that the model fits the data well.
  

F) AIC, BIC and RMSE from the three models above:
|Model          | AIC        | BIC           | RMSE  |
|---------------| ------------- |:-------------:| -----:|
|SARIMAX (0,0,0)(1,1,1,12)| 4209      | 4688 | 3845 |
|SARIMAX (0,1,0)(1,1,1,12)| 4226      | 4705      |   3873 |
|SARIMAX (1,1,1)(1,1,1,12)| 0.7413 | 0.7522      |    0.7804 |
  


