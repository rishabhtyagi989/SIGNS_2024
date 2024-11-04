## Pipeline Description for Stock News Sentiment Analysis

### Module 1: finance_sentiment_scores
- **Class `SentimentScoreAnalyzer`**:
  - **Initialization**: Sets up keywords and stock symbol for focused analysis using `SentimentIntensityAnalyzer` for sentiment scoring.
  - **Article Mapping**: Maps articles to the relevant stock symbol if specified keywords are present in the title or body text.
  - **Text Fetching**: Retrieves article text from a URL, handling errors for unauthorized or forbidden access.
  - **Sentiment Scoring**: Iterates through news data, fetches article text, and calculates sentiment scores if relevant keywords are found. Adds scores to a DataFrame and saves to CSV.
- **Data Loading**: Reads IT-related news data from a CSV file into a DataFrame `df_it`.

### Module 2: stock_news_preliminary_data_exploration
- **Data Loading**: Loads sentiment and stock price data for specified stocks (`GOOG`, `MSFT`, `NVDA`, `AMZN`, `AAPL`) from CSV files into separate dictionaries.
- **Date Filtering**: Filters sentiment and stock data based on a defined date range (`2011-05-02` to `2024-03-15`).
- **Data Alignment**: Retains only intersecting dates across sentiment and stock data for each stock symbol.
- **Calculate Price Difference**: Computes daily price difference (`Close - Open`) for each stock and stores it in a dictionary.
- **Sort IT News Data**: Converts publication dates to datetime format, sorts `df_it` by date, and removes duplicates.

This pipeline integrates sentiment scores from news articles with stock price data to facilitate analysis of the relationship between market sentiment and stock performance.
