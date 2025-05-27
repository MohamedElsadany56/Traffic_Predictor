# Traffic Prediction Model Results

## 1. Neural Network Performance

### Without Lag Features
- **MAE**: 16.7564  
- **R² Score**: 0.2646  

### With Lag Features
- **MAE**: 5.3303  
- **R² Score**: 0.9050  

---

## 2. Speed Prediction (With Lag Features)

### **CatBoost**
- **RMSE**: 0.0109  
- **MSE**: 0.0001  
- **MAE**: 0.0070  
- **Median Absolute Error**: 0.0047  
- **R² Score**: 0.9967  
- **Response Time**: 0.0301 sec  

### **LightGBM**
- **RMSE**: 0.0100  
- **MAE**: 0.0070  
- **R² Score**: 0.9972  
- **Response Time**: 0.1787 sec  

### **Random Forest**
- **RMSE**: 0.0103  
- **MAE**: 0.0046  
- **R² Score**: 0.9971  
- **Response Time**: 0.9014 sec  

### **XGBoost**
- **RMSE**: 0.0113  
- **MAE**: 0.0078  
- **R² Score**: 0.9965  
- **Response Time**: 0.0787 sec  

---

## 3. Travel Time Prediction (With Lag Features)

### **CatBoost**
- **RMSE**: 0.0156  
- **MSE**: 0.0002  
- **MAE**: 0.0082  
- **Median Absolute Error**: 0.0039  
- **R² Score**: 0.9919  
- **Response Time**: 0.0299 sec  

---

## 4. Speed Prediction (Without Lag Features)

- **RMSE**: 0.1261  
- **MSE**: 0.0159  
- **MAE**: 0.0950  
- **Median Absolute Error**: 0.0744  
- **R² Score**: 0.5593  
- **Response Time**: 0.0210 sec  

---

## 5. Travel Time Prediction (Without Lag Features)

- **RMSE**: 0.1333  
- **MSE**: 0.0178  
- **MAE**: 0.0908  
- **Median Absolute Error**: 0.0582  
- **R² Score**: 0.4063  
- **Response Time**: 0.0410 sec  

### Other Models:
| Model         | RMSE   | MSE    | MAE    | MedianAE | R²    | Response Time |
|---------------|--------|--------|--------|----------|--------|----------------|
| LightGBM      | 0.1402 | 0.0196 | 0.1067 | 0.0833   | 0.4558 | 0.0908 sec     |
| RandomForest  | 0.1380 | 0.0190 | 0.1036 | 0.0796   | 0.4723 | 0.4704 sec     |
| XGBoost       | 0.1366 | 0.0187 | 0.1031 | 0.0801   | 0.4831 | 0.0463 sec     |

