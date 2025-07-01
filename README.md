# House-Price-Prediction
Project Overview
This project focuses on predicting house prices using machine learning regression techniques. A Decision Tree Regressor is trained on a real estate dataset, and its performance is optimized using GridSearchCV for hyperparameter tuning.

Dataset
Name: HousePricePrediction-data.csv

Size: 4600 rows × 18 columns

Source: Uploaded to Google Drive and accessed via Google Colab.

Features Used for Modeling
The following columns were selected for model training:
bedrooms
bathrooms
sqft_living
sqft_lot
floors
condition
sqft_above
sqft_basement
yr_built
city

Preprocessing Steps
Checked for null values (none found)
Removed duplicate rows
Encoded categorical features: city, statezip using OrdinalEncoder
Split the dataset: 75% train / 25% test

Model Used
Algorithm: DecisionTreeRegressor

Initial Parameters:
DecisionTreeRegressor(
    criterion='squared_error',
    max_depth=4,
    min_samples_split=5,
    min_samples_leaf=1,
    random_state=23
)
Initial R² Score: 0.3657
Mean Squared Error: 71452269320.02

Hyperparameter Tuning with GridSearchCV
Used GridSearchCV with 5-fold CV and the following parameter grid:

param_grid = {
    "max_depth": [2, 4, 6, 8, 10],
    "criterion": ["squared_error", "absolute_error"],
    "min_samples_leaf": [1, 2, 3, 4, 5],
    "min_samples_split": [2, 5, 10, 15, 100],
    "random_state": [23, 42]
}
Best Parameters Found:
{
    'criterion': 'absolute_error',
    'max_depth': 6,
    'min_samples_leaf': 5,
    'min_samples_split': 2,
    'random_state': 42
}
Feature Importance (Top Contributors)
1. sqft_living     → 78.9%
2. yr_built        → 14.4%
3. city            → 5.0%
4. bathrooms       → 1.5%


Tools & Libraries Used
Google Colab
Python (Pandas, NumPy, Seaborn, Matplotlib)
Scikit-learn
Graphviz (for tree visualization)

How to Run
Upload the dataset to your Google Drive
Mount the drive in Colab using:
from google.colab import drive
drive.mount('/content/drive')
Load dataset and run cells sequentially.

Future Improvements
Try Random Forest Regressor or XGBoost
Perform feature engineering on date, street, or yr_renovated
Add scaling or normalization
Deploy using Streamlit or Flask

Author
Anushree
GitHub: @Anushree1403

