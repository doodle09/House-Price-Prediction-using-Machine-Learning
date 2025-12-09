House Price Prediction using Machine Learning (Regression + Feature Engineering)

This project builds a complete machine learning pipeline to predict house prices using the well-known Ames Housing dataset format. The workflow includes data cleaning, missing value imputation, feature engineering, one-hot encoding, model training, evaluation, and generating prediction files for submission.

The goal is to compare multiple regression algorithms—Random Forest, XGBoost, and Linear Regression—and determine which model produces the lowest RMSE score on a validation set.

Key Steps in the Project
1. Data Loading and Error Handling

The script loads train.csv and test.csv safely using exception handling to avoid crashes if files are missing or paths are incorrect.

2. Missing Value Analysis

The percentage of missing values is calculated for every column.
Columns with extremely high missing values (Alley, PoolQC, Fence, MiscFeature, Id) are dropped to simplify preprocessing.

3. Feature Engineering

Several new features are created to improve model performance:

TotalSF: Total square footage of the house

TotalBath: Combining full and half bathrooms

Age: Age of the property at the time of sale

These engineered features help capture structural and functional attributes of a home more effectively.

4. Encoding and Alignment

Categorical features are converted into dummy variables using one-hot encoding.
Because train and test sets may produce different dummy columns, both datasets are aligned to ensure identical feature sets.

5. Missing Value Imputation (KNNImputer)

A KNN Imputer fills remaining numerical missing values by estimating them based on similar samples, creating a cleaner and more complete dataset for modeling.

6. Model Training and Evaluation

Three regression models are trained and evaluated:

Random Forest Regressor

XGBoost Regressor

Linear Regression

The dataset is split into training and validation sets (80/20 split).
Each model's performance is measured using Root Mean Squared Error (RMSE).

7. Exporting Predictions

For each model, predictions on the test set are exported into separate CSV files:

submission_random_forest.csv

submission_xgboost.csv

submission_linear_regression.csv

This makes it easy to compare results or use them for competitions.

Final Output

The script prints RMSE scores for all three models and automatically identifies the best-performing model based on the lowest error.
