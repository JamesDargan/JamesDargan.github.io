## AMES Housing Regression ([Repo](https://github.com/JamesDargan/AMES))

**Project Component:**
After imputing missing values and engineering my desired new features, I proceed with linear methods for predictive modeling. I find minimal benefit from incorporating an L1 or L2 regularization penalty or applying Principal Components.
<br><br>



**Baseline Model 1: OLS on home SF components** <br>
R2: 0.715 <br>
RMSE: 55,280 <br>
MAE: 32,256 <br>

**Baseline Model 2: Neighborhood Average** <br>
R2: 0.760 <br>
RMSE: 51,382 <br>
MAE: 23,694 <br>


**Full OLS Model** <br>
I build an OLS model using 80 predictive features (counting all dummies). These features were selected based on EDA or engineered from provided features to be more informative. I exclude over half of the originally provided features due to low-variance, absence of relationship with sale price, or engineering of derived features. <br>
R2: 0.967 <br>
RMSE: 20,128 <br>
MAE: 9,777 <br>
My model reduces the mean absolute error by 58% compared to the neighborhood average baseline. My selected and engineered features explain 97% of the variance in home sale prices compared to the overall average. This is an increase of 20 points over the neighborhood average model. I find my residuals are normally distributed, not collinear with any continuous features, and homoskedastic with respect to sale price.
<br><br>

**Insight 1: Applying log transform to target improves performance by 29%.** After applying a log transform to saleprice, the OLS model mean absolute error decreases by about 3,900 from 13,714 to 9,776, an improvement of about 29 percent. Measuring by root mean squared error, the improvement is about 21% from an RMSE of 25,343 to 20,138. <br>


**Insight 2: Ridge regularization does not improve model performance.** Using 5-fold cross-validation, I find the optimum L2 alpha parameter value to be 0.22, which means any significant regularization reduces model performance. My 0.22 alpha model produces comparable metrics to the OLS model but with a larger training mean absolute error. <br>


**Insight 3: Lasso regularization worsens model performance.** Using 5-fold cross-validation, I find the optimum L1 alpha parameter value to be the minimum allowed in my search, which means the minimum regularization always outperforms greater regularization strength. My 0.2 alpha model produces 2.5 times the error as my OLS model, indicating all features which are not already optimized near 0 via OLS contribute valuable information. <br>


**Insight 4: Principal components regression does not outperform ordinary OLS.** Because my selected features already contain little pairwise correlation, my OLS does not suffer from collinearity issues. Even after 50 principal components are included, additional components continue to add predictive power. <br>
