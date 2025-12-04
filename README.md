# Activity-Index-GDP-nowcasting
This is the GitHub for my third year Introduction to Big data project which aims to answer the question: 
'Can google trends regarding hospitality help in nowcasting GDP?'

# **Structure**
- `1.datacleaning.py`sets up folders, saves `NAQ03.20251204T171251.csv` to `../data/raw`, collects data using pytrends API relating to hospitality searches, aggregated to quarterly and saves to `../data/processed`, merges the data sets, creates a hospitality index PCA
- `2.OLSRegression.py` , runs OLS regression of full data set, runs OLS regression using only the past five years of data, saves both regression results to `../results`
- `3.LASSORegression.py`, sets up a lagged GDP variable, runs LASSO regression of full data set, saves results to `../results` , runs LASSO regression of the data from the past five years and saves results to `../results`
- `4.RFNowcastingmodelandvalidation.py`, creates random forest regression using full data set, creates graph showing the difference between the predicted values and the actual GDP, creates random forest regression trained on the data from the past five years, creates graph showing the difference between the predicted values and the actual GDP, save results to `../results`, create graphs showing residuals of both models, save to `../results`, calculate MAE of both models

# **Prerequisites**
- Python
- Packages: ,`pytrends`, `pandas`, `scikit-learn` (imported as sklearn), `statsmodels`, `matplotlib`,`seaborn`, `numpy`
- Data file at `../file/NAQ03.20251204T171251.csv`

# Quick start 
- Ensure the directories exist
- Upload `NAQ03.20251204T171251.csv` to collab
- run the steps
  ```
  1_datacleaning.py
  2_OLSRegression.py
  3_LASSORegression.py
  4_RFNowcastingmodelandvalidation.py
  5_nowcastingmodel.py
  6_trainooutofsamplenowcast
  ```

  # Outputs
```
  - ols_summary_full_dataset
  - ols_summary_5_years_trained
  - lasso__coefficients_hospt_gdp_full_dataset
  - lasso__coefficients_hospt_gdp_5_years
  - nowcasting_results_full_dataset
  - nowcasting_results_5_years_trained`
```

# Notes and Tips
- `random_state=42` is used for the Time series split and the random forest
- `Pytrends API` occassionally shows `TooManyRequestsError`, this requires time in between requests from the same IP address
