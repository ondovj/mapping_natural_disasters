# Project 5 - Utilzing Social Media to Map Natual Disasters
08-02-19 | General Assembly <br>
*Authors: Jeremy Ondov, Samuel Leadley, Yisroel Len, and Mimi Kim*

## Problem Statement
As the effects of climate change are intensifying the magnitude and frequency of natural disasters the need for modern technological solutions in emergency responses is crucial. It is well known that indivduals are increasingly using social media as a platform to express themselves. Utilizing social media as a tool in crisis situations can support first responders tending to victims in need. Leveraging social media sites like twitter we can employ natural language processing and Logistic Regression to classify which tweets are requesting urgent help and map those locations for first responders. 
## Executive Summary
Our decision to base our program on information scraped from Twitter was due to Twitter's open scraping and privacy policies. However, the models we built could potentially be adapted to any social media platform, assuming the government first responders have authority to access those platforms like Facebook or Instagram. We used Twitterscaper, a well known tool for scraping Twitter, to access historical tweets of four different natural disasters and identify the most common forms of urgent help requests. The number of tweets was naturally enormous, making it difficult to sort through and find content actually containing emergencies, especially considering the proclivity of Twitter users to say things like "Help me!!" or "Get me outta here!!" when they're at their inlaws'. Our method to deal with this beyond reading twenty thousand tweets, was to establish a baseline of "crisis words" to red flag potential tweets and then narrow it down further by creating a bag of "anti-crisis words". This was somewhat successful, but still returning a number of non-emergency tweetsDue to privacy issues the locations of the scraped tweets were withheld, preventing us from using the location of an emergency in our predictive model. However, to clear up any potential confusion, our final dataframe includes randomly generated geographic points with an emphasis on areas where there would be a supposed concentration of emergencies. 

**Data**

|Category|Description|Example|
|---|---|---|
|is_retweet|Whether or not the tweet was a retweet|0|
|likes|Number of Likes|5|
|replies|Number of replies|20|
|retweets|Number of retweets|7 |
|text|Actual tweet|Help I'm stuck|
|timestamp|Year-Month-Day : Hour-Minute-Second|2018-03-04 23:56:24|
|tweet_id|Unique tweet Id|9704483028589536|
|user_id|Unique User Id|2890288726|
|username|Username|SomeRandomDude|
|disaster|The type of disaster|Hurricane|

## Model Interpretation
With 20,694 tweets and only 2,202 potential emergencies, any baseline model would be completely ineffective because it would either allocate resources to every single tweet out there or none at all. 

![Proof of concept](/Images/Example.png)

## Conclusions
Our final model had a score of BLANK 

**Possible ways to improve the model**
1) Getting access to data with locations during actual emergencies to train or model and help it predict the locations of actual emergencies.
2) Using time to improve the model as well. It could be that tweets which are uploaded in close proximity would indicate emergencies.
3) Further narrowing of the targeted tweets, to be more specific and more likely to be actual emergencies. This would involve a lot of manual labor but probably would be the best solution.
4) More tweets in disaster situations to find variations of calls for help.



