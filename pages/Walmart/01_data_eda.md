## Walmart Sales ([Repo](https://github.com/JamesDargan/Kaggle_Walmart))

**Project Description:**
Utilizing data provided by Walmart via Kaggle available [here](https://www.kaggle.com/c/walmart-recruiting-store-sales-forecasting/data), I aggregate sales by store level and perform exploratory analysis of weekly store sales and SARIMA models to predict future sales as time series.
<br><br>


#### EDA of Weekly Sales
Before generating any formal models, I explore the completeness of data coverage and explore trends in sales over time, detailed in my notebook hosted [here](https://github.com/JamesDargan/Kaggle_Walmart/blob/master/code/EDA.ipynb).


**Insight 1:**
Walmart store sales display an annual cycle with a massive spike during Christmas season and decline thereafter.
<img src="assets/roll_weeklysales.png?raw=true"/>


**Insight 2:**
Most holidays have negligible impact on weekly store sales.
<img src="assets/holidays_weeklysales.png?raw=true"/>


**Insight 3:**
Weekly sales displays sufficient stationarity to apply time series models without differencing. Additionally, the annual cycle of sales has greater correlation to current sales than any recent sales history.
