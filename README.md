# Onboard Bus Survey Analysis & Linear Regression

Analysis of onboard survey data from public buses on the Lagankhel ↔ Budhanilkantha route. Merges Excel surveys, wrangles data, aggregates into time bins, and builds a linear regression model to predict Planning Time (95th percentile travel time) from dwell delays.

## Project Pipeline
1. Merge multiple Excel files (Route1/Route2).
2. Wrangle: Calculate travel times, subtract delays for mean time.
3. Aggregate: 30-min bins with means/95th percentiles.
4. Model: Initial full OLS → refined based on p-values.
5. Evaluate: MAPE (4.41%), predictions table, scatter plot.

Key Technologies: Python (pandas, statsmodels, sklearn, seaborn/matplotlib).

## How to View
→ Interactive Notebook: [Onboard_survey_analysis.ipynb](Onboard_survey_analysis.ipynb)  
→ Static PDF: [Onboard_survey_analysis.pdf](Onboard_survey_analysis.pdf)

## Model Validation Results (Test Set)

The table below shows the actual vs predicted Planning Time (in seconds) for the 7 test samples, along with the percentage change.

| Field Planning Time (s) | Predicted Planning Time (s) | % Change   |
|--------------------------|------------------------------|------------|
| 6391.10                  | 6287.37                      | -1.62%     |
| 5422.05                  | 5405.84                      | -0.30%     |
| 5542.05                  | 5857.01                      | +5.68%     |
| 4898.45                  | 5406.21                      | +10.37%    |
| 5126.80                  | 4915.89                      | -4.11%     |
| 4938.35                  | 5089.19                      | +3.05%     |
| 6074.30                  | 5725.70                      | -5.74%     |

**Mean Absolute Percentage Error (MAPE):** 4.41%

**Key Observations:**
- Most predictions fall within ±6% of actual values — strong performance for a simple linear model on real bus data.
- The largest deviation (+10.37%) may indicate an outlier case (e.g., unusual dwell times or traffic conditions).
- Overall, the refined model provides reliable estimates for planning time.

**Limitations:**
- The dataset is small (only 32 aggregated rows total, 7 in test set). This is because Planning Time is calculated as the 95th percentile per 30-minute time bin — a standard approach for reliability analysis, but it significantly reduces the number of data points available for modeling.
- With limited data, the model may not capture all variability and could perform differently on a larger dataset.
- Future improvements: Collect more survey days or use individual trip data (instead of aggregated) to increase sample size.

## Notes
- Paths are local — adjust for your setup.
- Data not included (privacy) — request sample if needed.

## Contact

Questions or suggestions? Open an issue or reach out!

[Abiral Chalise](https://www.linkedin.com/in/abiral-chalise-123704330/)
