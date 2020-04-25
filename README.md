<img src='./images/reddit ethics.jpg' width='300' height='300'>

# Interpreting Ethics Using NLP and Social Media
### by Luke McKinley
<br>


## Problem Statement
---
#### As our society is bombarded with media from all outlets, consumers need to be confident the information we are consuming is not only legal and vactural, but also ethical.  

## Data Analysis
---
My initial dataset contained 10,000 posts each from LifeProTips and UnethicalLifeProTips.  Many values were cleaned by Pushshift API during downloading, so additional cleaning left a total of 19,852 rows of data.  

Beginning in notebook 02-tfidf-vectorization, I fitted the data on 5 different models:  
Cross Vectorization & Linear Regression<br>
TFIDF Vectorization & Linear Regression<br>
TFIDF Vectorization & Linear Regression with Sentiment Analysis<br>
Multinomial Naive Bayes<br>
Gaussian Naive Bayes<br>

The model that scored best with minimal variance was TFIDF Vectorization & Linear Regression.  

I built out a small list of custom stop words that, while lowering scores, made the output less generic. 
Additionally, setting ngrams to (1, 2) raised scores slightly, but again made the output more generic.  

Final testing scored as follows:  

Gridsearch best score: 0.811

Gridsearch training score: 0.879

Gridsearch testing score: 0.820

As a supplementary test, I tested my model against 5000 posts from the subreddit /r/Scams with no training and my model categorized 60% of the posts as unethical.  

## Conclusions
---
Using Natural Language Processing, our model is able to reliably classify 81% of unethical posts.  By adjusting the ngrams value, the model can be intentionally overfit to raise the training score to as high as 0.92.    
Although the model does not have exceedingly high accuracy at this time, with more data and model refinement, it can potentially be used as a browser plugin to warn about ethically questionable or misleading content. 




## Data Dictionary

---

### Data Source
All data was gathered using the pushift api to access reddit.com and the subreddits /r/lifeprotips, /r/unethicallifeprotips, and /r/scams.

### Data Types


|Column Name | Data Type|
|---|---|
|'text'| string|
|'unethical'| int|

