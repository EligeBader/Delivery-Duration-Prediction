
# 🚀 Delivery Duration Prediction 📦

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Pandas-1.3.3%2B-green)](https://pandas.pydata.org/)
[![NumPy](https://img.shields.io/badge/NumPy-1.21.2%2B-orange)](https://numpy.org/)
[![Matplotlib](https://img.shields.io/badge/Matplotlib-3.4.3%2B-red)](https://matplotlib.org/)
[![Seaborn](https://img.shields.io/badge/Seaborn-0.11.2%2B-yellow)](https://seaborn.pydata.org/)
[![Scikit-learn](https://img.shields.io/badge/Scikit--learn-0.24.2%2B-lightgrey)](https://scikit-learn.org/)
[![Optuna](https://img.shields.io/badge/Optuna-2.10.0%2B-blue)](https://optuna.org/)
[![Scikit-optimize](https://img.shields.io/badge/Scikit--optimize-0.8.1%2B-purple)](https://scikit-optimize.github.io/)
[![Pickle](https://img.shields.io/badge/Pickle-Standard%20Library-brightgreen)](https://docs.python.org/3/library/pickle.html)

### Skills
- **Data Cleaning**: Handling missing values, converting data types.
- **Feature Engineering**: Creating new features, target encoding.
- **Exploratory Data Analysis (EDA)**: Summary statistics, visualizations, correlation analysis.
- **Regression Modeling**: Building and evaluating different regression models.
- **Hyperparameter Tuning**: GridSearchCV, RandomizedSearchCV, Optuna.
- **Model Evaluation**: RMSE, R² score.
- **Model Saving**: Using pickle for model serialization.

## 📚 Project Overview
When a consumer places an order on DoorDash, the expected delivery time is shown. Accurately predicting this time is crucial for consumer experience. In this project, I predict the estimated time taken for a delivery using historical data.

## 📄Business Problem

The goal of this project is to predict the delivery duration for DoorDash orders. Accurate delivery time predictions are crucial for enhancing customer satisfaction, optimizing delivery operations, and improving overall efficiency. By predicting delivery times more accurately, DoorDash can provide better estimates to customers, allocate resources more effectively, and reduce operational costs.

## 📊 Data Description
The dataset `historical_data.csv` contains deliveries from early 2015 in a subset of cities. Each row corresponds to a unique delivery with the following features:

- **market_id**: City/region ID.
- **created_at**: Timestamp of order submission.
- **actual_delivery_time**: Timestamp of order delivery.
- **store_id**: Restaurant ID.
- **store_primary_category**: Cuisine category of the restaurant.
- **order_protocol**: Mode of order reception.
- **total_items**: Total number of items in the order.
- **subtotal**: Total value of the order in cents.
- **num_distinct_items**: Number of distinct items in the order.
- **min_item_price**: Price of the cheapest item in cents.
- **max_item_price**: Price of the most expensive item in cents.
- **total_onshift_dashers**: Number of available dashers within 10 miles at order creation.
- **total_busy_dashers**: Subset of above who are currently working on an order.
- **total_outstanding_orders**: Number of orders within 10 miles being processed.
- **estimated_order_place_duration**: Estimated time for the restaurant to receive the order in seconds.
- **estimated_store_to_consumer_driving_duration**: Estimated travel time between store and consumer in seconds.

The target variable is the total delivery duration in seconds (difference between `created_at` and `actual_delivery_time`).

## 🛠️ Data Preparation
In the data preparation phase, several steps were taken to clean and preprocess the dataset:
- Converted timestamps to datetime objects.
- Created a target variable for total delivery duration in seconds.
- Filled missing values using appropriate methods (e.g., mode, KNN imputation).
- Encoded categorical variables using Target Encoding.
- Extracted additional date and time features.

## 🔍 Exploratory Data Analysis (EDA)
- **Summary Statistics**: Provided an overview of the dataset with summary statistics.
- **Visualizations**: Created several plots to understand the distribution of the data and relationships between features.
  - Histogram of total delivery duration
  - Count plot of store primary categories
  - Scatter plot of average item price vs. total delivery duration
  - Distribution plots for univariate analysis
  - Pair plot for multivariate analysis
  - Correlation matrix heatmap to check for multicollinearity

## 🤖 Modeling
### Models to Run
1. **Linear Regression**:
   - Used a pipeline with StandardScaler and LinearRegression.
   - Performed GridSearchCV to find the best parameters.
   - Evaluated performance on the test set.

2. **Polynomial Regression**:
   - Used a pipeline with PolynomialFeatures, StandardScaler, and Ridge Regression.
   - Performed GridSearchCV to find the best degree and regularization strength.
   - Evaluated performance on the test set.

3. **Random Forest Regressor**:
   - Performed RandomizedSearchCV to find the best hyperparameters.
   - Evaluated performance on the test set.

4. **Lasso Regression**:
   - Used a pipeline with StandardScaler and Lasso Regression.
   - Performed GridSearchCV to find the best regularization strength.
   - Evaluated performance on the test set.

5. **XGB Regressor**:
   - Used Optuna for hyperparameter tuning.
   - Evaluated performance on the test set.

## 📏 Metric Analysis
- **Root Mean Squared Error (RMSE)**: Evaluated the model's prediction error.
- **R² Score**: Evaluated the proportion of variance explained by the model.

## 🏆 Results Summary
- The best models were saved for future use.
- The performances of different models were compared based on RMSE and R² scores.

## 🔮 Future Directions
1. **Model Improvements**: What would you do if you had more time.
2. **Business Insights**: What else could DoorDash analyze to improve delivery predictions based on your experience with this data.

## 📝 Conclusion
- Final thoughts on the project.
- Potential impacts and benefits of the model.
