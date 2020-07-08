## Subreddit Classification ([Repo](https://github.com/JamesDargan/Reddit_Classification))

**Project Description:**
Utilizing Reddit's Pushshift API, I scrape reddit posts and comments from two similar subreddits, /r/pcgaming and /r/boardgames, with the goal of utilizing NLP techniques to classify posts into the correct subreddit. I take a bag-of-words approach using both CountVectorizer and TFIDF text-representation methods. I then train three foundational classification models: Logistic Regression, Multinomial Naive-Bayes, and Linear Support Vector Classification.
<br><br>

#### Summarizing Bag-of-Words Classification Models

**Comparing 3 Model's Test Accuracy (CVEC):**

| Model     |   | Title  | Title & Body | Title, Body, & Comments |
|-----------|---|--------|--------------|-------------------------|
| Log Reg   |   | 0.8942 | 0.9151       | 0.9694                  |
| Multi NB  |   | 0.9000 | 0.9237       | 0.9705                  |
| Lin SVM   |   | 0.8911 | 0.9687       | 0.9618                  |


**Comparing 3 Model's Test Accuracy (TFIDF):**

| Model     |   | Title  | Title & Body | Title, Body, & Comments |
|-----------|---|--------|--------------|-------------------------|
| Log Reg   |   | 0.8950 | 0.9134       | 0.9805                  |
| Multi NB  |   | 0.8936 | 0.9073       | 0.9683                  |
| Lin SVM   |   | 0.8922 | 0.9173       | 0.9802                  |


**Insight 1:** TFIDF text representation enables greater accuracy performance with maximum text content included. The CVEC method maxed out about 1.5-2 accuracy points less for Logistic and SVC methods.

**Insight 2:** All 3 common text-classification methods performed similarly, with the greatest performance gap being less than 2 accuracy percentage points within most input setups.  

#### Comparing Accuracy Gains and Training Time

<img src="assets/TFIDF_3500_all.png?raw=true"/>

Above, the training time column measures in seconds the total time for gridsearch across several parameters when all title, post, and comment text was included. The time ratio column on the right illustrates the multiple of time required compared to completing the same gridsearch with only title text content. All times are dependent on local equipment and serve only to illustrate comparative times and performance.


**Insight 3:** Multinomial Naive-Bayes tended to slightly underperform logistic regression or SVC but required dramatically less computation time. The marginal gains to accuracy required much greater training time to find optimal parameters and fit.

<img src="assets/TFIDF_7000_all.png?raw=true"/>

The above table is identical to the previous table but now the n-grams and max features parameters have been expanded for gridsearch. The table illustrates the cost in time of training over more ngrams and including more features.

**Insight 4:** Doubling the maximum allowed features only slightly improved performance but required dramatically more computation time, illustrating the increasing cost of marginal gains in accuracy.
