## Walmart Sales ([Repo](https://github.com/JamesDargan/Kaggle_Walmart))

**Project Description:**
Utilizing data provided by Walmart via Kaggle available [here](https://www.kaggle.com/c/walmart-recruiting-store-sales-forecasting/data), I aggregate sales by store level and perform exploratory analysis of weekly store sales and SARIMA models to predict future sales as time series.
<br><br>


#### EDA of Weekly Sales
Before generating any formal models, I explore the completeness of data coverage and explore trends in sales over time, detailed in my notebook hosted [here](https://github.com/JamesDargan/Kaggle_Walmart/blob/master/code/EDA.ipynb).


**Insight 1:**
Walmart store sales display an annual cycle with a massive spike during Christmas season and decline thereafter.
<img src="assets/rolling_sales_peak.png?raw=true"/>


**Insight 2:**
Superbowl Sunday and Labor Day do not stand out visually while the Black Friday spike and post-Christmas crash are massive.
<img src="assets/weekly_sales_holidays.png?raw=true"/>

**Insight 3:**
Viewing the average autocorrelation values across all stores, only the first lag appears statistically significant with some evidence of a monthly cycle. Additionally, the 52-week lag correlates more strongly with future weekly sales than any other time lag.
<img src="assets/autocorrelation_plot.png?raw=true"/>

**Insight 4:**
Out of 45 stores, 8 fail the ADFuller test of stationarity. I find 5 stores display consistent, long-term trends while 3 display evidence of temporary shocks within the provided timeframe.
