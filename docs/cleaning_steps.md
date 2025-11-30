# Data Cleaning & Transformation Steps — Hospital ER Dataset

This document describes all data preprocessing steps performed before building the Power BI dashboard.  
Good data cleaning ensures accurate KPIs, improved model performance, and reliable insights.

---

## 1. Initial Data Inspection
- Loaded raw CSV into Power Query (Power BI).
- Checked column types (Text, Number, DateTime).
- Verified row count and duplicates.
- Identified missing values in key fields:
  - Waittime
  - Satisfaction Score
  - Department Referral
  - Admission Status

---

## 2. Handling Missing Values
### Waittime
- Null wait times removed or imputed depending on use case.  
(For dashboards, removal is recommended to preserve accuracy.)

### Satisfaction Score
- Missing values left blank because they don’t affect categorical metrics.

### Department Referral
- Empty/Null replaced with `"None"`.

---

## 3. Removing Duplicates
- Removed duplicates based on:
  - `Patient Id`
  - `Patient Admin Date`
- Duplicate patient entries on same date were treated as data errors.

---

## 4. Standardizing Text Fields
Applied the following transformations:
- Trim + Clean (to remove spaces)
- Capitalized inconsistent categories  
Examples:
- `"male"`, `"M"` → `"Male"`  
- `"f"`, `"Female"` → `"Female"`  
- Referral department variations mapped to one standard name.

---

## 5. Creating Date & Time Columns
Extracted time-based fields for visualizations:
- **AdmDate** (Date)
- **AdmHour** (Hour from timestamp)
- **AdmDay** (Day of the week)
- **AdmMonthYear** (MMM-YYYY)

These help build:
- Day vs Hour heatmap  
- Trend charts  
- Slicers

---

## 6. Converting Column Types
Ensured correct datatypes:
- Waittime → Whole number
- Satisfaction Score → Decimal number
- Patient Admin Date → Date/Time
- Gender / Race / Referral → Categorical text

---

## 7. Outlier Treatment (Optional)
Wait times above 300 minutes considered extreme outliers.  
Depending on analysis goals:
- Either removed  
or  
- Categorized as `">300 mins"`

---

## 8. Creating Dimension Tables (Best Practice)
Split dataset into:
- **Fact_ERVisits**
- **Dim_Patient**
- **Dim_Referral**
- **Dim_Date**

Improves relationships in data model and avoids ambiguity.

---

## 9. Creating Age Groups (If Age Provided)
Age grouped as:
- 0–19  
- 20–29  
- 30–39  
- 40–50  
- 50+  

Used for bar chart age distribution.

---

## 10. Final Validation
- Cross-checked row counts after cleaning.
- Verified wait time distribution with histograms.
- Confirmed correct relationship mapping.
- Ensured no broken visuals after data load.

---

### Notes
- Use Power Query Steps pane to document transformations.
- Cleaning pipeline must be updated when source data changes.
