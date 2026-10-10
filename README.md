# 📉 Customer Churn Analysis & Customer Intelligence

## Project Overview

This project analyzes customer, subscription, and customer-support data to explore customer churn, retention, subscription plans, revenue at risk, and support-related indicators.

The analysis is performed in a Jupyter Notebook using **Python, Pandas, NumPy, Matplotlib, Seaborn, and SQLite**. The workflow includes loading data from Excel into SQLite, cleaning and preparing the tables, joining data, creating churn-related features, calculating KPIs, and visualizing patterns.

> **Dataset note:** The supplied workbook is a small sample (21 customer records, 21 subscription records, and 9 support records). Treat the metrics in this project as an example analysis, not as statistically representative business-wide findings.

## Objectives

- Calculate churn and retention rates.
- Compare churn rates across subscription plan types.
- Calculate average revenue per user (ARPU).
- Estimate average customer tenure.
- Calculate monthly charges associated with churned customers as revenue at risk.
- Examine support escalations and complaint counts.
- Explore the relationship between support escalations and churn.
- Create churn-risk categories using the provided churn score.
- Visualize churn trends and relationships between customer and subscription variables.

## Tools & Technologies

- **Python** — analysis and feature engineering
- **Pandas** — data cleaning, transformation, joins, grouping, and pivot tables
- **NumPy** — churn flags and conditional categorization
- **Matplotlib** — churn trend and comparison charts
- **Seaborn** — correlation heatmaps, pair plots, and categorical comparisons
- **SQLite** — storing and querying the workbook's tables
- **Jupyter Notebook** — interactive analysis and documentation
- **Excel** — source data



## Workflow

### 1. Load Data

- Read the Excel workbook and its three sheets.
- Create a local SQLite database and load each sheet as a table.
- Read the tables into Pandas DataFrames.

### 2. Data Cleaning

- Rename `name` to `customer_name`.
- Remove the `interests` and `pincode` columns from the customer table.
- Convert date columns to datetime types.
- Standardize gender values such as `Men` and `Women` to `Male` and `Female`.
- Fill missing country values using the state-to-country mapping available in the data.
- Remove unused columns from the support table.
- Check support records for multiple entries per customer before joining.

### 3. Feature Engineering & Data Preparation

- Create `churn_flag`: `1` when `cancellation_date` is present, otherwise `0`.
- Calculate complaint counts by customer.
- Merge subscription, customer, and support data using `customerid`.
- Calculate customer tenure in days.
- Categorize churn scores into `low`, `med`, and `high` risk groups.
- Export the merged data to `exported_churn_data.csv`.

### 4. KPI Analysis

The notebook calculates:

- Churn rate and retention rate
- Churn rate by plan type
- Average revenue per user (ARPU)
- Average customer tenure
- Monthly charges associated with churned customers (revenue at risk)
- Support escalation rate
- Average complaints per customer
- Correlation between escalation status and churn

### 5. Visualization

The notebook includes:

- Monthly churn trend line chart
- Churn rate by plan type
- Churn rate by state
- Correlation heatmap
- Pair plot of selected encoded variables
- Monthly charges by plan type, gender, and churn-risk category
- Pandas pivot tables for comparing plan-level metrics

## Example Results From the Notebook

The following are the outputs currently recorded in the notebook. Because the sample is small, these values should be treated as **illustrative**, not as reliable estimates for a larger customer base.

| Metric | Recorded result |
|---|---:|
| Churn rate | 28.57% |
| Retention rate | 71.43% |
| Average monthly charges (ARPU as calculated in notebook) | 18.85 |
| Average tenure | 1,452 days |
| Monthly charges associated with churned customers | 73.94 |
| Escalation rate | 19.05% |
| Average complaints per customer | 0.43 |
| Correlation between escalation and churn | 0.77 |

### Churn Rate by Plan Type

| Plan type | Churn rate |
|---|---:|
| Basic | 60.00% |
| Standard | 22.22% |
| Premium | 14.29% |

These figures reflect the notebook's current data and calculations. The correlation value does not establish that escalations cause churn. Also, the notebook labels the revenue-at-risk value as `Rs 'K'`, but the source file does not establish the currency or scale; verify units before presenting it as a financial result.


## Skills Demonstrated

- Data cleaning and missing-value handling
- Data type conversion and standardization
- SQL database creation and table inspection with SQLite
- Joining multiple tables
- Feature engineering with Pandas and NumPy
- KPI calculation and grouped analysis
- Exploratory data analysis (EDA)
- Data visualization with Matplotlib and Seaborn
- Correlation analysis and pivot tables
- Communicating analytical findings with appropriate caveats

## Conclusion

This project demonstrates an end-to-end customer churn analysis workflow, from data loading and cleaning through feature engineering, KPI calculation, and visualization. It showcases practical Python-based analytics skills and provides a starting point for investigating churn and customer-support patterns.
