# StockFusion: Stock Market Closing Price Forecasting

**StockFusion** is a stock price prediction project that forecasts the next day's closing price using historical data. It combines models like LSTM, Linear Regression, SVR, and Random Forest, evaluated with multiple feature sets and metrics (MAE, RMSE, R²) to find the best approach.

---

## Models Implemented

### 1. Hybrid Model (HYBRID1)
- Combines **LSTM** and **Linear Regression**

### 2. Advanced Hybrid Model (HYBRID2)
- Integrates:
  - Linear Regression
  - LSTM
  - Support Vector Regressor (SVR)
  - Random Forest Regressor

### 3. Voting Regressor (VOT_REGRESSOR)
- Ensemble model combining predictions from the HYBRID2 components using a **Voting Regressor**

---

## Feature Engineering / Feature Selection

Each model is evaluated with three feature selection approaches:

### 🔹 Approach 1
- `Open`, `High`, `Low`, `Volume`, `Adjusted Close`

### 🔹 Approach 2
- `Open`, `High`, `Low`

### 🔹 Approach 3
- `Close` as both independent and dependent variable (using lag features)

---

## Evaluation Metrics

Performance is evaluated using:
- **MAE** – Mean Absolute Error
- **RMSE** – Root Mean Squared Error
- **R² Score** – Coefficient of Determination

---

## 📋 Results Summary

| Model          | Feature Approach | RMSE     | MAE      | R² Score  |
|----------------|------------------|----------|----------|-----------|
| HYBRID1        | Approach 1       | 0.224918 | 0.198645 | -9.795516 |
| HYBRID1        | Approach 2       | 0.220523 | 0.194120 | -9.377730 |
| HYBRID1        | Approach 3       | 0.064204 | 0.052957 |  0.120335 |
| HYBRID2        | Approach 1       | 0.131997 | 0.115328 |  0.754412 |
| HYBRID2        | Approach 2       | 0.131637 | 0.114410 |  0.755747 |
| HYBRID2        | Approach 3       | 0.045483 | 0.035602 |  0.558546 |
| VOT_REGRESSOR  | Approach 1       | 0.018960 | 0.016103 |  0.995401 |
| VOT_REGRESSOR  | Approach 2       | 0.022069 | 0.018663 |  0.993769 |
| VOT_REGRESSOR  | Approach 3       | 0.032301 | 0.027143 |  0.988428 |

---

## 🏁 Final Conclusion

- **Best Model:** **Voting Regressor**
- **Best Feature Strategy:** **Approach 1** (`Open`, `High`, `Low`, `Volume`, `Adjusted Close`)
- **Best Metrics:**
  - **RMSE:** 0.018960
  - **MAE:** 0.016103
  - **R² Score:** 0.995401

> The Voting Regressor using full features (Approach 1) produced the highest accuracy and lowest error, making it the most effective combination for next-day stock closing price prediction.



