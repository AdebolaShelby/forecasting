# Time Series Forecasting

This project builds a model to forecast sales quantity and predict when stock will run out for different product categories using time series forecasting and ARIMA models.

## Steps

1. **Generating Synthetic Data**
    - Generate synthetic data for sales and stock quantities for demonstration purposes.

2. **Data Preparation**
    - Filter the dataset for the Home Goods category.
    - Group the data by date and sum the sales quantity.
    - Ensure the date column is in datetime format.
    - Convert the date index to monthly periods and strings.

3. **Stock Calculation**
    - Calculate the average stock remaining at the end of each month.
    - Ensure the date column is in datetime format.
    - Convert the date index to monthly periods and strings.

4. **Merge Sales and Stock Data**
    - Merge the sales and stock data on the monthly period.

5. **Cumulative Stock Calculation**
    - Calculate the cumulative stock remaining.
    - Define a threshold for low stock (e.g., 50 units).

6. **Stockout Date Calculation**
    - Identify the first date when the cumulative stock remaining falls below the threshold.
    - Print the earliest stockout date.

7. **Time Series Analysis for Product_1**
    - Filter the dataset for Product_1.
    - Group the data by date and sum the sales quantity.
    - Ensure the date column is in datetime format.
    - Convert the date index to monthly periods and strings.
    - Split the data into training and testing sets.
    - Define a function to evaluate ARIMA models.
    - Perform a grid search to find the best ARIMA parameters.
    - Fit the ARIMA model with the best parameters.
    - Forecast for the test period.
    - Calculate and print the RMSE for the test period.

## Key Functions and Methods

- `pd.to_datetime()`: Converts a column to datetime format.
- `dt.to_period('M')`: Converts a datetime column to monthly periods.
- `groupby()`: Groups the data by a specified column.
- `cumsum()`: Calculates the cumulative sum of a column.
- `merge()`: Merges two DataFrames on a specified column.
- `ARIMA()`: Fits an ARIMA model to the data.
- `mean_squared_error()`: Calculates the mean squared error between actual and forecasted values.

## Example Output

```
Earliest stockout date for Home Goods: 2023-01-01
Best ARIMA parameters for Product_1: (p, d, q) with RMSE: X.XX
RMSE for ARIMA model on Product_1: X.XX
```

## Dependencies

- pandas
- numpy
- matplotlib
- statsmodels
- sklearn

## Usage

1. Ensure all dependencies are installed.
2. Run the notebook to generate synthetic data, filter data, calculate stock, and predict the stockout date.
3. Perform time series analysis and forecasting for Product_1.

## Notes

- Adjust the `low_stock_threshold` value as needed based on specific requirements.
- Ensure the dataset contains the necessary columns: `date`, `sales_quantity`, `stock_remaining`, `category`, and `product_id`.