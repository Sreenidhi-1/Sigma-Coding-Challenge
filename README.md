# SIGMA INTERNSHIP CODING CHALLENGE 

### Goal

We want to build a model to decide whether to place a buy trade for day d+1 to maximize the portfolio value.

### Data Acquistion

Extracted the daily close prices of Apple stock (sid=’AAPL’) for the year 2023 from the freely available us-stock price data in Quantrocket

## StockTrading Class

The `StockTrading` class contains the following key functions:

1. **classify_states()**: Calculates daily returns and classifies them into market states (Bear, Flat, Bull).

2. **find_portfolio()**: Finds the portfolio value of the day and collects optimal buy indices.

3. **probability_distribution()**: Computes the transition probability matrix for moving between different market states.

4. **output()**: Displays the portfolio value, optimal buy indices, buy dates, and visualized transition probability matrix.

5. **predict()**: Predicts whether to place a buy order trade on certain dates, considering conditions such as weekends.

## Output

The output of the model includes:

- **Portfolio Value (V(N))**: The calculated portfolio value.

- **Optimal Buy Indices**: Indices of the days where it is optimal to place a buy order.

- **Buy Dates**: Corresponding dates on which the stock should be bought.

## Time Series Forecasting

### Components

The model checks for Trend, Seasonality, and Residual components in the data, with the following results:

- **Trend**: Increasing trend observed.
- **Seasonality**: No seasonality detected.
- **Residuals**: No residuals found.

### Testing Stationarity

The stationarity of the data is checked using KPSS and Dickey Fuller tests.

### ARIMA Model

The AutoRegressive Integrated Moving Average (ARIMA) model is chosen after comparing with other models like LSTM, Prophet, and Exponential Smoothing. Key ARIMA parameters are (1, 1, 18), and the Root Mean Squared Error (RMSE) value is 2.347.

## Prediction

To make predictions, input any date of the format (YYYY-MM-DD). The model calculates the number of days between the last date in the dataset and the given date. This is used as steps to forecast using the ARIMA model. The `StockTrading` model then uses the predicted dataframe to check conditions and predict whether the stock can be bought on the specified day.

---

