## Pipeline Description

### Module 1: finance_sentiment_score
- **Class `SentimentScoreAnalyzerCSV`**:
  - **Initialization**: Initializes a sentiment analyzer with specific keywords related to geopolitical, environmental, and economic events. These keywords are associated with sentiment scores, reflecting their likely impact on market sentiment.
  - **Keyword Randomization**: Randomizes sentiment scores around the base values to capture slight variability.
  - **Article Mapping**: Checks if an article contains relevant keywords, mapping it to a specific stock symbol.
  - **Sentiment Scoring for DataFrame**: For each headline in a dataset, calculates sentiment scores if keywords are detected. Average scores are computed for each row, saved as "compound sentiment score" in the DataFrame, and exported to CSV.

### Module 2: news_preliminary_data_exploration
- **Setup and Data Loading**: Loads precomputed sentiment scores and stock data for a list of stock symbols (`GOOG`, `MSFT`, `NVDA`, `AMZN`, `AAPL`) into separate dictionaries.
- **Date Conversion and Filtering**: Converts and filters dates in both sentiment and stock data to focus on a specified range (`2006-06-01` to `2016-06-01`).
- **Data Alignment**: Retains only matching dates across sentiment and stock data to ensure data consistency for analysis.
- **Price Difference Calculation**: Computes daily price differences (`Close - Open`) for each stock symbol, which can be used to study the relationship between sentiment and stock price movements.

This pipeline enables a comprehensive analysis by linking sentiment scores from news articles to daily stock performance, allowing for the study of sentiment's impact on financial markets.
