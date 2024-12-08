# StockMovementPrediction
Predict the movement of stock using data from subreddit 
Stock Movement Analysis Based on Social Media Sentiment
Step 1: Pulling the data from the Subreddits
•	Main aim in this step was to get the data from the subreddit using web scraping 
•	I used “praw” framework to extract the data
•	Challenges faced: No challenges, just had to create a an app with my account in reddit
•	Subreddits from which the data was scraped are -"StockMarket", "IndianStockMarket", "investing", "Stocks"
Step 2: Data Analysis:
•	Imported SentimentIntensityAnalyzer from vaderSentiment
•	Calculated the compound score where -1 was most negative and +1 was the most positive
•	Then calculated the sentiment of the title(heading of the post) subtext(discussion) separately and categorized them as negative, positive or neutral
•	Eliminate posts unrelated to stocks using keywords that are usually related to investing and stocks (e.g., memes or irrelevant discussions)
•	Removed unnecessary urls and emojis in the posts
•	Calculated the popularity indicators
•	Challenges faced: adding the popularity indicators back to our sentimentally analysed data as a column and clean it again 
•	Performed some EDA
Step 3: Prediction Model
•	This was the most challenging aspect of the project
•	First I split the data into training and testing data(80/20)
•	Then I noticed that the price up of each of my stocks were not calculated
•	Calculated the price up of each stock 
•	Combined this into a new data set called stock_data.csv
•	Now the challenge was to combine the sentiment analysis data and stock data so that they have the same format
•	I found out that the stock data that I pulled from yahoo finance can be joined with my previous dataset with the datetime feature. 
•	I changed the format of the datasets so that they match and combined them 
•	Now I could split it into train and test data
•	I used Logistic Regression and RandomForestClassifier.
•	There was a class imbalance hence my F1 and accuracy scores were 0
•	I had to resample using SMOTE 
•	After which I got good results from RandomForestClassifier
•	Challenges Faced: Combining different sources of data, resampling data 
