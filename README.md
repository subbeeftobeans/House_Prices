> **Questions:** (1) What drives home sale prices in Ames, Iowa? (2) How accurately can they be predicted from property features?
 
[One-sentence summary: what you built, which models, and your headline result. Example: "Predicted sale prices with [model] (RMSE of [X] on log price) and found that [top drivers] explain most of the variation."]
 
![Dashboard preview](images/dashboard.png)
 
---
 
## Table of Contents
- [Overview](#overview)
- [Dataset](#dataset)
- [Tools](#tools)
- [Process](#process)
- [Results](#results)
- [Key Findings](#key-findings)
- [Limitations & Next Steps](#limitations--next-steps)
- [Repository Structure](#repository-structure)
- [How to Run](#how-to-run)
---
 
## Overview
 
[2-3 sentences: the goal (explain and predict home prices), who would care (buyers, sellers, appraisers, lenders), and the Kaggle competition context.]
 
## Dataset
 
- **Source:** [Kaggle: House Prices - Advanced Regression Techniques](https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques)
- **Origin:** Real home sales from Ames, Iowa, compiled by Dean De Cock
- **Size:** [~1,460 training rows, 79 features]
- **Target:** `SalePrice` (modeled as `log(SalePrice)`)
## Tools
 
| Purpose | Tool |
|---|---|
| Database & querying | PostgreSQL, Postico |
| Cleaning, EDA & modeling | Python (Pandas, NumPy, Scikit-learn, [Matplotlib / Seaborn]) |
| Dashboard | Tableau |
| Version control | Git / GitHub |
 
## Process
 
1. **SQL exploration:** Loaded `train.csv` into PostgreSQL and profiled the data, including price by `Neighborhood`, `OverallQual`, and `YearBuilt`.
2. **Cleaning:** Treated "missing means none" columns (e.g., `PoolQC`, `Alley`) per the data description; handled true missing values (e.g., `LotFrontage`) using [method]; reviewed outliers such as [describe].
3. **EDA:** [Key plots: price distribution, price vs. `GrLivArea`, correlation heatmap.]
4. **Feature engineering:** [e.g., total square footage, house age, log-transforming skewed features.]
5. **Modeling:** Compared [Linear Regression, Ridge/LASSO, Random Forest, Gradient Boosting] using [k-fold cross-validation].
6. **Kaggle submission:** Submitted predictions for an official score.
7. **Dashboard:** Built a Tableau report showing [price by neighborhood, top price drivers].
## Results
 
| Model | CV RMSE (log price) | Notes |
|---|---|---|
| Linear Regression (baseline) | [X] | |
| LASSO | [X] | |
| [Best model] | [X] | |
 
- **Kaggle score:** [X] (leaderboard position: [top X%], if you want to include it)
## Key Findings
 
1. **[Finding 1]:** [e.g., Overall quality and living area were the strongest predictors of price.]
2. **[Finding 2]:** [e.g., Neighborhood effects: X commanded Y% higher prices after controlling for size.]
3. **[Finding 3]:** [...]
## Limitations & Next Steps
 
- [Single city and time period, so results may not generalize.]
- [Ideas: model stacking, more feature engineering, an interactive price-estimator tool.]
## Repository Structure
 
```
housing-price-analysis/
├── data/
├── sql/
│   ├── 01_create_schema.sql
│   └── 02_exploration_queries.sql
├── notebooks/
│   ├── 01_cleaning_eda.ipynb
│   └── 02_modeling.ipynb
├── dashboard/
│   └── housing_prices.pbix
├── images/
│   └── dashboard.png
└── README.md
```
 
## How to Run
 
1. Clone the repo:
```bash
   git clone https://github.com/[username]/[repo-name].git
```
2. Download `train.csv` and `test.csv` from the Kaggle competition into `data/`.
3. Create the database and table with `sql/01_create_schema.sql`, then import the CSV.
4. Run the queries in `sql/02_exploration_queries.sql`.
5. Run the notebooks in order.
6. Open `dashboard/housing_prices.pbix` in Power BI Desktop.
## Author
 
**Ryleigh Bergmann**
[LinkedIn](https://www.linkedin.com/in/ryleigh-bergmann)
