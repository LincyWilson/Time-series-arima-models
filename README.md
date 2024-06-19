# Champagne Sales Forecasting

## Project Overview

This project involves time series analysis and forecasting of monthly champagne sales data from Perrin Frères, spanning from January 1964 to September 1972. Using various statistical and machine learning techniques, the goal is to understand the trends, seasonality, and forecast future sales. The project employs methods such as ARIMA and Seasonal ARIMA (SARIMA) for predictive modeling.

## Data

The dataset used in this project is `perrin-freres-monthly-champagne.csv`, which contains monthly sales data with the following columns:

- `Month`: Date of the observation
- `Sales`: Number of champagne sales

## Exploratory Data Analysis (EDA)

1. **Yearly Sales Trend**:
   - A bar plot showing the average sales per year indicates a gradual increase in sales from 1964 to 1969, followed by fluctuations between 1970 and 1972.

2. **Monthly Sales Trend**:
   - A bar plot showing the average sales per month reveals that sales are relatively constant from January to July, dip in August, and then rise sharply from September to December.

3. **Monthly Sales by Year**:
   - A heatmap of monthly sales for each year highlights the seasonal pattern in sales.

4. **Sales Time Series Plot**:
   - A line plot of sales over time shows the overall trend and seasonality in the data.

## Time Series Decomposition

- Decomposed the time series into trend, seasonal, and residual components using multiplicative decomposition, highlighting the underlying patterns in the sales data.

## Stationarity Check

- Applied the Augmented Dickey-Fuller (ADF) test to check for stationarity.
  - The original series was non-stationary (p-value > 0.05).
  - Differencing the series made it stationary (p-value < 0.05).

## Autocorrelation and Partial Autocorrelation

- Plotted the ACF and PACF of the differenced series to identify potential AR and MA terms for the ARIMA model.

## ARIMA Model

- Fitted an ARIMA(1,1,1) model to the differenced data.
- The model summary and diagnostics indicated a decent fit, but it did not capture seasonality.

## Seasonal ARIMA (SARIMA) Model

- Fitted a SARIMA(1,1,1)x(1,1,1,12) model to account for seasonality.
- The model summary and diagnostics showed a better fit.

## Forecasting

- Forecasted the next 24 months (2 years) using the SARIMA model.
- Plotted the forecasted values alongside the actual sales data, showing that the model captures the seasonal pattern well.

## How to Run the Project

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/yourusername/champagne-sales-forecasting.git
   cd champagne-sales-forecasting
2. **Run the Notebook**:
Open and run the Jupyter notebook champagne_sales_forecasting.ipynb to reproduce the analysis and forecasts.

## Requirements
pandas
numpy
matplotlib
statsmodels
seaborn
Jupyter Notebook

## Results
The ARIMA model provided a preliminary forecast but did not account for seasonality.
The SARIMA model effectively captured both trend and seasonality, providing a reliable forecast for future sales.

## Conclusion
The project successfully demonstrates the application of time series analysis and forecasting techniques on historical sales data. The SARIMA model proved to be effective in capturing seasonal patterns and providing accurate forecasts, suggesting that the champagne sales follow a predictable seasonal pattern.

## Future Work
Experiment with other time series models such as Prophet, LSTM, and other advanced forecasting techniques.
Incorporate additional external factors (e.g., marketing campaigns, economic indicators) to improve the model accuracy.

## Contributing
Contributions are welcome! Please open an issue or submit a pull request for any improvements.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
