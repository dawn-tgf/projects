 Project 3: Subreddit Classification using NLP

## Problem Statement
To develop a classifier that can predict if a reddit user is suffering from depression, or has the tendency to commit suicide by classifying posts from two subreddit "depression_help" and "SuicideWatch"  

## The Need
Suicide is the 10th leading cause of death in the US.  According to the statistics from American foundation for Suicide Prevention, there are estimated 3836 suicide attempts per day in 2017. Suicide prevention is one way to combat the problem.  

Depression usually develops before suicide. The purpose of this project is to create a NLP classifier that hopefully can distinguish someone with suicidal intents from depression by analyzing the words they say.  This is done by classifying posts from two Reddit subreddit "depression_help" and "SuicideWatch"  

 Reddit is an American social news aggregation, web content rating, and discussion website. Registered members submit content to the site such as links, text posts, and images, which are then voted up or down by other members. Posts are organized by subject into user-created boards called "subreddits".  According to Alexa Internet, as of July 2019, Reddit ranks as the No. 5 most visited website in the U.S. and No. 13 in the world.  Subreddit "SuicideWatch" has 179K members, while "depression_help" has 47.3K members.  As their names suggest, these two subreddits are platforms where users with depression or suicidal thoughts could use to seek help.  Texts from these two subreddits form the dataset of this classifier project.

## The Solution
NLP classifiers Logistic Regression and Naïve Bayes were used and their performance was evaluated.

The classifier attempts to predict which subreddit a given post came from.  The positive is "SuicideWatch". In this case, as our goal is to prevent suicide, the evaluation metrics is to minimize false negative (i.e. avoiding scenario when someone with suicidal thoughts is incorrectly predicted as just having depression, hence a miss case ).  Technically speaking, that's to maximize the sensitivity or recall.

The performance results show that none of the models generalize well. The best model using Countervectorizer and LogisticRegression only has 77% of accuracy and 85% of sensitivity after optimization.  This can be explained by the similar contents, the high overlaps of the words seen in both subreddits.  In order to have better results, other classifiers such as SVM or Random Forest could be explored.

 ## Conclusion

 The classifier is able to predict a SuicideWatch post with an accuracy of 77% and sensitivity of 85%, which isn't fantastic. However what is learnt from this project is:
 - If someone mentions "suicide", "suicidal" or "kill", or "die" in a post, we shouldn't ignore the potential of suicidal intention, for very obvious reasons.
 - A suicidal person tends to say things like "doesn't matter", or "it's okay" in his post, which is the exact opposite of the situation.  
 - A suicidal person also seems to mention "ex" and "dad" - as I'm not a domain expert in psychology, but it's natural to guess that father has some sort of influence, and relationship is one of the reasons of suicides.  This can be verified with the domain experts.
