# Stock Sentiment Analysis on X

This Python script performs sentiment analysis on US stocks based on posts from platform X. It fetches recent posts mentioning stock cashtags (e.g., `$AAPL`), cleans the text, analyzes sentiment using TextBlob, and outputs the results in a table and CSV file.

## Features
- Fetches posts from X using the v2 API.
- Analyzes sentiment for popular US stocks (e.g., Apple, Microsoft, Tesla).
- Cleans text by removing URLs and special characters.
- Outputs average sentiment scores and saves them to a CSV file.

## Prerequisites
- Python 3.6 or higher
- An X Developer account with API credentials (see [Setup](#setup))

## Installation

1. **Clone the Repository** (if applicable):
   ```bash
   git clone https://github.com/yourusername/stock-sentiment-analysis.git
   cd stock-sentiment-analysis
   ```

2. **Install Required Libraries**:
   Run the following command to install the necessary Python packages:
   ```bash
   pip install tweepy textblob pandas
   ```

## Setup

1. **Obtain X API Credentials**:
   - Sign up for an X Developer account at [developer.x.com](https://developer.x.com).
   - Create a project and app in the Developer Portal.
   - Generate and note down the following credentials:
     - API Key
     - API Secret
     - Access Token
     - Access Token Secret
     - Bearer Token

2. **Configure the Script**:
   - Open `stock_sentiment.py` in a text editor.
   - Replace the placeholder credentials with your actual ones:
     ```python
     API_KEY = "your_api_key"
     API_SECRET = "your_api_secret"
     ACCESS_TOKEN = "your_access_token"
     ACCESS_TOKEN_SECRET = "your_access_token_secret"
     BEARER_TOKEN = "your_bearer_token"
     ```

## Usage

1. **Run the Script**:
   Execute the script from the command line:
   ```bash
   python stock_sentiment.py
   ```

2. **Output**:
   - The script will analyze sentiment for the stocks defined in the `stocks` dictionary (e.g., AAPL, MSFT, GOOGL, TSLA, AMZN).
   - Results will be printed to the console and saved to `stock_sentiment_analysis.csv`.

   Example output:
   ```
   Sentiment Analysis Results (as of 2025-03-10 12:34:56):
       stock  company     average_sentiment  post_count
   0   AAPL   Apple       0.1523            100
   1   MSFT   Microsoft   0.0876            100
   2   GOOGL  Google      0.1245            100
   3   TSLA   Tesla       0.1987            100
   4   AMZN   Amazon      0.0954            100
   ```

## Customization
- **Add More Stocks**: Edit the `stocks` dictionary in `stock_sentiment.py`:
  ```python
  stocks = {
      "NVDA": "NVIDIA",
      "JPM": "JPMorgan Chase"
  }
  ```
- **Adjust Post Count**: Modify `num_posts` in the `analyze_stock_sentiment` function call (default is 100).
- **Enhance Sentiment Analysis**: Replace `TextBlob` with a more advanced model like `FinBERT` for financial-specific sentiment (requires additional setup).

## Notes
- **API Limits**: The free X API tier has rate limits (e.g., 500,000 posts/month as of early 2025). Check your plan and adjust `num_posts` accordingly.
- **Sentiment Accuracy**: `TextBlob` provides basic sentiment analysis. For better results in a financial context, consider a pre-trained model like `FinBERT`.
- **Error Handling**: The script includes basic error handling; check the console for issues like rate limits or invalid credentials.

## Dependencies
- `tweepy`: For accessing the X API.
- `textblob`: For sentiment analysis.
- `pandas`: For data manipulation and output.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details (if applicable).

## Contributing
Feel free to submit issues or pull requests to improve the script!

