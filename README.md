# LTA-Traffic

Road traffic congestion is one of the most significant problems in the world as the population burgeons with time, especially in larger cities. In Singapore, accidents and traffic conjection have increased in many major roads due to increasing number of vehicles at any point of time. Twitter has emerged as an important source of information on various topics including road traffic. A large number of tweets are posted every day by LTA Traffic News twitter account as it aim to inform their followers about traffic conditions. To minimize traffic related problem, it is very necessary to monitor traffic in real time so that we can recognize the areas and roads that are risky to safety of drivers and riders.

In this project, I would like to explore a methodology for preprocessing and analyzing these realtime traffic related incident tweets from LTA Traffic News twitter account as well as ideating ways to inculcate the corresponding realtime road traffic camera images and pinpoint precise location of traffic conditions.

First segment of my project I will focus on the collection, preparation and cleaning of the scraped LTA Traffic News tweets. Following which, I will be using text mining technique and natural language programming - to classify traffic related tweets, apply tokenization, stop word filtering, stemming and stemming filtering.  I will then move on to do sentiment analysis of the tweets - categorized into serious and non-serious tweets. After which, I will try to render geolocation of the traffic conditions in terms of latitude and longitude format. In additonal to, I will obtain the corresponding realtime road traffic camera images for a visual representation. The final segment will presents the conclusion and future work of the project. 

I managed to scrap 3222 tweets from @LTATrafficNews twitter account systemically backdated from 3th February 2020, 12pm [Web Scraped Timing]

After extracting the data from Twitter, the tweets were cleaned and preprocessed accordingly. Upon exploring my cleaned data set, several interesting observations were evident.

*Which months are road traffic accidents most likely to occur?*
***Taking into consideration of 3222 tweets with the cut-off in respective of web scraped timing***

![LTA 1](https://github.com/RadheV/LTA-Traffic/blob/master/Image1.png)

Tuesdays in the month of December has the highest number of traffic conditions reported. 
The dates [3th, 10th, 17th, 24th and 31st] falls on a Tuesday that month. Particularly 24th and 31st Decemeber are the eve of Christmas and New Year respectively. Perhaps the festive rush and laid mood might be a factor for this high traffic condition incidence? 

Let's take the exploration further.

*Which days are road traffic accidents most likely to occur?*
***Taking into consideration of 3222 tweets with the cut-off in respective of web scraped timing***

![LTA 2](https://github.com/RadheV/LTA-Traffic/blob/master/Image2.png)

For which, sentiment analysis was applied to categorize the tweets into serious and non-serious.

To find out some of the frequent and important terms being used in the tweets I have extracted, a word cloud was generated for both the categorized serious and non-serious.

**Non Serious Tweets**

![LTA 3](https://github.com/RadheV/LTA-Traffic/blob/master/Image3.png)

**Serious Tweets**

![LTA 4](https://github.com/RadheV/LTA-Traffic/blob/master/Image4.png)

The next step will be Feature Extraction where I needed to convert textual representation in the form on numeric features. For which, I went ahead with two popular techniques to perform feature extraction:
1. Bag of words (Simple vectorization)
2. TF-IDF (Term Frequency - Inverse Document Frequency)

Using a simple Naive Bayes model, I went ahead to find predictions on:
1. 'key words' based features
2. 'key phrases' based features
for both BOW word and TF-IDF word features

### Predictions on 'key words' based features

![CM1](https://github.com/RadheV/LTA-Traffic/blob/master/CM1.png)
[BOW word features] Accuracy Score = 0.969

![CM2](https://github.com/RadheV/LTA-Traffic/blob/master/CM2.png)
[TF-IDF word features] Accuracy Score = 0.971

### Predictions on 'key phrase' based features

![CM3](https://github.com/RadheV/LTA-Traffic/blob/master/CM3.png)
[BOW word features] Accuracy Score = 0.347

![CM4](https://github.com/RadheV/LTA-Traffic/blob/master/CM4.png)
[TF-IDF word features] Accuracy Score = 0.400


Based on comparing accuracy scores, predictions on 'key words' based features performed better than on 'key phrase' based features. And TF-IDF performed better than BOW though the difference were slight. 

Therefore, I am proceeding with TF-IDF as a vectorizer usind prediction on 'key words' based features 





