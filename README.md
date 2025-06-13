## 🔄 Pipeline Overview

### 1. **Data Collection**
Data gathered from:
- [NYC DOT Traffic Speeds](https://data.cityofnewyork.us/Transportation/DOT-Traffic-Speeds-NBE/i4gi-tjb9)
- [NYC Collision Reports](https://data.cityofnewyork.us/Public-Safety/Motor-Vehicle-Collisions-Crashes/h9gi-nx95)
- [Visual Crossing Weather Data](https://www.visualcrossing.com/)

Weather data was downloaded monthly due to API limitations.

### 2. **Preprocessing**
- Aligned and merged time-based records
- Filled timestamp gaps, cleaned inconsistencies
- Selected a single road segment for cleaner and denser records

### 3. **Feature Engineering**
- Temporal encodings using sine and cosine transformations
- Holiday and non-business day tagging
- Weather metrics (wind, humidity, UV index, solar radiation, etc.)
- Crash statistics (injuries, fatalities, severity)
- Lag features (1h, 2h, 3h, 24h, 168h)
- Rolling statistics (mean and std for 3h, 6h, 12h)
- Change rates and percentage deltas

### 4. **Modeling**
Evaluated five models:
- **LightGBM**, **XGBoost**, **CatBoost**, **Random Forest**
- **Neural Network (MLPRegressor)**

Each model was trained with and without lag features to assess temporal dependency learning.

---

## ✅ Best Results Summary

### Results Summary

| Model         | Target       | Lag Features | RMSE     | MAE   | R²        | Response Time (s) |
| ------------- | ------------ | ------------ | -------- | ----- | --------- | ----------------- |
| **LightGBM**  | speed        |  Yes        | **1.09** | 0.71  | 0.988     | **0.36**          |
| **XGBoost**   | speed        |  Yes        | 1.10     | 0.72  | 0.988     | 1.56              |
| RandomForest  | speed        |  Yes        | 1.22     | 0.76  | 0.985     | 5.09              |
| CatBoost      | speed        |  Yes        | 1.29     | 0.89  | 0.984     | 1.40              |
| NeuralNetwork | speed        |  Yes        | 2.62     | 1.73  | 0.933     | 2.41              |
| **XGBoost**   | speed        |  No         | 5.63     | 4.21  | 0.689     | 0.45              |
| LightGBM      | speed        |  No         | 5.89     | 4.50  | 0.659     | **0.11**          |
| CatBoost      | speed        |  No         | 6.35     | 4.66  | 0.603     | 0.71              |
| RandomForest  | speed        |  No         | 6.50     | 4.90  | 0.585     | 0.27              |
| NeuralNetwork | speed        |  No         | 8.67     | 6.69  | 0.261     | 0.97              |
| **XGBoost**   | travel_time  |  Yes        | **4.42** | 2.10  | **0.982** | 1.60              |
| LightGBM      | travel_time  |  Yes        | 4.95     | 2.59  | 0.977     | **0.31**          |
| RandomForest  | travel_time  |  Yes        | 5.25     | 2.25  | 0.974     | 6.05              |
| CatBoost      | travel_time  |  Yes        | 5.32     | 2.81  | 0.974     | 1.42              |
| NeuralNetwork | travel_time  |  Yes        | 5.96     | 3.98  | 0.967     | 1.06              |
| **XGBoost**   | travel_time  |  No         | 21.41    | 13.59 | 0.573     | 0.48              |
| LightGBM      | travel_time  |  No         | 22.91    | 14.43 | 0.512     | **0.10**          |
| CatBoost      | travel_time  |  No         | 23.28    | 14.24 | 0.496     | 0.73              |
| RandomForest  | travel_time  |  No         | 24.36    | 15.50 | 0.448     | 0.28              |
| NeuralNetwork | travel_time  |  No         | 30.22    | 19.76 | 0.151     | 0.99              |

---

### Key Observations

* **Lag features** significantly improve performance for both targets.
* **LightGBM** and **XGBoost** consistently outperform other models.
* **Neural Networks** underperform, particularly without lag features.
* **LightGBM** offers the best **speed–accuracy tradeoff**.

---

## 📌 Limitations

- Weather data was generalized from a regional station, not per-street level.
- Data was focused only on **one road segment** for consistency.
- Manual weather downloads slowed automation.
- Limited compute power and training time restricted tuning deep learning models.

---
## 📈 Future Work

- Explore Deep Learning Architectures: Integrate LSTM, GRU, or Transformer-based models for better temporal sequence learning and prediction accuracy.
- Multivariate Time Series Forecasting: Model traffic speed and travel time jointly using multivariate forecasting techniques.
- Dynamic Route Prediction: Incorporate routing data using external APIs (e.g., Google Maps, OpenStreetMap) to model real-time congestion across paths rather than fixed segments.
- Anomaly Detection: Add unsupervised models to detect abnormal traffic conditions due to weather, construction, or special events.
- City-Wide Scalability: Extend predictions beyond a single road to multiple NYC zones or even entire cities with improved data handling pipelines.
- Classification Use Case: Frame traffic congestion as a classification task (e.g., heavy, medium, light) for better interpretability in deployment.
- Live Model Deployment: Deploy models with dashboards or alerts, enabling integration into smart city traffic systems.
- Weather Data Granularity: Incorporate more granular weather data (e.g., per-zone sensors or satellite feeds) for localized accuracy.
- Automated Feature Engineering: Use tools like Featuretools or AutoML pipelines to scale feature generation efficiently.


## 🙌 Acknowledgments

We would like to thank:
- **Prof. Sahar Selim** and **TA Amira Tarek** for their guidance in the Machine Learning course.
- Team Members: **Abdullah Yasser**, **Abdelrahman Alsamany**, and **Mona Gomaa**.

---

## 📦 Requirements

Install dependencies:
```bash
pip install -r requirements.txt
