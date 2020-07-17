# Selected Projects

---

## Exploring SAT and ACT State Averages ([Repo](https://github.com/JamesDargan/ACT-SAT){:target="\_blank"})

I measure the impact of student self-selection into participation on college prep exams and explore the resulting bias introduced to state rankings based on state average scores using data scraped from various digest tables published by the NCES for the classes of 2017 and 2018. By incorporating case studies and analyzing changes between years, I demonstrate a causal connection between participation rates and state averages on the ACT and SAT. I produce a MLR with an adjusted R2 of 0.805 and mean absolute error of 0.68 points when explaining 2017 ACT scores, which predicts 2018 scores with a mean absolute error of 0.75 points.
<br>

**My Medium Blogs on This Project:**<br>
[Visualizing SAT & ACT Averages](https://medium.com/@james.dargan/visualizing-sat-act-averages-2a4759f9684){:target="\_blank"}<br>
[Participation Rates Skew State Averages](https://medium.com/@james.dargan/participation-skews-state-averages-f68969371a01){:target="\_blank"}<br>
[Opt-In Bias Drives SAT & ACT State Averages](https://medium.com/@james.dargan/self-selection-drives-state-averages-8e5b53be0c17){:target="\_blank"}<br>
[Estimating Classroom Impact on State Averages](https://medium.com/@james.dargan/estimating-classroom-impact-on-sat-act-state-averages-b91891cae252){:target="\_blank"}<br>


[Visualizing State Differences ](pages/ACT-SAT/01_visualization.md) <br>
Utilized Python and Plotly to collect data from online sources and create interactive U.S. Maps to compare state averages and participation rates on the SAT and ACT exams.
<img src="images/part_and_score_by_state.png?raw=true"/>


[Predicting State Averages](pages/ACT-SAT/02_participation.md)<br>
Utilized Python and Stats Models to quantify the relationship between test participation rates and states averages, I demonstrate state rankings from these assessments misrepresent the relative quality of state education systems through the bias of student self-selection.


[Modeling Impact of State Education System Features](pages/ACT-SAT/03_state_char) <br>
Incorporating state level spending per student, average class size, and average teacher salary as a proxy for teacher quality, I model how these affect state performance on college admissions tests after controlling for participation. I show failing to account for the selection bias produces drastically biased coefficients and lower explanatory power.


---

## AMES Housing Regression ([Repo](https://github.com/JamesDargan/AMES){:target="\_blank"})

Provided with a variation of the classic AMES real estate dataset for a private Kaggle competition, I perform extensive EDA, impute missing values across 10 features including a regression imputation model, and engineer new features. I build an OLS on a selected subset of provided and engineered features which reaches an R2 score of 0.97. I demonstrate my OLS model outperforms L1 and L2 regularized models as well as principal components regression. I then buid a voting classifier based on OLS, Random Forest, and XGBoost models which improves test peformance by 10% as measured by root mean squared error.

[Validation and Missing Imputation](pages/AMES/01_cleaning.md) <br>
I use pandas and missingno packages to identify missing values and inconsistent variable totals. I proceed to  impute values for 30 observations across 10 features based on class probability estimation. I create a linear regression imputation model for lot frontage with an average margin of error of about 10%.


[Regularization and PCA](pages/AMES/03_linear_models.md) <br>
I build an OLS model on selected and engineered features which delivers an R2 score of 0.967, a root mean squared error of 20,128, and mean absolute error of 9,777, which outperforms simple base models by 58% or more. I explore incorporating regularization and principal components into my linear model.

---

## Reddit NLP Classification ([Repo](https://github.com/JamesDargan/Reddit_Classification){:target="\_blank"})

Utilizing Reddit's Pushshift API, I collect posts and comments from the subreddits /r/pcgaming and /r/boardgames. I perform core NLP tasks, EDA of text content, and create a bag-of-words based predictive model to classify new posts with 98% accuracy.

[Data Scrape and EDA](pages/Reddit/01_data_prep_eda.md)<br>
I build a pair of functions to collect post content from Reddit through its API. I explore the text content and functional features of subreddit activity.


[Bag-of-Words Models](pages/Reddit/02_models_text_comp.md)<br>
I tokenize, lemmatize, and employ CountVectorizer and TFIDF to prepare my collected data. I then use Logistic Regression, Multinomial Naive-Bayes, and Support Vector Classifiers to predict post subreddit with over 90% accuracy. I then compare the accuracy and model optimization computational time for each model with increasing layers of text content.

---

## Domestic Flights


---

## Digit Classification ([Repo](https://github.com/JamesDargan/MNIST){:target="\_blank"})

[NMIST Convolutional NN](pages/MNIST/01_walkthrough.md) <br>
I create a walkthrough notebook on Kaggle that briefly explores the role of each layer in constructing a multilayer convolutional neural network which scores 0.98775 accuracy on the Kaggle test set. I demonstrate keras tools to view network architecture, visualize activation layers applied on test data at each stage, and generate confusion matrices.


[Step-by-Step Optimization of CNN with Kannada and Arabic Digits](pages/MNIST/02_combine_kannada_arabic.md) <br>
I combine the Kannada and Arabic handwritten digit datasets and empirically test and optimize each component of a CNN architecture to build a model with 98.692% test accuracy across 20 digit categories. I then explore error introduced by similarities between digits across languages.

<img src="pages/MNIST/compare_assets/kannada_digits.png?raw=true"/>


---

## Walmart Store Sales ([Repo](https://github.com/JamesDargan/Kaggle_Walmart){:target="\_blank"})

[EDA of Weekly Sales](pages/Walmart/01_data_eda.md) <br>
I explore trends in Walmart sales at the store level over time, demonstrating stationarity and identifying good candidates parameters for a SARIMA time series model.

<img src="pages/Walmart/assets/rolling_sales_peak.png?raw=true"/>



[Optimizing a SARIMA Forecast](pages/Walmart/02_SARIMAX_model.md) <br>
Utilizing 3 stores as case studies, I explore SARIMA model parameters, residual patterns, and overall performance at the individual store level in predicting weekly sales. I find an optimal model structure for each store to forecast sales with a mean absolute percent error of 2.77, 3.13, and 3.60 respectively. I then limit historical data reach and extend forecast distance to more closely simulate practical business conditions, retaining prediction error within 5%.
<br><br>
Utilizing 45 stores, I systematically optimize a SARIMA structure for all stores with adjustments for special-cases. I explore adding exogenous variables such as changes in fuel prices without success. I simulate a real-world business context to evaluate my model and find an average test mean absolute percent error of %.


---
<p style="font-size:11px">Page template forked from <a href="https://github.com/evanca/quick-portfolio">evanca</a></p>
<!-- Remove above link if you don't want to attribute -->
