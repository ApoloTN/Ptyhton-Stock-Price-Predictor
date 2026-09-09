# Simple Stock Price Predictor

A beginner machine learning project that explores stock price prediction using **PyTorch, Pandas, NumPy, yfinance, scikit-learn, and Matplotlib**.

The project downloads historical **Apple (AAPL)** market data and uses a **sliding-window approach** to provide previous price data to a PyTorch model, which then attempts to predict the next price.

> **Warning:** This project is strictly educational. The model produces inaccurate predictions and **should under no circumstances be used to predict actual stock prices or make investment decisions.**

## Overview

This project was created after I became more interested in investing and wanted to explore how machine learning could be applied to financial markets.

The goal was not to build a profitable trading system, but rather to gain practical experience working with machine learning and financial time-series data.

The project covers:

* Downloading historical stock data with `yfinance`
* Processing financial data with **Pandas** and **NumPy**
* Standardizing data using `StandardScaler`
* Creating training data using a **sliding-window approach**
* Building and training a neural network with **PyTorch**
* Evaluating predictions using **Root Mean Squared Error (RMSE)**
* Visualizing stock data and model predictions with **Matplotlib**
* Supporting both **CPU** and **CUDA-enabled GPU** execution

## How It Works

The model uses historical stock prices to create input sequences.

For example, given a window of previous prices:

```text
[Price 1, Price 2, Price 3, Price 4, Price 5]
```

the model attempts to predict:

```text
[Price 6]
```

The window then moves forward:

```text
[Price 2, Price 3, Price 4, Price 5, Price 6]
```

to predict the following price.

This process continues throughout the dataset, allowing the model to learn relationships between previous prices and the next price.

### Data Preprocessing

The historical data is standardized using scikit-learn's `StandardScaler` before being provided to the neural network.

This helps put the input values on a consistent scale and makes the data more suitable for training.

### Model

The project uses a simple PyTorch neural network designed as an introduction to neural networks and time-series prediction.

The model is intentionally basic. It does not incorporate many factors that influence real financial markets, such as:

* News
* Economic conditions
* Company fundamentals
* Market sentiment
* Trading volume
* Interest rates
* Broader market movements

Because of this, its predictions should not be interpreted as meaningful forecasts of future market prices.

## Technologies Used

| Technology       | Purpose                            |
| ---------------- | ---------------------------------- |
| **Python**       | Main programming language          |
| **PyTorch**      | Neural network and model training  |
| **Pandas**       | Data manipulation and analysis     |
| **NumPy**        | Numerical operations               |
| **yfinance**     | Downloading historical market data |
| **scikit-learn** | Data preprocessing and evaluation  |
| **Matplotlib**   | Data visualization                 |

## Hardware Acceleration

The project detects whether CUDA is available and can run PyTorch on a compatible NVIDIA GPU.

Otherwise, it falls back to the CPU.

```text
CUDA GPU available → GPU
CUDA unavailable   → CPU
```

This provides some practical experience with running PyTorch models across different hardware configurations.

## Evaluation

Model performance is evaluated using **Root Mean Squared Error (RMSE)**.

RMSE measures the typical size of prediction errors, with larger errors receiving greater weight.

The project also visualizes the actual and predicted prices to make it easier to see how closely the model follows the historical data.

## Installation

Clone the repository:

```bash
git clone <repository-url>
cd <repository-folder>
```

Install the required Python packages:

```bash
pip install torch pandas numpy yfinance scikit-learn matplotlib
```

Then run the project using the appropriate Python file or notebook included in the repository.

## Example Workflow

The general workflow is:

```text
Download AAPL Data
        ↓
Clean / Prepare Data
        ↓
Standardize Prices
        ↓
Create Sliding Windows
        ↓
Train PyTorch Model
        ↓
Generate Predictions
        ↓
Calculate RMSE
        ↓
Visualize Results
```

## Limitations

This project has significant limitations and is **not a financial forecasting system**.

The model:

* Uses a relatively small set of inputs
* Relies primarily on historical price information
* Uses a simple neural network architecture
* Does not account for external market factors
* Produces inaccurate predictions
* Has not been designed or tested for real-world trading

Financial markets are highly complex and cannot reliably be predicted simply by looking at previous prices.

**Do not use this project to make financial or investment decisions.**

## Purpose

The primary purpose of this project was to gain hands-on experience with:

* PyTorch
* Neural networks
* Pandas
* NumPy
* Data preprocessing
* `StandardScaler`
* Time-series data
* Sliding-window datasets
* Model training
* Model evaluation
* RMSE
* Data visualization
* GPU/CUDA support

It serves as an introductory machine learning project that combines programming, data science, and an area of personal interest in investing.

## Disclaimer

This project is for **educational purposes only**.

The predictions generated by this model are not reliable financial forecasts. Nothing in this project should be interpreted as financial advice, and the model should **under no circumstances be used to make investment or trading decisions**.

## README Generation

This README was generated with assistance from **GPT-5.6 Luna**.
