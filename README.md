# 📈 Multivariate Time Series Forecasting for Stock Prediction using LSTM

## Overview

This project explores **multivariate time series forecasting** for stock market prediction using **Deep Learning (LSTM networks)**. The model learns temporal dependencies from historical stock data to predict future values of multiple variables including:

- Open
- High
- Low
- Close
- Volume

The goal of this project was to understand and implement a **deep learning pipeline for financial time-series data**, including preprocessing, sequence generation, training, and evaluation.

This project was developed as part of my journey transitioning from a **Physics background into Data Science and Machine Learning**.

---

## Problem Statement

Stock markets are complex systems influenced by many factors. Traditional regression methods often struggle to capture **temporal dependencies** present in financial data.

Recurrent Neural Networks (RNNs), particularly **Long Short-Term Memory (LSTM) networks**, are designed to capture such sequential relationships.

The objective of this project is to:

- Learn temporal patterns from historical stock data
- Use **multivariate features** instead of a single variable
- Forecast future stock behavior using deep learning

---

## Dataset

The dataset used is historical **Apple (AAPL) stock market data**, containing:

| Feature | Description |
|------|------|
| Open | Opening price |
| High | Highest price |
| Low | Lowest price |
| Close | Closing price |
| Adj Close | Adjusted closing price |
| Volume | Number of shares traded |

The data is treated as a **multivariate time series**.

---

## Methodology

### 1. Data Preprocessing

Steps performed:

- Converted the **Date column to datetime**
- Set **Date as index**
- Performed **chronological train-test split** to avoid data leakage
- Applied **MinMax scaling**
- Scaling formula used: x_scaled = (x - x_min) / (x_max - x_min)
---

### 2. Sequence Generation

To train the LSTM model, the data was converted into **sliding window sequences**.

Example:Day 1–100 → predict Day 101
Day 2–101 → predict Day 102
Day 3–102 → predict Day 103


Window size used: 100 timesteps


---

### 3. Model Architecture

The deep learning architecture consists of stacked LSTM layers with dropout for regularization.
Input Sequence
↓
LSTM Layer
↓
Dropout
↓
LSTM Layer
↓
Dropout
↓
LSTM Layer
↓
Dense Output Layer

Framework used:

- **TensorFlow / Keras**

---

## Model Training

Training configuration:

| Parameter | Value |
|------|------|
| Optimizer | Adam |
| Loss Function | Mean Squared Error |
| Epochs | 50 |
| Batch Size | 32 |
| Early Stopping | Enabled |

Early stopping was used to prevent **overfitting**.

---

## Evaluation Metrics

The model performance is evaluated using:

- **MAE** – Mean Absolute Error  
- **RMSE** – Root Mean Squared Error  
- **MAPE** – Mean Absolute Percentage Error  

These metrics measure the difference between predicted and actual values.

---

## Results

The model successfully learns the **general trend of stock price movements**. However, certain challenges remain:

- Financial markets are inherently noisy
- Volume predictions can occasionally become **negative due to scaling and model extrapolation**
- Predicting multiple variables simultaneously increases complexity

Despite these challenges, the model demonstrates the ability to capture **temporal patterns in stock data**.

---

## Key Learnings

This project helped me understand:

- Multivariate time series forecasting
- Data scaling and inverse transformations
- Sliding window sequence generation
- LSTM architecture and training
- Handling data leakage in time series
- Model evaluation techniques

---

## Limitations

Some limitations of the current implementation:

- Financial markets are influenced by external factors not included in the dataset
- Technical indicators (RSI, MACD, etc.) were not included
- Volume predictions may become negative due to model extrapolation
- Hyperparameter tuning could further improve performance

These are potential areas for improvement in future work.

---

## Future Improvements

Planned enhancements:

- Add **technical indicators** (RSI, MACD, Moving Averages)
- Experiment with **GRU networks**
- Implement **Transformer-based time-series models**
- Use **walk-forward validation**
- Predict **close price specifically instead of all features**

---

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-Learn
- TensorFlow / Keras

---

## Repository Structure
project/
│
├── data/
│ └── AAPL.csv
│
├── notebook/
│ └── stock_prediction.ipynb
│
├── README.md


---

## Author

Achu  
Physics Graduate | Aspiring Data Scientist  

Interested in:

- Machine Learning
- Deep Learning
- Time Series Forecasting
- Data Science Research

---

⭐ If you found this project interesting, feel free to star the repository.
