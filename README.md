# Ad-Ease-Business-Case

A time-series forecasting case study for AdEase, an advertising infrastructure company. The analysis forecasts daily Wikipedia page views by language to support ad inventory planning and campaign timing.

## Project files

- `AdEase_Time_Series_Business_Case.ipynb`: Exploratory analysis, language-level aggregation, stationarity checks, ARIMA/SARIMA/SARIMAX/Prophet comparisons, and 30-day forecasts. Notebook outputs can be cleared to keep the repository lightweight while retaining the code and written analysis.
- `Exog_Campaign_eng`: Daily campaign and event indicator used as an external regressor for English forecasts.
- `train_1.csv`: Required Wikipedia page-view dataset. The local copy is about 265 MB, above GitHub’s 100 MB per-file limit, so it must be stored elsewhere or added using Git LFS. Place it beside the notebook before running the analysis.

## Run the analysis

Install Jupyter and the notebook dependencies: NumPy, pandas, Matplotlib, Seaborn, statsmodels, scikit-learn, and Prophet. Launch Jupyter from this directory and run the notebook from top to bottom.

The notebook reads `train_1.csv` and `Exog_Campaign_eng` using paths relative to the project directory. The source data spans 550 daily observations; the final 60 days are held out for model evaluation.

## Main findings

- English accounts for about 55.6% of total views and is the primary inventory opportunity.
- A weekly pattern appears across languages.
- For English, adding the campaign indicator to SARIMAX reduced the reported MAPE from about 8.15% to 6.10%.
- Forecast accuracy varies by language. The notebook compares fitted models with a seasonal-naive baseline and includes 30-day forecasts with intervals.

These forecasts are planning estimates based on historical traffic and should be refreshed as new data and campaign schedules become available.
