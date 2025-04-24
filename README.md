# Olympic Swimming Data Analysis and Prediction (1912-2020)

This project analyzes Olympic swimming results and predicts the gold medal time for the 100m freestyle event at the 2028 Olympics using machine learning.

## Project Structure
- `data/Olympic_Swimming.csv`: Main dataset (1912-2020)
- `Notebooks/eda_and_preprocessing.ipynb`: Exploratory Data Analysis (EDA) and data cleaning
- `Notebooks/prediction_100m_gold_2028.ipynb`: ML pipeline for predicting the 2028 100m freestyle gold medal time

## Analysis Highlights
- Comprehensive EDA: trends, country performance, gender gap, and more
- Statistical questions: improvement rates, relay vs. individual, country progress
- Feature engineering: time conversion, categorical encoding

## Prediction Pipeline
- Train/test split (train: all years before 2020, test: 2020)
- Feature scaling (StandardScaler)
- LightGBM regression model
- Robust handling of categorical features
- Prediction for 2028 using the most common feature values

## Results (as of April 2025)
- **2020 actual gold medal times (100m freestyle):**
  - Men: 47.02 seconds
  - Women: 51.96 seconds
- **Model MSE on 2020 test set:** (see notebook for value)
- **Predicted 100m freestyle gold medal time for 2028:** (see notebook for value)

## Conclusion
The model provides a data-driven estimate for the 2028 Olympic 100m freestyle gold medal time, based on historical trends and advanced ML techniques. Actual results may vary due to unforeseen factors, but this serves as a strong statistical baseline for future performance expectations.
