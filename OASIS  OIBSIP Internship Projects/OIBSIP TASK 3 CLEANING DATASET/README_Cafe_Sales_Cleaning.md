# Cafe Sales — Data Cleaning Project

## Overview
A data cleaning project that transforms a messy, real-world cafe sales dataset (`dirty_cafe_sales.csv`) into an analysis-ready dataset by systematically identifying and fixing missing values, placeholder strings, type errors, and duplicates.

## Data Quality Issues Identified
- Placeholder strings (`"ERROR"`, `"UNKNOWN"`) used in place of true missing values
- Incorrect data types (numeric/date columns stored as text)
- Missing values across `Item`, `Quantity`, `Price Per Unit`, `Total Spent`, `Payment Method`, `Location`, and `Transaction Date`
- Duplicate rows and duplicate Transaction IDs
- Value-range anomalies in numeric columns

## Cleaning Process
1. **Standardization** — unify all placeholder strings to `NaN`, strip whitespace
2. **Type Correction** — cast columns to appropriate types (string, Int64, float64, category, datetime)
3. **Missing Data Recovery** — exploit the dataset's structural relationships to recover values algebraically:
   - `Quantity × Price Per Unit = Total Spent` used to back-fill any one missing field from the other two
   - Near 1:1 `Item ↔ Price` mapping used to recover missing `Item` or `Price Per Unit`
   - `Payment Method` / `Location` missing values kept as an explicit "Missing" category rather than imputed
   - Rows with unrecoverable `Transaction Date` (or still missing core fields) dropped as a last resort
4. **Duplicate Removal** — full-row duplicates and duplicate Transaction IDs removed
5. **Outlier Detection** — IQR method applied to numeric columns, with consistency checks to confirm flagged outliers were genuine, not data-entry errors
6. **Before vs. After Summary** — row counts, dtype accuracy, and null counts compared pre/post cleaning

## Output
Cleaned dataset saved as `cafe_sales_cleaned.csv`, with zero nulls and consistent types.

## Tech Stack
Python · pandas · NumPy

## Files
- `cafe_sales_cleaning.ipynb` — full cleaning notebook
