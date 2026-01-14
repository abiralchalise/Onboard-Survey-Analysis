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
→ Interactive Notebook: [Interview.ipynb](Interview.ipynb)  
→ Static PDF: [Interview.pdf](Interview.pdf)

## Key Output: Regression Scatter Plot
![Regression Scatter](figures/regression_scatter.png)

## Notes
- Paths are local — adjust for your setup.
- Data not included (privacy) — request sample if needed.

Abiral  
Kathmandu, Nepal  
January 2026
