# Project 5 - Utilzing Social Media to Map Natual Disasters
08-02-19 | General Assembly <br>
*Authors: Jeremy Ondov, Samuel Leadley, Yisroel Len, and Mimi Kim*

## Problem Statement
As the effects of climate change are intensifying the magnitude and frequency of natural disasters the need for modern technological solutions in emergency responses is crucial. It is well known that indivduals are increasingly using social media as a platform to express themselves. Utilizing social media as a tool in crisis situations can support first responders tending to victims in need. Leveraging social media sites like Twitter we can employ natural language processing and a classification model to classify which tweets are requesting urgent help and map those locations for first responders. 

## Data
### Datasets
Each targeted disaster was scraped and saved to its own csv file. These datasets were then compiled and cleaned, and had locations attached to each tweet. The final dataset is `clean_df.csv`.

### Data Dictionary

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


## Executive Summary
Our decision to base our program on information scraped from Twitter was due to Twitter's open scraping and privacy policies. However, the models we built could potentially be adapted to any social media platform, assuming the government first responders have authority to access those platforms like Facebook or Instagram. We used Twitterscaper, a well known tool for scraping Twitter, to access historical tweets of four different natural disasters and identify the most common forms of urgent help requests. These natural disasters were picked to represent a wide range of possible disasters, to make the model as robust and flexible as possible. The actual storms that were picked had been recent enough to have a wide amount of tweets connected to them, and in certain cases had specific hashtags for people to use in their tweets. The number of tweets was naturally enormous, making it difficult to sort through and find content actually containing emergencies, many of which could be phrased as such, but are merely hyperbole or jokes. Our method to deal with this beyond reading all twenty thousand tweets, was to establish a baseline of "crisis words" to red flag potential tweets. This was somewhat successful, but still returning a number of non-emergency tweets. Due to privacy issues the locations of the scraped tweets were withheld, preventing us from using the location of an emergency in our predictive model. However, to clear up any potential confusion, our final dataframe includes randomly generated geographic points with an emphasis on areas where there would be a supposed concentration of emergencies. 

## Conclusions and Recommendations

**Conclusions**

We were able to create an AdaBoost model that had an 89.1% recall towards new data (the test set), while minimizing variance as much as possible. Compared to the base model, we were able to increase the overall accuracy from 90.3% to 98.8%. During this process, we discovered how difficult it can be to determine if someone is trying to reach out for help through a tweet. Many times, words that might be used to indicate trouble are merely warnings, or news updates, making it extremely important to have correctly classified data to train the model on. There are many times where a model may not be able to determine context in certain language that a person would be able to identify.

**Recommendations**

We recommend while using this model to get broader social media access in order to access the location of each tweet. Having the real-time geo-location of the tweets is crucial as it would be difficult to map otherwise. It would also be helpful to have information about the timing of the tweets and using the frequency of tweets in a given time span to gauge how urgent the emergency is.  

**Limitations**

This model has many limitations. The dataset does not include all varieties of natural disasters and therefore might not be well prepared to classify tweets during natural disasters outside of the types we scraped Twitter for. Also, the data works with a limited time frame. 

Our dataset is also limited to Twitter only as it was the only social media platform that we were able to scrape. While having access to Facebook statuses would have been more helpful, most people have hidden profiles and statuses are not as easily accessible. Twitter was the only viable option as we were able to search for specific terms found in tweets. However, with Twitter we were unable to acquire location data for the individual tweets. Location would have been useful to include as a feature for our model.

It is also important to keep in mind the steps take early in the process to artificially create our target class in the dataset. In order to apply this model to a real-world scenario, it would be helpful to have a dataset that has already been combed and properly classified as to its emergency status.