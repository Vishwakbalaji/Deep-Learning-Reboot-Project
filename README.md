# 📊 7-Day Restaurant Sales Forecasting (Midday Shift)

This project is a reboot of my final semester deep learning capstone, focused on **forecasting restaurant sales for the midday shift** using a blend of **Machine Learning**, **Time Series**, and **Deep Learning** models. The motivation behind this was to help improve operational planning such as staff scheduling and inventory control.

---

## 📂 Dataset

- Dataset contains historical sales data from **multiple restaurants** across different shifts.
- This project zooms in on **one specific restaurant's midday shift**, which showed high variance influenced by holidays and weekday effects.
- **ADF test** (Augmented Dickey-Fuller) was used to test stationarity prior to time series modeling.

---

## 🛠️ Tools & Libraries

- Python (Pandas, NumPy, Matplotlib, Seaborn)
- Machine Learning: Scikit-learn (Linear Regression, Random Forest, SVR, KNN), XGBoost
- Time Series: ARIMA, SARIMAX, Prophet
- Deep Learning: TensorFlow, Keras (LSTM, CNN)

---

## 🔄 Workflow

### 1. Data Cleaning & Preprocessing
- Removed null values, converted dates, and filtered records
- Verified stationarity using ADF Test
- Feature engineering:
  - Lag features (1, 7 days)
  - Rolling mean, rolling std
  - One-hot encoded events (Carnival, Lent, Ramadan)
  - Shift encoding: focused on **midday** only

### 2. Dimensionality Reduction
- Removed low-variance and high-correlation features

### 3. Modeling
- Trained and evaluated **10 models**:
  - ✅ **ML**: Linear Regression, Random Forest, SVR, XGBoost, KNN
  - ✅ **Time Series**: ARIMA, SARIMAX, Prophet
  - ✅ **Deep Learning**: LSTM, CNN

### 4. Evaluation Metrics
- Mean Absolute Percentage Error (**MAPE**)
- Root Mean Square Error (**RMSE**)
- Learning curves, residual histograms, and forecast vs actual plots

---

## 📈 Updated Results Summary

| Model                  | RMSE     | MAPE      |
|------------------------|----------|-----------|
| **CNN-LSTM**           | **0.070863** | 16.06%    |
| **LSTM**               | 0.082207 | 19.71%    |
| **Linear Regression**  | 0.880661 | **0.30%** |
| **Prophet with Regressors** | 1.001558 | 0.38%     |
| SARIMAX with Regressors | 1.040867 | 0.52%     |
| Gradient Boosting      | 3.133384 | 1.08%     |
| XGBoost                | 5.113366 | 1.09%     |
| Random Forest          | 7.219758 | 1.63%     |
| KNN Regressor          | 48.828359| 12.36%    |
| Exponential Smoothing  | 31.652912| 16.07%    |

### 🏆 Best Performing Models:
- **Lowest RMSE:** CNN-LSTM  
- **Lowest MAPE:** Linear Regression  

👉 This shows a key insight: **deep learning models like CNN-LSTM** had exceptional RMSE accuracy, but **Linear Regression** had much lower percentage error (MAPE) — likely due to its stability on smaller fluctuations.

---

## 📌 Key Takeaways

- Midday sales had a 50/50 chance of being high or low, heavily influenced by holidays and weekday behavior — making it a crucial forecasting target.
- ADF testing helped validate the appropriateness of time series models.
- Feature engineering and data cleaning had more impact on accuracy than model complexity alone.
- Model comparison across ML, TS, and DL gave full visibility into performance.
- Residual analysis and error visualization helped pinpoint improvement areas beyond just metrics.

---

## 📆 Project Folder Structure

```
project/
├── data/
│   ├── raw_sales.xlsx
│   └── cleaned_sales.xlsx
├── notebooks/
│   ├── DL_Reboot_Cleaning_and_Feature_Selection_on_7_days_forecasting.ipynb
│   └── DL_Reboot_7_day_Forecast_Base_and_Enhancement_model.ipynb
├── outputs/
│   ├── plots/
│   └── final_forecast_comparison.csv
└── README.md
```

---

## 📢 Contact

If you're looking for a data scientist with hands-on experience in time series forecasting and hybrid modeling, feel free to reach out or connect with me on [LinkedIn]([https://www.linkedin.com/in/your-profile](https://www.linkedin.com/in/vishwak-balaji-jayasankar-8a384018a/)).

---

> "This project helped me bridge academic theory with real-world application — from ADF tests to CNNs, all tied to solving a practical business forecasting challenge."
