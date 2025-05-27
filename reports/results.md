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
- **RMSE**: 0.0122  
- **MSE**: 0.0002  
- **MAE**: 0.0076  
- **Median Absolute Error**: 0.0049  
- **R² Score**: 0.9938  
- **Response Time**: 0.0227 sec  

### **LightGBM**
- **RMSE**: 0.0097  
- **MAE**: 0.0001  
- **R² Score**: 0.9961  
- **Response Time**: 0.0509 sec  

### **Random Forest**
- **RMSE**: 0.0086  
- **MAE**: 0.0046  
- **R² Score**: 0.9970  
- **Response Time**: 0.7228 sec  

### **XGBoost**
- **RMSE**: 0.0116  
- **MAE**: 0.0082  
- **R² Score**: 0.9945  
- **Response Time**: 0.0365 sec  

---

## 3. Travel Time Prediction (With Lag Features)

### **CatBoost**
- **RMSE**: 0.0122  
- **MSE**: 0.0002  
- **MAE**: 0.0076  
- **Median Absolute Error**: 0.0049  
- **R² Score**: 0.9938  
- **Response Time**: 0.0227 sec  

---

## 4. Speed Prediction (Without Lag Features)

- **RMSE**: 0.1412  
- **MSE**: 0.0199  
- **MAE**: 0.0989  
- **Median Absolute Error**: 0.0682  
- **R² Score**: 0.1815  
- **Response Time**: 0.0037 sec  

---

## 5. Travel Time Prediction (Without Lag Features)

- **RMSE**: 0.1518  
- **MSE**: 0.0230  
- **MAE**: 0.1047  
- **Median Absolute Error**: 0.0711  
- **R² Score**: 0.1388  
- **Response Time**: 0.0041 sec 

### Other Models:
| Model         | RMSE   | MSE    | MAE    | MedianAE | R²    | Response Time |
|---------------|--------|--------|--------|----------|--------|----------------|
| LightGBM      | 0.1459 | 0.0213 | 0.1045 | 0.0745   | 0.1263 | 0.0402 sec     |
| RandomForest  | 0.1524 | 0.0190 | 0.1036 | 0.0796   | 0.4723 | 0.4704 sec     |
| XGBoost       | 0.1556 | 0.0242 | 0.1148 | 0.0863   | 0.0058 | 0.0183 sec     |

