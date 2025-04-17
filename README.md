#  Wikipedia Web Traffic Time Series Forecasting

This project forecasts daily web traffic for Wikipedia pages using time series models like ARIMA, XGBoost, and LSTM. It combines classical statistical methods with advanced deep learning to analyze and predict user engagement trends across thousands of articles.

## Project Overview

- Predicts future page views for Wikipedia articles.
- Useful for capacity planning, content strategy, and analytics.
- Includes a Flask-based web interface to input article index and forecast date.

##  Dataset

- Sourced from [Kaggle: Web Traffic Time Series Forecasting](https://www.kaggle.com/competitions/web-traffic-time-series-forecasting).
- 145,000+ time series from July 2015 to December 2016.
- Columns include page name, access type, agent type, language, and daily views.
- Contains missing values, seasonality, and high variance across articles.

##  Models Used

### 1. Baseline Heuristics
- Mean/Median of recent values used as simple forecast.

### 2. Classical Models
- Moving Averages
- ARIMA (AutoRegressive Integrated Moving Average)

### 3. Machine Learning Models
- XGBoost / LightGBM using engineered time-based features.

### 4. Deep Learning
- LSTM with multi-input architecture.
- Embedding layers for categorical features (access type, agent, language).
- Dense layers for final output prediction.

##  Preprocessing

- Filled missing values via forward fill/interpolation.
- Scaled data using MinMaxScaler.
- Reshaped for supervised learning using sliding windows.
- Embedded categorical features for LSTM input.

##  Challenges & Solutions

| Challenge | Solution |
|----------|----------|
| Large dataset size | Focused on top-viewed articles |
| Missing data | Imputation using forward fill |
| Overfitting in LSTM | Dropout layers and reduced complexity |
| Computational load | Used efficient NumPy-based data pipelines |

## Web App

- Built using **Flask**.
- Input an article index and date to view predictions.
- Renders output on a separate HTML page with traffic metrics.

##  Future Scope

- Deploy live dashboard using Streamlit or Dash.
- Implement transformer-based models (like Temporal Fusion Transformers).
- Add external features (events, news) for better accuracy.
- Generalize model for other content platforms (blogs, news, etc.)

##  Directory Structure
├── app.py # Flask app for prediction interface ├── final_file.py # Model inference logic ├── templates/ │ ├── index.html │ └── new.html ├── models/ │ ├── arima_model.pkl │ └── lstm_model.json/h5 ├── data/ │ └── web_traffic.csv ├── README.md # Project documentation

##  Authors

- **Eesha Kamal** – Shiv Nadar University
- Special thanks to collaborators and Kaggle for the dataset.

##  Contact

For questions, feedback, or collaboration, feel free to reach out at [eeshakamal.vadigi02@gmail.com]

---

*Let’s forecast the future, one time series at a time!*




