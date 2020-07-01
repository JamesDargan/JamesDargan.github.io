## AMES Housing Regression ([Repo](https://github.com/JamesDargan/AMES))

**Project Component:**
Building on my high-performing OLS model of housing prices, I explore non-linear models which more flexibly capture the relationships between by many categorical features and sale price. I build a equal-weighted voting classifier of OLS, Random Forest, and XGBoost models to reduce my training error by 34%.
<br><br>

**My Project Medium Blogs:**<br>
[]()<br>
<br>


**Random Forest**<br>
My random forest models optimizes at 20 features with 200 estimators, however it exhibits the common problem of overfitting. Even after reducing feature counts and estimators, a 10 point training-test gap in performance remains as measured by R2 scores.

Interestingly, when overall quality is included as a feature it dominates all other features with 10-fold the importance of the 2nd most important feature. However when overall quality is removed, the most important feature has half the relative importance and all top 10 features gain a relatively large influence, often around 50% increase in importance.
<br><br>



**XGBoost**<br>
My XGBoost model optimizes at a depth of 1 and displays only a 5 point gap between training and test performance as measured by R2 scores.

Overall quality exhibits much less influence in this model, demonstrating  feature importance of less than 15% than that in random forest. The model also performs better without it included as a feature.
