# DSA210-Project
## Motivation
This project aims to examine if public sentiment expressed on social media platforms such as Reddit can anticipate actual market shifts, potentially offering predictive insights for investment decisions.\
The findings of this project will establish whether “wisdom of the crowd” on financial social media measurably affects stock prices, and will uncover patterns that might guide investment strategies.

## Hypotheses
**Null Hypothesis:** There is no statistically significant relationship between Reddit sentiment about cryptocurrencies and their subsequent stock price movements within a 1-day time frame.\
<br/>
**Alternative Hypothesis:** Reddit sentiment about cryptocurrencies has a statistically significant relationship with subsequent stock price movements, where positive sentiment correlates with positive returns and negative sentiment correlates with negative returns within a 1-day time frame.

## Data Sources and Collection Methods
Data collection occurs daily, building a longitudinal dataset for analysis.
<ins>Data Sources</ins>
1. Reddit Data:
+ **Collection Method:** Daily web scrape via BeautifulSoup of Chart Exchange (https://chartexchange.com/trends/reddit/mentions/cx-all/), a website which calculates Reddit sentiment and 1-day price returns from various cryptocurrency-focused subreddits.
+ **Data to Collect:** Ticker, type (stock or crypto), sentiment score, 1-day price-change estimate (for reference)

2. Price Returns:
+ **Data to Collect:** Next-day closing-price return for each cryptocurrency
+ **Collection Method:** Yahoo Finance API (via yfinance), pulling the previous day's close and the subsequent day's close 

## Data Processing Pipeline
1. Data Acquisition:
+ Daily scraping of Reddit sentiment from Chart Exchange (additionaly collecting 1-day price return data as reference)
+ Retrieval of corresponding cryptocurrency prive data from Yahoo Finance

2. Data Preprocessing:
+ Cleaning sentiment scores
+ Calculation of next-day returns
+ Removal of records with missing data points

3. Data Storage
+ Daily results are appended to a CSV file
+ This creates a growing longitudinal dataset for ongoing analysis

4. Visualization:
+ Daily scatter plots are generated to visualize the relationship between sentiment and returns
+ These visualizations provide feedback on daily patterns

## Correlation Analysis (Hypothesis Testing):
The primary statistical method employed is Pearson correlation analysis, which measures the linear relationship between two continous variables:
+ The independent variable is the Reddit sentiment score
+ The dependent variable is the next-day price return
+ Correlation coefficient (r) quantifies the strength and direction of the relationship
+ P-value determines statistical significance

Framework:
+ Significance level (α) is set at 0.05
+ If p-value < 0.05, the null hypothesis is rejected, indicating a statistically significant relationship
+ If p-value ≥ 0.05, the null hypothesis cannot be rejected

Longitudinal Perspective:
As data accumulates over time:
+ The statistical power of the test increases
+ The analysis becomes more robust against daily anomalies

## Results:
<ins>First Run</ins> (2025-04-24, 21.00)
+ Executed the code main.ipynb for the first time.
+ Scraped 18 crypocurrencies' sentiment scores and 24-hour price-change from Chart Exchange for 2025-04-24.
+ Appended ~19 rows to daily_crypto_sentiment.csv dated 2025-04-24.
+ Conducted Pearson correlation on this single-day sample (n ≈ 19), reported r and p, and displayed the scatter plot of sentiment vs. return.
<img width="763" alt="image" src="https://github.com/user-attachments/assets/6bf3ec31-13b9-4611-addd-33c5ab499480" />

<ins>Final Run</ins>
+ Reran the code, scraped ~19 new observations for 2025-04-25. (total n ≈ 38)
+ Appended these to the CSV, bringing the cumulative dataset to ~38 rows.
+ Performed the **overall** Pearson test across all observations (n ≈ 38) and updates the scatter plot to reflect the full sample.
<img width="753" alt="image" src="https://github.com/user-attachments/assets/5e21f5ef-8421-45cb-90d7-d5c684cc346b" />

## Limitations and Future Work:
+ Single-day horizon: So far, the code only measures 1-day returns. However, it may take longer than 24 hours for sentiment to fully feed into prices.
+ Hypothesis Test Result: To achieve more reliable and precise results, a larger sample size than currently available is needed. Given the time constraints so far, the dataset remains limited. Throughout the remainder of this project, the code will be continued to run daily -manually at present- to accumulate additional observations and increase sample size. As the sample grows, the statistical power of the hypothesis test will increase, yielding more accurate conclusions.

  
   
