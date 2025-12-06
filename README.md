# Boston Airbnb Price Prediction

This project uses supervised machine learning to predict log-transformed nightly
Airbnb prices in Boston. The workflow includes data cleaning, exploratory data
analysis (EDA), feature engineering, and model evaluation using Linear Regression
and Random Forest.

---

## Dataset

Source: Boston Airbnb Open Data (Kaggle)
Target variable: log_price (log-transformed nightly price)

---

## Methods

### 1. Data Cleaning
- Removed irrelevant columns (IDs, URLs, descriptions)
- Dropped columns with excessive missing values
- Cleaned the price column
- Created a log-transformed target: log_price = log(price + 1)
- Selected 12 meaningful features for modeling

### 2. Exploratory Data Analysis (EDA)
- Distribution plots of price and log_price
- Room type vs log_price
- Neighbourhood vs log_price
- Relationships between numeric features and log_price
- Correlation heatmap

### 3. Modeling

Models trained on an 80/20 train/test split:
- Baseline model (predicts mean log_price)
- Linear Regression
- Random Forest Regressor

Metrics used:
- MAE (Mean Absolute Error)
- RMSE (Root Mean Squared Error)
- R² (Coefficient of determination)

Model Comparison Table:
Model | MAE | RMSE | R²
------|-----|------|---
Baseline | 0.518 | 0.636 | 0.000
Linear Regression | 0.270 | 0.378 | 0.648
Random Forest | 0.237 | 0.342 | 0.712

---

## Feature Importance

Random Forest feature importances indicate that the strongest predictors of price are:
- Room type
- Property size (accommodates, bedrooms, bathrooms)
- Latitude and longitude

---

## How to Run the Project

1. Clone this repository:
   git clone <repo-url>
   cd boston-airbnb-price-prediction

2. (Optional) Create a virtual environment:
   python -m venv venv
   venv\Scripts\activate     # Windows

3. Install dependencies:
   pip install -r requirements.txt

4. Make sure your dataset exists at:
   data/listings.csv

5. Launch Jupyter Notebook:
   jupyter notebook

6. Open and run:
   notebooks/airbnb_price_boston.ipynb

---

## Conclusion

Random Forest performed best, capturing nonlinear relationships and producing the
lowest errors. Location, room type, and property characteristics were the strongest
predictors of Airbnb prices.

---

## License

This project is for educational use.
