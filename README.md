# Airline Passenger Time Series Forecasting

A statistical forecasting project designed to predict future airline passenger traffic by analyzing historical trends, seasonality, and stationarity in time-indexed data.

## Overview

Time series forecasting is a crucial tool for capacity planning and resource allocation in the aviation industry. This project analyzes the classic AirPassengers dataset, covering 144 months of data. The workflow includes transforming the data into a stationary series, decomposing components, and preparing for predictive modeling.

## Dataset

- **Source:** Classic Airline Passengers dataset (`26_AirPassengers_dataset.csv`).
- **Time Range:** January 1949 to December 1960.
- **Key columns:**
  - `Month`: The time index (YYYY-MM).
  - `#Passengers`: The total count of international airline passengers (thousands).

## Objectives

- Perform **Time Series Decomposition** to isolate Trend, Seasonality, and Residuals.
- Test for **Stationarity** using the **Augmented Dickey-Fuller (ADF) Test**.
- Apply data transformations (Log scaling, Moving Averages) to stabilize variance and mean.
- Analyze **Autocorrelation (ACF)** and **Partial Autocorrelation (PACF)** plots to identify model orders.
- Forecast passenger counts for the subsequent 12-month period.

## Methods and Analysis

The project follows a rigorous statistical forecasting pipeline:

- **Data Preprocessing**
  - Converting the `Month` column to a datetime object and setting it as the index.
  - Initial visualization to identify the upward trend and multiplicative seasonality.

- **Stationarity Testing & Transformation**
  - **Rolling Statistics:** Plotting rolling mean and standard deviation to visually check for stationarity.
  - **ADF Test:** A formal statistical test where a p-value > 0.05 indicates non-stationary data.
  - **Differencing:** Subtracting moving averages or lagged values to remove trends.



- **Model Identification**
  - Utilizing **ACF (Autocorrelation Function)** to determine the MA (Moving Average) components.
  - Utilizing **PACF (Partial Autocorrelation Function)** to determine the AR (Autoregressive) components.



- **Forecasting**
  - Predicting the passenger count for the next 12 months based on the learned patterns of the previous 12 years.

## Tech Stack

- **Language:** Python 3
- **Libraries:**
  - `pandas` and `numpy`: For time-indexed data manipulation.
  - `matplotlib` and `seaborn`: For visualizing trends and seasonal patterns.
  - `statsmodels`: For ADF testing, seasonal decomposition, and ACF/PACF plotting.
- **Environment:** Jupyter / Google Colab

## How to Run

1. **Clone this repository:**
   ```bash
   git clone [https://github.com/](https://github.com/)<your-username>/airline-passenger-forecasting.git
   cd airline-passenger-forecasting

2. *Create and activate a virtual environment (optional but recommended):*
   python -m venv .venv
   source .venv/bin/activate  # On Windows: .venv\Scripts\activate

3. *Install dependencies:*
   pip install pandas numpy seaborn matplotlib statsmodels

4. Ensure the dataset is present: Place 26_AirPassengers_dataset.csv in the root folder.

5. *Open the notebook:*
   jupyter notebook 26_TimeSeries_Project.ipynb
