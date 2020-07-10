# Classifying Partisanship in Politicians’ Social Media Posts

**Authors**: Maryam Seifeldin (https://github.com/mseifeldin) and Priyanka Shanmugasundaram (https://github.com/prishanmu)

**Filtering, encoding, and text-preprocessing code credit to**: https://www.kaggle.com/laiquet/neutral-and-partisan-tweets-posts



**Background** 

In the last few decades, much public political discourse has moved on to social media, and more intensely partisan messages from politicians on these platforms have been shown to heavily influence voters' decisions (Hemphill, Culotta & Heston, 2013). We apply machine learning techniques to find a relatively accurate model for identifying partisan messages in a sample dataset of Congressional politicians' tweets and Facebook posts from Crowdflower/Figure Eight. Aside from the text of each message, we use coded evaluations of each message’s target audience and intention as well as the identity of the posting politician, their state, and their Congressional house to predict partisanship.

**Data Source**

Link: https://www.kaggle.com/crowdflower/political-social-media-posts

Data come from Kaggle’s ‘Political Social Media Posts’ dataset, uploaded by Figure Eight. This data contains 5000 social media posts from Twitter and Facebook posted by US. House Representatives and Senators. Each post was then broken down by audience (national or local constituency), bias (non-partisan vs. partisan), and type of content in message (informational, attack on another candidate, appearance announcement etc.). In addition, the rater’s confidence in identifying each category was included. 

**Our Work**

1. Preprocessing:
Audience, bias, source and type of politician were contrast coded. Message content, each politician’s state, and the poster’s id was one-hot encoded. Each post was stripped of punctuation, non-words, stopwords using the NLTK library, and words with low-information load. Then, these posts were put into a TF-IDF vectorizer to extract features from the posts. Uninformative columns and columns with repetitive information, were dropped. We ended up removing about 3% of the posts by filtering out any raters whose confidence was not 100%. Each of these variables except for bias were used as features for our classifier and clusters.  

2. Classification:
For the classifier we decided that ‘bias’ was the target variable. We used GridSearchCV to test four models: Linear SVC, Kernelized SVM, Logistic Regression, and Random Forest Classifier. This provided us the best parameters for each model and the accuracy scores those parameters would give us. 

3. Clustering:
In order to decide the number of clusters necessary, we created an Elbow Plot. This recommended around 4 clusters. Using the KMeans model, we clustered the data into 4 clusters and compared averages of features based across clusters. Then, we conducted an ANOVA to see if there was a significant difference in bias between clusters. 

**Files in this Repo**

* Jupyter Notebook: Final_Project.ipynb

Please contact us directly if you would like to see our final poster. 







