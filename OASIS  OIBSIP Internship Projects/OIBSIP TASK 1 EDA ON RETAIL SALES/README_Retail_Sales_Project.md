# Retail Sales Dataset — Exploratory Data Analysis

## Objective
Uncover patterns, customer behavior trends, and actionable business insights from retail transaction data.

## Dataset
- `retail_sales_dataset.csv` — 1,000 transactions across 9 columns
- Clean dataset: zero missing values, zero duplicates
- Fields: transaction ID, date, customer ID/gender/age, product category, quantity, price per unit, total amount

## Analysis Performed
1. **Descriptive Statistics** — mean, median, mode, std for Age, Quantity, Price per Unit, Total Amount
2. **Time Series Analysis** — monthly and quarterly sales trends
3. **Customer Demographics** — spending patterns by age group and gender
4. **Product Analysis** — revenue and quantity by category; top 10 product lines by revenue (using category + price as a proxy, since no individual product-name column exists)
5. **Correlation Analysis** — heatmap of numerical variables
6. **Additional Insights** — age group × category spending heatmap; day-of-week sales patterns

## Key Insights
- Revenue is split almost evenly across the three categories (Beauty, Clothing, Electronics)
- Beauty sells the most units at lower prices; Clothing and Electronics earn similar revenue from fewer, higher-priced sales
- Gender has little effect on average spend per transaction
- Age barely correlates with spending, suggesting age-based targeting alone wouldn't move revenue much
- Sales are spread fairly evenly across the week rather than peaking on weekends

## Business Recommendations
1. Bundle high-volume Beauty items with higher-margin Clothing/Electronics items to raise average order value
2. Target promotions by age + category combination rather than age alone
3. Reconsider weekend-only promotions, since demand is steady throughout the week

## Tech Stack
Python · pandas · NumPy · Matplotlib · Seaborn

## Files
- `Retail_Sales_Project.ipynb` — full EDA notebook
