## Walmart Sales ([Repo](https://github.com/JamesDargan/Kaggle_Walmart))

**Project Description:**
Utilizing data provided by Walmart via Kaggle available [here](https://www.kaggle.com/c/walmart-recruiting-store-sales-forecasting/data), I construct a SARIMAX model to forecast future store sales.
<br><br>


#### Baseline Models
I propose 2 computation-free baselines to compare any forecast model against which perform with an average mean absolute percent error under 10%.
- *Baseline 1*: Each store's sales will be equal to the previous week
- *Baseline 2*: Each store's sales will equal that of the previous year for that weekly
Baseline 1 predicts sales with an average MAPE of 8.2 on the training data and 5.6 on the test data, but is not practical because forecasts are intended to provide advanced notice. Baseline 2 predicts sales with an average MAPE of 6.5 on the training data and 6.0 on the test data. Baseline 2 performs reasonably accurately, provides advanced notice in its forecasts, and requires minimal resources. However, this baseline will perform poorly when a store experiences any trend in sales.

**Baseline MAPE: Train 6.5, Test 6.0**


#### SARIMAX Parameter Search

**Seasonal Component: (1,1,1,52)**

**ARIMA Component: (2,0,1)**

**Exogenous Features:**
I exclude provided feature data which are not available at time of forecast. I explore temperature and changes in fuel prices as exogenous predictors but find both worsen model performance.

#### Business Context Simulation

To properly evaluate my model, I add 3 constraints to my model building and forecast process.
1. I delay sales data availability for the following week to simulate data collection and cleaning delay.
2. I extend forecasts to a two week advance minimum to simulate real-world demands of advanced notice for planning.
3. I maintain a consistent training window to simulate limited data storage.

All prediction errors will be measured from a 3-week advance to accommodate these simulated business demands.
<br><br>

#### Final Model Performance
