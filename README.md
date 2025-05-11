# Olympic Swimming Data Analysis and Prediction (1912-2020)

This project analyzes Olympic swimming results and predicts the gold medal time for the 100m freestyle event at the 2028 Olympics using machine learning.

## Project Structure
- `data/Olympic_Swimming.csv`: Main dataset (1912-2020)
- `Notebooks/eda_and_preprocessing.ipynb`: Exploratory Data Analysis (EDA) and data cleaning
- `Notebooks/prediction_100m_gold_2028.ipynb`: ML pipeline for predicting the 2028 100m freestyle gold medal time

## Analysis Highlights

### Evolution of 100m Gold-Medal Times
The analysis revealed significant improvements in swimming performance across all strokes over time:
- All four strokes (Freestyle, Backstroke, Breaststroke, Butterfly) show consistent improvement trends
- Freestyle remains the fastest stroke throughout Olympic history
- The rate of improvement has slowed in recent decades, suggesting approaching physical limits

### Gender Gap Analysis
A detailed examination of 100m event times by gender showed:
- Consistent performance differences across all strokes
- Similar improvement rates between men and women
- Smallest gender gap in breaststroke events
- Greatest gender gap in butterfly events

### Top Performing Nations
Analysis of gold medal distribution revealed:
- United States dominance in Olympic swimming
- Strong performances from Australia, East Germany, and other swimming powerhouses
- Recent emergence of new competitive nations

### Event Growth and Evolution
The total number of medals awarded per year shows:
- Steady increase in event count over time
- Major expansions in 1968 and 1996
- Equal representation of men's and women's events in modern Olympics

### Performance Improvement Trends
Statistical analysis of improvement rates showed:
- Average improvement of 0.2-0.3 seconds per Olympic cycle in 100m events
- Faster improvement rates in newer strokes (butterfly)
- Slowing improvement rates in established strokes (freestyle)

### Relay vs Individual Performance
Analysis of relay versus individual event speeds revealed:
- Significantly faster times in relay segments
- Effect consistent across both genders
- Approximately 2-3% improvement in relay legs versus individual races

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
- **Model MSE on 2020 test set:** 0.637
- **Predicted 100m freestyle gold medal time for 2028:** 48.06 seconds

## Conclusion
The model provides a data-driven estimate for the 2028 Olympic 100m freestyle gold medal time, based on historical trends and advanced ML techniques. Our analysis shows:
- A slowing rate of improvement in recent decades
- Strong predictive power with an MSE of 0.637
- Conservative estimates that account for the natural limits of human performance

Actual results may vary due to unforeseen factors such as technological advances, rule changes, or exceptional individual performances, but this serves as a strong statistical baseline for future performance expectations.
