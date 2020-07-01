## AMES Housing Regression ([Repo](https://github.com/JamesDargan/AMES))

**Project Component:**
I create a local library to house custom functions to automate visualization of various feature data types. I use pandas and missingno packages to identify missing values and inconsistent variable totals. I proceed to logically impute some missing values and create a linear regression imputation model for lot frontage.
<br><br>

**My Project Medium Blogs:**<br>
[AMES Data Cleaning]()<br>
<br>


**Logic-based Imputation:**<br>
I find 2 observations in training dataset with missing values for basement area or bathroom counts, which can be imputed with certainty based on other features indicating these observations do not have a basement.
<br>

**Probable Class Imputation:**<br>
I find a total of 28 observations containing missing values across 8 features. I single-value impute 7 categorical features and 1 continuous feature with probability > 90% based on class identity derived from related categorical features.
<br>

**Multiple Linear Regression Imputation Model:**
After extensive EDA and some logistic regression models, I find no evidence that these values are not missing at random. After performing EDA on features related to lot shape, size, and location, I create a regression imputation model for 490 observations missing a value for lot frontage (330 training, 160 test). My regression model imputes the log transform of lot frontage based on 5 features, which I then exponentiate to a value in feet.
<br><br>
Model R2 Score = 0.77 <br>
Model Root Mean Squared Error = 14.32 <br>
Model Median Absolute Error= 8.44$ <br>
Imputation average % Error: 11.90% <br>
<br>
The avoid summary means that on average, our imputed values likely misrepresent the true missing value by 8.4 feet on average, which is an error margin of about 12% relative to the correct, unknown value. While less than ideal in accuracy, this imputation enables this feature to be included in our predictive model without dropping over 10% of our training data or specifying 2 separate models for observations with and without this value.
<br><br>



**Insight 1: Inconsistent square footage values**<br>
A total of 40 observations (33 training, 7 test) have values for above-ground square footage that exceed the values for 1st floor and 2nd floor square footage. Exploring structural features, no consistent trend is found, including when exploring the hypotheses: 1) Houses of type 1.5 or 2.5 have offset levels not included in either 1st or 2nd floor, 2) Houses on uneven ground have added sf from either exposed basement or enclosed porches, which are already recorded separately.
<br><br>
**Insight 2: Low variance in most ratings**<br>
Out of 9 features with ordinal qualitative ratings on scales 1-5, 4 ratings features assign 1 value to over or near 95% of observations in our training dataset. The heavy concentration of these ratings renders these features without value for predictive modeling purposes.
<br><br>
**Insight 3: Cyclical scale activity but stable prices**<br>
Utilizing the sales date feature, I plot a cyclical trend in transactions annual with increased sales activity in spring and summer months. However, I do not find any trend in saleprice during our time interval.
<br><br>

**Why It Matters:** Detailed data cleaning ensures all features are consistent and values logical to avoid errors in the model building stages. In the provided AMES data, I found over 200 missing values across over 10 features, most of which were isolated occurrences. By correcting and imputing these missing values now, I avoid troubleshooting issues in my predictive models.
<br><br>
