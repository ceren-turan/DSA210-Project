# DSA210-Project
## Motivation
This project aims to examine if public sentiment expressed on social media platforms such as Reddit or Twitter/X can anticipate actual market shifts, potentially offering predictive insights for investment decisions.\
The findings of this project will establish whether “wisdom of the crowd” on financial social media measurably affects stock prices, and will uncover patterns that might guide investment strategies.

## Hypotheses
**Null Hypothesis:** There is no statistically significant relationship between social media sentiment about companies and their subsequent stock price movements within a 1-3 day time frame.\
<br/>
**Alternative Hypothesis:** Social media sentiment about companies has a statistically significant relationship with subsequent stock price movements, where positive sentiment correlates with positive returns and negative sentiment correlates with negative returns within a 1-3 day time frame.

## Data Sources and Collection Methods
<ins>Primary Data Sources</ins>
1. Reddit Data:
+ **Focus:** Posts about selected companies on the "r/wallstreetbets", "r/stocks", "r/investing" Subreddits
+ **Data to Collect:** Post titles, content, number of comments, upvote ratios, timestamps
+ **Collection Method:** Reddit API (using PRAW library in Python)

2. Twitter/X Data:
+ **Focus:** Tweets mentioning selected company tickers/names and financial hashtags
+ **Data to Collect:** Tweet text, number of likes and retweets, timestamps
+ **Collection Method:** snscrape library in Python (could also use Twitter API)

3. Stock Market Data:
+ **Data to Collect:** Daily open, high, low, close prices, and trading volume of selected companies stocks
+ **Collection Method:** Yahoo Finance API

<ins>Enrichment Data Sources</ins>
1. Market Index Data:
+ **Data to Collect:** NASDAQ, S&P 500 index values
+ **Collection Method:** Yahoo Finance API

## Planned Data Analysis Methods and Tools
<ins>1. Data Collection and Preprocessing:</ins>
+ Clean and preprocess text data
+ Extract company tickers and names from text data

<ins>2. Sentiment Analysis:</ins>
+ Apply NLP (Natural Language Processing) techniques to categorize sentiment from posts/tweets/comments as positive, negative, or neutral\
Tool options: VADER (Lexicon-based analysis tool) or FinBert (NLP model to analyze sentiment on financial text)
+ Aggregate sentiment to get an overall sentiment score for each company using pandas

<ins>3. Visualization:</ins>
+ Using Matplotlib and Seaborn to visualize the correlations between the variables (sentiment scores and stock price shifts)

<ins>4. Correlation Analysis (Hypothesis Testing):</ins>\
Using the visualizations;
+ Examine correlations between sentiment scores and stock price movements
+ Look for time lags to determine whether sentiment change precede price changes
  
  
   
