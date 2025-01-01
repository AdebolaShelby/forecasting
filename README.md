# Time Series Forecasting and Seasonal Decomposition

This project builds models to forecast sales quantity, predict when stock will run out for different product categories using time series forecasting and ARIMA models, and perform seasonal decomposition analysis.

## Data Source

The dataset is generated synthetically for demonstration purposes. It includes various features such as date, sales quantity, stock remaining, product ID, and category.

## Steps

### 1. Generating Synthetic Data
- Generate synthetic data for sales and stock quantities.
- Create a DataFrame and save it as `enhanced_cro_data.csv`.

### 2. Data Preparation
- Filter the dataset for the Home Goods category.
- Group the data by date and sum the sales quantity.
- Ensure the date column is in datetime format.
- Convert the date index to monthly periods and strings.

### 3. Stock Calculation
- Calculate the average stock remaining at the end of each month.
- Ensure the date column is in datetime format.
- Convert the date index to monthly periods and strings.

### 4. Merge Sales and Stock Data
- Merge the sales and stock data on the monthly period.

### 5. Cumulative Stock Calculation
- Calculate the cumulative stock remaining.
- Define a threshold for low stock (e.g., 50 units).

### 6. Stockout Date Calculation
- Identify the first date when the cumulative stock remaining falls below the threshold.
- Print the earliest stockout date.

### 7. Time Series Analysis for Product_1
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

### 8. Seasonal Decomposition for Product_1
- Filter the dataset for Product_1.
- Group the data by date and sum the sales quantity.
- Ensure the date column is in datetime format.
- Set the date column as the index and set the frequency.
- Fill missing values using interpolation.
- Perform seasonal decomposition.
- Plot the seasonal decomposition results.

## Key Functions and Methods

- `pd.to_datetime()`: Converts a column to datetime format.
- `dt.to_period('M')`: Converts a datetime column to monthly periods.
- `groupby()`: Groups the data by a specified column.
- `cumsum()`: Calculates the cumulative sum of a column.
- `merge()`: Merges two DataFrames on a specified column.
- `ARIMA()`: Fits an ARIMA model to the data.
- `mean_squared_error()`: Calculates the mean squared error between actual and forecasted values.
- `seasonal_decompose()`: Performs seasonal decomposition on time series data.

## Findings

- **Stockout Date for Home Goods**: The earliest stockout date for the Home Goods category was identified based on the cumulative stock remaining falling below a threshold.
- **Best ARIMA Parameters for Product_1**: The best ARIMA parameters for Product_1 were found using a grid search, and the model was evaluated using RMSE.
- **Seasonal Decomposition for Product_1**: The seasonal decomposition analysis for Product_1 revealed the observed, trend, seasonal, and residual components of the sales quantity.


## Dependencies

- pandas
- numpy
- seaborn
- matplotlib
- statsmodels
- scikit-learn

## Usage

1. Ensure all dependencies are installed.
2. Run the notebook to generate synthetic data, filter data, calculate stock, and predict the stockout date.
3. Perform time series analysis and forecasting for Product_1.
4. Perform seasonal decomposition analysis for Product_1.

## Notes

- Adjust the `low_stock_threshold` value as needed based on specific requirements.
- Ensure the dataset contains the necessary columns: `date`, `sales_quantity`, `stock_remaining`, `category`, and `product_id`.