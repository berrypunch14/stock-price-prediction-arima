# Stock Price Prediction using ARIMA

## Project Overview

This project analyzes and predicts the stock prices of Nestlé India Limited using time series forecasting techniques, with a focus on the ARIMA (Autoregressive Integrated Moving Average) model. The goal is to build a model that can capture the underlying patterns in historical stock data to make future price predictions.

## Dataset

The dataset used in this project is the historical stock price data for Nestlé India Limited, obtained from a CSV file (`NESTLEIND.csv`). The data includes daily stock prices with features like:
- **Date**: The trading date.
- **Open**: The opening price of the stock.
- **High**: The highest price of the stock during the day.
- **Low**: The lowest price of the stock during the day.
- **Close**: The closing price of the stock.
- **VWAP**: Volume Weighted Average Price.
- **Volume**: The number of shares traded.

## Methodology

The project follows these key steps:

1.  **Data Loading and Preprocessing**: The dataset is loaded using pandas, and initial data cleaning is performed. This includes handling missing values by dropping the 'Trades' column which had null entries, and setting the 'Date' column as the index.

2.  **Exploratory Data Analysis (EDA)**: The historical stock prices, particularly the Volume Weighted Average Price (VWAP), are visualized to understand trends, seasonality, and potential stationarity issues.

3.  **Feature Engineering**: Rolling window statistics (mean and standard deviation) are calculated for features like 'High', 'Low', 'Volume', and 'Turnover' over 3-day and 7-day periods to create lag features. These new features help the model capture recent trends.

4.  **ARIMA Modelling**: The `pmdarima` library's `auto_arima` function is used to automatically determine the optimal parameters (p, d, q) for the ARIMA model. The model is trained on the initial 2400 data points.

5.  **Forecasting and Evaluation**: The trained ARIMA model is used to forecast the stock prices for the remaining data points. The forecasted values are then plotted against the actual 'VWAP' to assess the model's performance visually.

## Technologies and Libraries Used

-   **Python**: The core programming language for the project.
-   **pandas**: For data manipulation and analysis.
-   **NumPy**: For numerical operations.
-   **Matplotlib & Seaborn**: For data visualization.
-   **Plotly**: For creating interactive plots.
-   **pmdarima**: For fitting the ARIMA model.
-   **SciPy**: For statistical analysis.

## How to Run the Code

1.  Clone the repository:
    ```bash
    git clone [https://github.com/berrypunch14/stock-price-prediction-arima.git](https://github.com/berrypunch14/stock-price-prediction-arima.git)
    ```
2.  Install the required libraries:
    ```bash
    pip install pandas numpy matplotlib seaborn plotly pmdarima scipy
    ```
3.  Run the Jupyter Notebook:
    ```bash
    jupyter notebook stock-price-prediction-arima.ipynb
    ```

## Results

The project successfully implements an ARIMA model to forecast stock prices. The visualisation of the forecast shows how the model's predictions compare with the actual stock prices.

![Screenshot_29-7-2025_21308_](https://github.com/user-attachments/assets/9aaeb161-2689-4098-9cc9-d82635c251b6)

## Future Improvements

-   Experiment with other time series models like SARIMA, LSTMs, or Prophet.
-   Incorporate more features, such as market sentiment from news articles.
-   Perform a more rigorous evaluation of the model using metrics like Mean Absolute Error (MAE) or Root Mean Squared Error (RMSE).
