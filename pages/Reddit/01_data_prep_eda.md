## Subreddit Classification ([Repo](https://github.com/JamesDargan/Reddit_Classification))

**Project Description:**
Utilizing Reddit's Pushshift API, I scrape reddit posts and comments from two similar subreddits, /r/pcgaming and /r/boardgames, with the goal of utilizing NLP techniques to classify posts into the correct subreddit. Here, I explore the text content and functional features of subreddit activity.
<br><br>


**Data Collection:**
Reddit provides a well-documented API for collecting data. I write 2 simple functions which extract posts and comments when given a subreddit name, a desired post count, and UTC datetime to scrape backwards from. This can be viewed as a py executable with my parameters [here](https://github.com/JamesDargan/Reddit_Classification/blob/master/code/api_pull.py).
<br>


####EDA of Structural Features
Before analyzing the text content of these posts, I explore what features describing the structure of the post content can be used in a model in addition to the text. I explore post and comment length, activity, time of posting, and domain of hyperlinked content in the notebook [here](https://github.com/JamesDargan/Reddit_Classification/blob/master/code/EDA_Posts.ipynb).


**Insight 1:**
Both subreddits have comparable text length. The boardgames subreddit has more extremely long content and pcgaming has more minimal text content.
<img src="assets/body_lengths.png?raw=true"/>


**Insight 2:**
PCGaming is more active in late hours of night / early hours of morning while Boardgames is more active in late afternoon. Thus time of day could be a useful predictive feature.
<img src="assets/comment_hours_bar.png?raw=true"/>


**Insight 3:**
Type of hyperlink content and domain predict subreddit. Image content in posts exclusively indicates /r/boardgames membership while many linked domain beyond youtube strongly indicate pcgaming membership.
<img src="assets/domain_links.png?raw=true"/>


####EDA of Text
Utilizing the nltk library, I tokenize and lemmatize the text content of titles, posts, and comments.

**Insight 3:**
We find words such as dice, card, and board which reference concrete objects is associated with /r/boardgames.
<img src="assets/title_lwords_bar.png?raw=true"/>
