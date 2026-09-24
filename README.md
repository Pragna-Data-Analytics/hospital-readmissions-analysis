
# Hospital Readmissions Analysis

Operational analysis of hospital readmissions using Excel and Power BI, identifying
which patient segments carry the highest readmission risk.

## Business Question

**Which patient segments have elevated readmission rates, and what operational factors
should hospital administrators focus on to reduce readmissions?**

## Dataset

[Hospital Readmissions Dataset](https://www.kaggle.com/datasets/dubradave/hospital-readmissions)
(Kaggle) — 25,000 hospital stay records, including patient age, length of stay,
admitting specialty, diagnosis category, and readmission outcome.

## Tools Used

- **Excel** — data cleaning and pivot table analysis
- **Power BI** — interactive dashboard

## Method

1. Cleaned the dataset in Excel, confirming no missing values and correcting a stray
   phantom row picked up by an oversized pivot table source range
2. Built pivot tables calculating readmission rate by age bracket, medical specialty,
   and length of stay (grouped into bands)
3. Rebuilt the same analysis as an interactive Power BI dashboard using a custom DAX
   measure for readmission rate, cross-validated against the Excel results

## Key Findings

| Segment        | Finding                                                                      |
| -------------- | ---------------------------------------------------------------------------- |
| Overall        | 47.02% readmission rate (see note on dataset balancing below)                |
| Age            | Rises from 44.5% (40-50) to 49.6% (80-90), drops to 42.1% (90-100)           |
| Specialty      | Highest: Family/GeneralPractice (49.5%); Lowest: Surgery (41.2%)             |
| Length of stay | Rises from 44.3% (1-3 days) to 50.7% (7-9 days), eases to 46.2% (13-15 days) |

Full write-up and recommendations:
[`reports/business_summary.md`](reports/business_summary.md)

## Dashboard

Interactive Power BI dashboard: [`dashboard/hospital_readmissions_dashboard.pbix`](dashboard/hospital_readmissions_dashboard.pbix)
(open with Power BI Desktop, free download)

## Project Structure

```
hospital-readmissions-analysis/
├── data/                              # Raw CSV (not included — download from Kaggle link above)
├── excel/
│   └── hospital_readmissions.xlsx     # Cleaned data + pivot table analysis
├── dashboard/
│   └── hospital_readmissions_dashboard.pbix
├── reports/
│   └── business_summary.md
└── README.md
```

## How to Reproduce

1. Download the dataset from the [Kaggle link above](https://www.kaggle.com/datasets/dubradave/hospital-readmissions)
2. Open in Excel and build pivot tables as described in `excel/hospital_readmissions.xlsx`
3. Open `dashboard/hospital_readmissions_dashboard.pbix` in Power BI Desktop to explore
   the interactive dashboard

## Notable Data Quality Note

An early pivot table showed a phantom "(blank)" category with #DIV/0! errors, despite
the source data having zero actual missing values. This was traced to the pivot table's
source range extending beyond the real data (a common Excel artifact after row edits),
not a genuine data quality issue. It was resolved by manually specifying the exact data
range (`A1:Q25001`) rather than relying on Excel's auto-detected range.
