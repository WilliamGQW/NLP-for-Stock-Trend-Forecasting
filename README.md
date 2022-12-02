# CSCI544 Group 15 - NLP for Stock Trend Forecasting

## Notes
Our project is developed and ran on Google CoLab. Thus, to run this project successfully, make sure to specify the correct path to your drive before running our code. To be more specific, after clone/download our source code to CoLab, modify and run the following code as the first cell of each notebooks:

```
from google.colab import drive
drive.mount('/content/drive')
%cd '/content/drive/<your drive>/csci544-project'
```

## Directory Tree:
```
.
├── Group15_NLP_Stock_Forecasting_with_oecd.ipynb               # Our project's step-by-step process with OECD indicators
├── Group15_NLP_Stock_Forecasting_without_oecd.ipynb            # Our project's step-by-step process without OECD indicators
├── us_financial_news_articles_2018.csv                         # News data, saved in Cloud Drive dut to its large size 821.6 MB
├── us_financial_news_articles_2018_with_sentiment.csv          # News data with sentiment scores, saved in Cloud Drive dut to its large size 827.5 MB
├── LICENSE
├── README.md
├── data                                                        # Data directory
│   ├── SP500.csv                                               # SP500 Index
│   ├── large_data
│   │   ├── us_financial_news_articles_2018.csv                 # News data, large size 821.6 MB, saved in Cloud Drive
│   │   ├── us_financial_news_articles_2018_with_sentiment.csv  # News data with sentiment scores, large size 827.5 MB, saved in Cloud Drive
│   ├── oecd_data                                               # OECD indicators
│   │   ├── BCI.csv
│   │   ├── CCI.csv
│   │   └── CLI.csv
│   ├── source_price.csv                                        # Aggregated stock data with News sentiment scores
│   ├── source_price_sentiment_oecd.csv                         # Aggregated stock data with News sentiment scores and OECD indicators
│   └── stockdata
└── data_preprocessing
    ├── 1_news_data_loading.ipynb                               # News data loading
    ├── 2_feature_extraction.ipynb                              # Sentiment feature extraction
    ├── 3_data_processing.ipynb                                 # Sentiment aggregation
    └── 4_OECD_data_aggregation.ipynb                           # OECD aggregation
```

## References
<a id="1">[1]</a > 
Xinyi L., Yinchuan L., Hongyang Y., Liuqing Y., Xiaoyang L. 2019. DP-LSTM: Dif- ferential Privacy-inspired LSTM for Stock Prediction Using Financial News. ArXiv, abs/1912.10806

<a id="2">[2]</a > 
Yang L., Yi P. 2022. A novel ensemble deep learning model for stock prediction based on stock prices and news. International Journal of Data Science and Analytics, 13(2), 139-149