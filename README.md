# Financial Health Executive Dashboard (Power BI)

A comprehensive, interactive Power BI dashboard designed to analyze and evaluate the financial stability of individuals based on socioeconomic factors. This report transforms raw population metrics into actionable financial risk assessments.

## 📄 Project Overview
This dashboard tracks and visualizes the financial landscape of a 100-individual cohort. It highlights the correlations between financial stress (instability) and variables like savings, debt accumulation, employment status, and monthly expenditure.

### Key Insights Tracked:
* **Total Cohort Size:** 100 individuals
* **Average Monthly Expenses:** ₹2.9K
* **Debt to Saving Percentage:** 39.29%
* **Financial Instability Rate:** 100.00% of the monitored group in this specific view.

---

## 📊 Dashboard Architecture

### 1. Executive Summary (Top Ribbon KPI Cards)
* **Total Population:** High-level count of individuals tracked.
* **Average Expenses:** Aggregated average of monthly spending patterns.
* **Dept to Saving Percentage:** A core metric measuring the total leverage ratio.
* **Unstable Percentage:** The proportion of individuals flagged with an unstable financial status.

### 2. Risk & Stability Drivers (Scatter Plot)
* **Savings vs. Debt Analysis:** Maps individuals as distinct data points to visually isolate the cluster thresholds where debt-to-savings ratios cross into financial instability.

### 3. Socioeconomic Profiles (Clustered Column Chart)
* **Stability by Employment Status:** Cross-references employment metrics against stability categories to demonstrate the impact of job security on overall financial wellness.

---

## 🛠️ DAX Measures Used

### Unstable Population Percentage
```dax
unstable = 
DIVIDE(
    CALCULATE(
        COUNT(Sheet1[Individual_ID]), 
        Sheet1[Financial_Stability] = "Unstable"
    ), 
    COUNT(Sheet1[Individual_ID])
)
