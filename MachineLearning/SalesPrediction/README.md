Olist Daily Sales Forecasting
Machine Learning project for daily sales forecasting using historical e-commerce transaction data from the Olist dataset.

The project focuses on transforming historical sales into a time-series regression problem, engineering predictive temporal features, benchmarking multiple regression models, and selecting the best-performing approach based on out-of-sample performance.

1. Project Objective
The objective is to develop a predictive model capable of estimating daily sales revenue from historical sales behavior and temporal patterns.

This project addresses the following question:

Can historical sales patterns and temporal information be used to accurately predict future daily sales?

The problem is formulated as a supervised time-series regression task.

2. Methodology
The Machine Learning workflow follows these main stages:

Historical Sales │ ▼ Data Preparation │ ▼ Exploratory Data Analysis │ ▼ Time-Series Feature Engineering │ ▼ Chronological Train/Test Split │ ▼ Model Benchmarking │ ├── Baseline ├── Linear Regression ├── Random Forest └── Gradient Boosting │ ▼ Performance Evaluation │ ▼ Model Selection


---

## 3. Dataset Preparation

The transactional data was aggregated at the **daily level** to create the modeling dataset.

The target variable is:

```text
daily_sales
Data preparation included:

Data type validation
Missing-value analysis
Data consistency checks
Chronological sorting
Removal of invalid observations
Removal of NaN values generated during lag and rolling feature creation
4. Exploratory Data Analysis
Exploratory analysis was conducted to identify relevant patterns and relationships in historical sales.

The analysis included:

Sales distribution
Sales evolution over time
Temporal patterns
Weekly seasonality
Correlation analysis
Feature importance analysis
The analysis indicated that recent historical sales contain significant predictive information about future sales.

5. Feature Engineering
Since the problem is based on temporal data, features were engineered to represent historical sales behavior and calendar effects.

Historical Features
Lag variables:

sales_lag_1 sales_lag_7 sales_lag_14 sales_lag_30


These variables represent sales observed at previous time points.

### Rolling Statistics

Historical moving averages:

sales_rolling_7
sales_rolling_14
sales_rolling_30
These features capture short-, medium-, and long-term sales trends.

Rolling features were constructed using historical observations only in order to avoid data leakage.

Calendar Features
year month quarter week_of_year day_of_week day_of_month


These variables allow the models to capture temporal and seasonal effects.

---

## 6. Target and Predictors

### Target


y = daily_sales
Predictors
X = year month quarter week_of_year day_of_week day_of_month sales_lag_1 sales_lag_7 sales_lag_14 sales_lag_30 sales_rolling_7 sales_rolling_14 sales_rolling_30


---

## 7. Train/Test Strategy

Because this is a **time-series forecasting problem**, a random train/test split was avoided.

The observations were split chronologically:

```text
Past                                              Future
│----------------------------------------------------│
│                  Training                         │
│                                                    │
│                                      Test          │
│                                      │             │
└──────────────────────────────────────┴─────────────┘
The training set contains earlier observations, while the test set represents a later period.

This approach provides a more realistic evaluation of future forecasting performance and reduces the risk of temporal data leakage.

8. Models
Four approaches were benchmarked.

Baseline
A naive forecasting approach using the previous day's sales as the prediction.

Linear Regression
A linear regression model used as a simple Machine Learning benchmark.

Random Forest Regressor
An ensemble of decision trees designed to capture non-linear relationships and interactions between predictors.

Gradient Boosting Regressor
A sequential ensemble method that builds decision trees iteratively to reduce prediction errors.

9. Evaluation Metrics
Model performance was evaluated using three regression metrics.

MAE — Mean Absolute Error
Measures the average absolute difference between actual and predicted sales.

Lower values indicate better performance.

RMSE — Root Mean Squared Error
Measures prediction error while assigning greater importance to large errors.

Lower values indicate better performance.

MAPE — Mean Absolute Percentage Error
Measures prediction error relative to the actual value.

Lower values indicate better performance.

MAPE was interpreted cautiously because percentage-based errors can become unstable when actual sales values are close to zero.

