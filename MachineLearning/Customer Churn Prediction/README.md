# Customer Churn Prediction

## Objective

The objective of this project is to build a Machine Learning classification model capable of predicting customer churn based on historical customer behavior from the Olist dataset.

The project focuses on identifying customers who are likely to stop purchasing in the future by using behavioral features such as recency, frequency, monetary value, and purchasing activity.

The main goal is to provide a reliable Machine Learning approach for customer retention analysis.

---

## Business Problem

Customer churn can negatively impact business revenue and long-term customer relationships.

The objective is therefore to:

* Identify customers at risk of churn.
* Analyze historical customer purchasing behavior.
* Build classification models to predict future churn.
* Compare different Machine Learning algorithms.
* Select the most appropriate model based on evaluation metrics.

---

## Dataset

The project uses the **Olist Brazilian E-Commerce Dataset** stored in a PostgreSQL Data Warehouse.

The Machine Learning process uses customer transaction and date information extracted from the Data Warehouse.

Main information used:

* Customer ID
* Purchase date
* Order information
* Purchase value
* Number of items
* Customer purchasing history

---

## Methodology

The project follows a structured Machine Learning workflow:

```text
PostgreSQL Data Warehouse
        ↓
Data Extraction
        ↓
Data Preparation
        ↓
Feature Engineering
        ↓
Churn Target Definition
        ↓
Data Leakage Prevention
        ↓
Train / Test Split
        ↓
Baseline Model
        ↓
Logistic Regression
        ↓
Random Forest
        ↓
Gradient Boosting
        ↓
Model Evaluation
        ↓
Model Comparison
        ↓
Feature Importance
        ↓
Final Model Selection
```

---

## Data Preparation

The extracted customer data was cleaned and prepared before Machine Learning.

The preparation process included:

* Checking the dataset structure.
* Removing missing values.
* Checking data types.
* Verifying customer records.
* Preparing customer-level features.

---

## Customer Feature Engineering

Customer behavioral features were created from historical transactions.

### Recency

Recency represents the number of days since the customer's last purchase during the observation period.

```text
Recency = Reference Date - Last Purchase Date
```

A higher recency indicates that the customer has been inactive for a longer period.

### Frequency

Frequency represents the number of purchases/orders made by the customer during the observation period.

### Monetary

Monetary represents the total amount spent by the customer during the observation period.

### Total Items

Represents the total number of items purchased by the customer.

### Average Order Value

Represents the average value of the customer's orders.

---

## Churn Target Definition

A major improvement was made to avoid **target leakage**.

Instead of defining churn directly from the same historical features used by the model, the dataset was divided into:

```text
Historical Period
        ↓
Customer Features
        ↓
Future Period
        ↓
Customer Future Behavior
        ↓
Churn Target
```

A customer is classified as:

```text
Churn = 1 → No purchase during the future period
Churn = 0 → At least one purchase during the future period
```

This approach ensures that the target represents **future customer behavior** rather than information already contained in the input features.

---

## Machine Learning Models

Three classification models were evaluated in addition to a baseline model.

### 1. Baseline

A `DummyClassifier` was used as a reference model.

The baseline predicts the majority class and provides a minimum performance reference for the Machine Learning models.

### 2. Logistic Regression

Logistic Regression was used as a simple and interpretable classification model.

It provides a useful benchmark for comparing more complex algorithms.

### 3. Random Forest

Random Forest was used to capture non-linear relationships between customer behavioral features and churn.

The model combines multiple decision trees to improve classification performance.

### 4. Gradient Boosting

Gradient Boosting was also evaluated because of its ability to model complex relationships by sequentially improving the predictions of previous trees.

---

## Model Evaluation

The models were evaluated using:

* Accuracy
* Precision
* Recall
* F1-Score
* ROC-AUC

### Evaluation Results

| Model               | Accuracy | Precision |  Recall | F1-Score | ROC-AUC |
| ------------------- | -------: | --------: | ------: | -------: | ------: |
| Baseline            |   69.16% |    69.16% | 100.00% |   81.77% |       — |
| Logistic Regression |   62.09% |    69.21% |  81.41% |   74.81% |       — |
| Random Forest       |  100.00% |   100.00% | 100.00% |  100.00% |  1.0000 |
| Gradient Boosting   |  100.00% |   100.00% | 100.00% |  100.00% |  1.0000 |

---

## Results

Random Forest and Gradient Boosting achieved the highest performance on the test dataset.

Both models obtained:

```text
Accuracy  : 100%
Precision : 100%
Recall    : 100%
F1-Score  : 100%
ROC-AUC   : 1.0000
```

These results indicate that both tree-based models were able to perfectly separate the two churn classes on the current test set.

However, such perfect performance should be interpreted carefully. Even after correcting the original target leakage, the churn definition is strongly related to customer recency and purchasing behavior. Therefore, additional validation on a separate temporal period would be recommended before considering the model production-ready.

---

## Feature Importance

Feature importance was analyzed for the tree-based models to understand which customer behavioral variables contributed most to churn prediction.

The main features analyzed were:

* Recency
* Frequency
* Monetary
* Total Items
* Average Order Value

This analysis provides additional interpretability and helps understand the behavioral factors associated with customer churn.

---

## Conclusion

This project demonstrates a complete Machine Learning workflow for **Customer Churn Prediction** using Olist e-commerce data.

The project progressed from data extraction and preparation to customer feature engineering, future-based churn definition, model training, and evaluation.

The comparison showed that **Random Forest and Gradient Boosting** achieved the strongest performance on the current test dataset.

The most important methodological improvement was the correction of **target leakage** by defining churn from customer behavior during a future period rather than directly from the historical features used for training.

The project provides a solid foundation for customer retention analysis and can be extended with:

* Temporal validation
* Hyperparameter tuning
* Cross-validation
* Feature selection
* SHAP-based model explainability
* Customer churn probability scoring
* Early-warning customer risk analysis

---

## Technologies

* Python
* Pandas
* NumPy
* Scikit-learn
* SQLAlchemy
* PostgreSQL
* Jupyter Notebook

---

## Project Structure

```text
Customer-Churn-Prediction/
│
├── Customer_Churn_Prediction.ipynb
│
├── README.md
│
└── results/
    └── model_evaluation.csv
```

---

## Author

**BI / Data Analytics Engineering Student**

This project is part of a broader Business Intelligence and Data Analytics project based on the Olist e-commerce dataset.
