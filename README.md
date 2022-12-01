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
├── Group15_NLP_Stock_Forecasting_with_oecd.ipynb           # Our project's step-by-step process with OECD indicators
├── Group15_NLP_Stock_Forecasting_without_oecd.ipynb        # Our project's step-by-step process without OECD indicators
├── LICENSE
├── OECD_data_processing.ipynb                              # Data pre-processing
├── README.md
└── data                                                    # Data directory
    ├── SP500.csv                                           # SP500 Index
    ├── oecd_data                                           # OECD indicators
    │   ├── BCI.csv
    │   ├── CCI.csv
    │   └── CLI.csv
    ├── source_price.csv                                    # Aggregated stock data with News sentiment scores
    ├── source_price_sentiment_oecd.csv                     # Aggregated stock data with News sentiment scores and OECD indicators
    └── stockdata
```