10. Model Performance
Model	MAE ↓	RMSE ↓	MAPE ↓
Baseline	6,336.76	8,170.41	32.14%
Linear Regression	8,233.85	9,912.99	197.33%
Random Forest	5,911.33	7,987.67	130.08%
Gradient Boosting	6,384.30	8,560.27	147.09%
11. Model Selection
Based on the current test-set results, Random Forest Regressor achieved the strongest overall performance.

Best results
MAE = 5,911.33 RMSE = 7,987.67


Random Forest achieved the lowest MAE and RMSE among the evaluated approaches.

Compared with the baseline:


MAE improvement
6,336.76 → 5,911.33

RMSE improvement
8,170.41 → 7,987.67
This indicates that the Random Forest model extracted additional predictive information from the engineered historical and temporal features beyond the previous-day sales baseline.

12. Feature Importance
Feature importance analysis from the Random Forest model revealed the following ranking:

Rank	Feature	Importance
1	sales_rolling_7	53.82%
2	sales_lag_1	18.27%
3	day_of_week	6.20%
4	sales_rolling_14	4.89%
5	sales_lag_14	4.80%
6	sales_rolling_30	4.37%
7	sales_lag_7	2.58%
8	sales_lag_30	1.46%
The dominance of sales_rolling_7 and sales_lag_1 indicates that recent sales behavior is the primary source of predictive information in the current feature set.

The importance of day_of_week also suggests the presence of a weekly sales pattern.

Feature importance represents the relative contribution of variables within the Random Forest model; it should not be interpreted as causal influence.

13. Key Findings
The current experiments lead to several conclusions:

Historical sales are strong predictors of future sales.
Short-term historical features outperform most calendar variables.
Random Forest outperformed both linear and boosting approaches tested in the current experiment.
The previous-day baseline remains competitive, highlighting the strong temporal persistence of daily sales.
MAPE should not be used as the sole selection criterion because low actual sales values can produce disproportionately large percentage errors.
14. Limitations
The current model represents an initial forecasting benchmark.

Potential limitations include:

Limited feature set
No external business variables
No hyperparameter optimization yet
No advanced time-series models
Sensitivity of MAPE to low sales values
Current feature importance is model-specific
Therefore, the Random Forest model should be considered the best current candidate, rather than the final optimized forecasting solution.

15. Next Steps
The next phase of the project will focus on improving the selected model through:

Random Forest hyperparameter tuning
Time-series cross-validation
XGBoost benchmarking
Additional temporal features
Alternative error metrics
Multi-step forecasting
Future sales prediction
Model persistence and deployment
16. Technologies
Programming

Python
Data Processing

Pandas
NumPy
Visualization

Matplotlib
Machine Learning

Scikit-learn
Development Environment

Jupyter Notebook
17. Repository Structure
machine-learning/ │ ├── notebooks/ │ └── sales_prediction.ipynb │ ├── images/ │ └── model_results/ │ ├── README.md │ └── .gitignore


---

## 18. Project Status

| Phase                     | Status      |
| ------------------------- | ----------- |
| Data Preparation          | ✅ Completed |
| Exploratory Data Analysis | ✅ Completed |
| Correlation Analysis      | ✅ Completed |
| Feature Engineering       | ✅ Completed |
| Train/Test Split          | ✅ Completed |
| Baseline                  | ✅ Completed |
| Linear Regression         | ✅ Completed |
| Random Forest             | ✅ Completed |
| Gradient Boosting         | ✅ Completed |
| Model Evaluation          | ✅ Completed |
| Model Selection           | ✅ Completed |
| Hyperparameter Tuning     | 🔄 Planned  |
| Advanced Models           | 🔄 Planned  |
| Future Forecasting        | 🔄 Planned  |
| Deployment                | 🔄 Planned  |

---

## 19. Conclusion

This project demonstrates an end-to-end Machine Learning workflow for **daily sales forecasting**.

Several regression approaches were benchmarked using a chronological evaluation strategy. Among the tested models, **Random Forest Regressor achieved the best performance based on MAE and RMSE**, outperforming both the naive baseline and the other Machine Learning models.

The feature importance analysis further demonstrates that **recent sales history is the most informative component for predicting future sales**.

The next objective is to optimize the selected model and evaluate more advanced forecasting approaches before generating future sales predictions.
