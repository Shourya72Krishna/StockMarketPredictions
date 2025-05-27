# 📈 Stock Market Prediction using Machine Learning

This project applies machine learning to predict future stock prices based on historical data from multiple CSV files stored inside a ZIP archive. Each CSV represents data for a specific stock.

## 🔍 Project Overview

- Loads multiple stock data files from a ZIP archive.
- Preprocesses and selects only numeric data columns.
- Creates lag features and targets for next-day closing price.
- Trains a machine learning model (**HistGradientBoostingRegressor**) for each stock.
- Evaluates model performance using **Mean Squared Error (MSE)** and **R² score**.
- Visualizes actual vs predicted closing prices for each stock.

## 🗂️ Input Data

- Input ZIP file: `StockMarket.zip`
- Each CSV file contains daily stock data with columns like:
  - `Open`, `High`, `Low`, `Close`, `Volume`, `Turnover`, etc.

## 📊 Features Used

- Selected only numeric columns.
- Created lag features for `Close`:
  - `Close_lag_1`, `Close_lag_2`, `Close_lag_3`
- Target column: `Close_next` (next day's closing price)

## ⚙️ Machine Learning Model

- **Model Used**: `HistGradientBoostingRegressor` from scikit-learn
- Chosen for its speed and efficiency with large datasets
- Features were standardized using `StandardScaler`

## 📈 Metrics

- **Mean Squared Error (MSE)**: Measures average squared difference between predictions and actual values.
- **R² Score**: Indicates how well predictions approximate actual values (closer to 1 is better).

## 📉 Example Output

- **Before Optimization**:
  - MSE: ~11,000,000  
  - R²: ~0.08 (very low)

- **After Using Gradient Boosting**:
  - MSE: ~30,000  
  - R²: ~0.9975 (very high accuracy)

## 🖼️ Visualization

- Plots show **Actual vs Predicted** closing prices.
- Separate plot for each CSV file.
- Blue: Actual closing prices  
- Light Red: Predicted closing prices

## 🚀 How to Run

1. Place your `StockMarket.zip` in the working directory.
2. Make sure it contains multiple `.csv` files with stock data.
3. Run the Python script provided.
4. View performance metrics and individual prediction graphs for each stock.

## 📦 Requirements

Install the following Python packages before running:

```bash
pip install pandas matplotlib scikit-learn
