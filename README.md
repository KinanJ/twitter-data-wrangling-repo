# WeRateDogs Twitter data wrangling 
## by Kinan Jemil Hassen

## Dataset

There were three datasets used in this illustration. The main data is the tweet archive of Twitter user @dog_rates, also known as WeRateDogs. Since the twitter archive on its own wasn’t sufficient to perform any remarkable exploratory analysis, a dataset containing image predictions and another dataset which consisted of retweet and favorite counts were used as well.

The tweet archive dataset can be found [here](https://d17h27t6h515a5.cloudfront.net/topher/2017/August/59a4e958_twitter-archive-enhanced/twitter-archive-enhanced.csv) and the image predictions file can be found [here](https://d17h27t6h515a5.cloudfront.net/topher/2017/August/599fd2ad_image-predictions/image-predictions.tsv). The final dataset containing retweet and favorite counts can be accessed through twitter api but for the sake of convenience, you can get the file [here](https://video.udacity-data.com/topher/2018/November/5bf60fc9_tweet-json/tweet-json.zip)<br>

## Required Packages

* pandas
* NumPy
* requests
* tweepy
* json


## Project Phases

Step 1: Gathering data

Step 2: Assessing data

Step 3: Cleaning data

Step 4: Storing data

Step 5: Analyzing, and visualizing data

Step 6: Reporting


## Summary of Findings

The objective of this data wrangling project was to gather data from various sources, perform assessment, clean the data and then perform some analysis to provide insights and visualizations. The insights and visualizations were described through a well written report.

There were 3 different datasets on which I was expected to work on. They were the twitter archive of the twitter user WeRateDogs and an image predictions dataset both provided by Udacity. As for the third dataset, I was expected to gather it through the twitter API using the tweepy library. All three datasets were gathered using different methods. The twitter archive file which was directly downloaded. The images prediction file was downloaded through Requests library. This was done through the help of the URL which was already provided. The method of gathering the third dataset however, was slightly different. I had to get authorization from twitter to get access to their api to be able to gather the tweets from the Tweepy library. After being authorized, I was able to gather the tweets through the API keys provided by twitter. The data I gathered contained the retweet and favorite counts for the tweets. This concluded the gathering step. I then proceeded to the assessment of the 3 datasets I gathered.

Two types of assessments were to be performed. The first one was through visual means. I loaded all 3 datasets and scanned them visually to identify any quality and tidiness issues. For better experience while visually assessing, I opted to load the dataframes on Jupyterlab. Since Jupyterlab doesn’t collapse the rows, it was really convenient to scan through the rows of data. I was able to identify that the time_stamp column in the twiter_archive dataset wasn’t readable and could be segregated into separate date and time columns which could later be helpful in the analysis phase of the project. I also noticed that NaN values had been incorrectly represented as None which would result in pandas classifying them as non-null data instead of null. There were also some retweets and replies included within the datasets which had to be discarded as the instruction states to only deal with original tweets with images and not replies and retweets. Another issue I noticed was that the doggo, floofer, pupper, and puppo columns could be categorized under a single parent column instead of each being a column on its own. These were some of the quality and tidiness issues I was able to identify visually.

After visually assessing the data, I proceeded to perform programmatic assessment. I used various pandas methods such as info(), describe(), duplicated(), shape, sample() and isnull() among others. I noticed some fields had incorrect data types such as the timestamp column in the twitter_archive dataset. Some invalid names were present under the name column as well. Another issue I found is that there were some outlier values in the rating_numerator and rating denominator columns. In the project overview, it was stated that the rating_numerator values for the majority of the entries was 10. Any value apart from 10 is likely to be inserted by mistake. Since it would be impossible to detect each and every quality issue and tidiness issue, I ended my assessment here and proceeded to the cleaning phase.

During cleaning, each and every quality and tidiness issue was dealt with. The data types were corrected, retweets and replies were discarded resulting in original tweets only. Unneccessary columns were dropped as well. Filtering of the dataset was also done accordingly. Outliers were also removed as well. As far as tidiness is concerned, the datasets were merged into a single cleaned master dataset after the quality issues had been handled.

## Key Insights from the analysis

- There is a high positive correlation between the retweets and likes. Higher number of retweets means more likes and the vice versa.
- The most common rating given to the dogs is 12 followed by 10, 11 and 9.
- The most liked tweet is of a Labrador Retriever.
- The least liked tweet is of English setter breed.
- As for the accuracy of the image prediction algorithm, the algorithm has been able to correctly label 74.23% of the tweets as dog breeds.

## Resources
- [WeRateDogs Twitter archive](https://d17h27t6h515a5.cloudfront.net/topher/2017/August/59a4e958_twitter-archive-enhanced/twitter-archive-enhanced.csv)
- [Images predictions file](https://d17h27t6h515a5.cloudfront.net/topher/2017/August/599fd2ad_image-predictions/image-predictions.tsv)
- [Additional Twitter data](https://video.udacity-data.com/topher/2018/November/5bf60fc9_tweet-json/tweet-json.zip)

