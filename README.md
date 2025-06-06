# Bitcoin Price Forecasting & Market Segmentation

This project implements a dual-task deep learning framework to **forecast Bitcoin (BTC-USD) price changes** and **segment market regimes** using hourly data from the Coinbase exchange.

## Project Overview

Bitcoin's volatile nature makes it difficult to model with traditional forecasting tools. This project:
- Segments the time series into market states: Tight/Broad Bull/Bear Channels, and Ranges.
- Forecasts percentage changes in OHLC prices over the next 24 hours using the past 48 hours of data.

## Dataset

- Source: Coinbase BTC-USD  
- Frequency: Hourly  
- Period: July 2015 – January 2024  
- Records: ~82,944

## Preprocessing

- Compute percentage change of OHLC values
- Calculate technical indicators: MA20, MA50, RSI, ATR
- Segment data using log-price slope and ATR ratio thresholds
- Normalize features using `StandardScaler`
- One-hot encode segmentation classes

## Models Used

### Forecasting
- LSTM
- CNN-LSTM
- Attention-based LSTM (Bahdanau attention)

### Segmentation
- LSTM
- Bi-directional LSTM

## Evaluation Metrics

| Task         | Metric           | Best Model           |
|--------------|------------------|----------------------|
| Forecasting  | MAE, MSE, R²     | CNN-LSTM             |
| Segmentation | Accuracy, F1     | Bi-directional LSTM  |

Note: Forecasting percentage changes is more difficult than predicting absolute prices due to Bitcoin’s inherent randomness and volatility.

## Results

- Forecasting MAE: ~0.454  
- Segmentation Accuracy: ~95%  
- CNN-LSTM achieved the best performance for price prediction  
- Bi-LSTM performed best for market regime classification

## Future Work

- Integrate Transformer architectures for improved performance
- Explore risk-aware or stochastic optimization strategies
- Use forecasts as directional signals, not standalone trading systems

## Contact

**Monib Saadi**  
edusaamon001@fh-kaernten.at  
FH Kärnten

