# NLP for Stock Trend Forecasting

## Project Summary
An ensemble **RNN-LSTM-GRU** model integrating **attention** to forecast stock price with financial news headline from Reuters and other websites.

## Data Collection and Data Pre-processing
We used an existing dataset including financial news and stock prices in days, and added OECD economic indicators to the datasets to expect a better performance. 

<img width="479" alt="image" src="https://user-images.githubusercontent.com/18302400/215399484-aa537bb9-5789-425d-958d-144f783be924.png">

## Split Time-Series Data

Since we deal with time series forecasting, we use the financial news and stock prices of the past 10 days as a rolling window to predict the price of the next trading day, and we split dataset into training/validation/test datasets.

<img width="477" alt="image" src="https://user-images.githubusercontent.com/18302400/215399623-2d768057-1a8e-4f33-9f38-ac57021d3bb0.png">

## Ensemble Learning

- **Why?** Each base model has its pros and cons, we aspire to fuse all the decisions to further improve prediction results.
- **How?** We choose Blending as our ensemble learning method since it reduces generalization error reduction. After we obtain the predictions of the validation data for all four base models, we combine them into a new training dataset. This new dataset will be passed to the second level to train the meta-learner.

<img width="809" alt="image" src="https://user-images.githubusercontent.com/18302400/215400679-7103d5d3-0bb4-4f0a-96a8-aa24c4439f29.png">


## Evaluation and Result
<img width="460" alt="image" src="https://user-images.githubusercontent.com/18302400/215400880-b92c6dbe-ae71-4ebf-82eb-729273cafe35.png">

## Result and Conclusion
- The 4-model Ensemble model outperforms all four base models.
- The 4-model Ensemble model also has better precision score than the 2-model Ensemble model does.
- Decreased MSE by 12% compared to recent papers by leveraging sentiment and OECD economic indicators.

<img width="476" alt="image" src="https://user-images.githubusercontent.com/18302400/215400932-dddf47e5-7c16-45a9-a7f7-72c6b1bb5857.png">

## Future Research
- implement a reinforcement learning model as the second-level model
- change the historical windows dynamically based on the type of news
- increase the size of training dataset by integrating data from other sources

## Notes
This project was developed and ran on Google CoLab. Thus, to run this project successfully, make sure to specify the correct path to your drive before running our code. To be more specific, after clone/download our source code to CoLab, modify and run the following code as the first cell of each notebooks:

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
