### Project 2 - Reddit NLP

## Goals:
Reddit, the user-generated internet news/content aggregator has at its heart a system of creating specialized "subreddits" where users may gather and discuss pertinent interests together. Our goal is to design a machine-learning algorithm based on supervised Natural Language Processing (NLP) and see if it has the ability to distinguish whether a post came from one of two selected subreddits.

## Methods
Using Python, pandas and dataframes as the primary mode of analysis as well as Python-based dependencies such as sklearn, nltk, and xgboost  to complete the modeling analysis. Analysis is completed in Jupyter Notebook form and all suggestions are contained within the Jupyter Notebook. Will utilize a variety of models native to sci-kit learn (sklearn) package such as Logistic Regression, Multinomial Naive Bayes, and Random Forest Classifier. Scores will be cross-validated and optimal parameters are primary found using GridSearchCV.

## Conclusions
Gathering roughly 8,000 posts and 10,000 posts from each subreddit, the cleaning process led to very little loss in of data and as such, each subreddit was well-represented in the final classification model. No balancing of classes was required.

From there, analysis and optimization of grid searches over hyperparameters led to the following insights. From all NLP models -  Logistic Regression, Multinomial Naive Bayes, Random Forest Classification, and XGBoost, it seemed like in general the Logistic Regression performed the best with the highest interpretability and least tuning.

A simple grid search on the Logistic Regression parameters while it took several iterations, was much simpler than the fine tuning that a XGBoost required. It was simply much easier to get a good result with Logistic Regression. Results of training off the submission selftext typically scored nearly 0.99 and roughly 0.95/0.96 across most of the model. Understandably so, the use of XGBoost as the last model was extraneous, as there was not much room for improvement, and our results show that as such. XGBoost's fitting did not have room to perform much better. Given its notable efficacy within the Machine Learning community, it is not hard to imagine that with even more tuning of the hyperparameters, XGBoost could beat all the other previously mentioned models. However, in this case, our subreddits were farther apart in terms of language than we initially estimated and NLP should be able to distinguish them close to 100% of the time. Most of the language we found that scored highly was very indicative of r/legaladvice.

One extra note of insight we found was that training models on comments alone and lead to good post accuracy scores (~.99). However, training a model on selftext could only lead to scores in the neighborhood of (0.80) for identifying the subreddit given a comment. This suggests that selftexts are MORE indicative of a subreddit than the comments. And intuitively, we think this is true because there are many more comments than there are posts (most users comment, but few post) and these comments may come with much more variance than the possibly moderate posts. We may also theorize that posts are typically submitted by the most dedicated members of the subreddit and as such, are more representative of the community.

TLDR:
- Logistic Regression was the most balanced model in terms of interpretability and Results
- Comments can predict Submission selftexts subreddit origin
- Selftexts cannot predict Comment subreddit origin

## Reference Sources
- www.reddit.com
- www.reddit.com/r/legaladvice
- www.reddit.com/r/relationship_advice
