# Banking Customer Data Analysis Project

This project analyzes Indian bank customer data using **Python (pandas, numpy, matplotlib)**
to clean the data and generate insights covering all the requirements listed in `Banking.pdf`.

## Folder Structure

```
banking_project/
│
├── Banking.pdf                                  # Original requirement document (what to find/analyze)
├── indian_bank_customers_10000_enhanced.csv     # Raw source data (10,200 customers)
├── clean_bank_customers.csv                     # Cleaned data (generated after running the notebook)
├── banking_analysis.ipynb                       # Main source code (Jupyter Notebook)
├── README.md                                    # This file
│
└── charts/                                      # All output chart images (14 PNG files)
    ├── chart1_null_values.png
    ├── chart2_loyalty_count.png
    ├── chart3_risk_distribution.png
    ├── chart4_income_boxplot.png
    ├── chart5_state_income_heatmap.png
    ├── chart6_loans_vs_income.png
    ├── chart7_ccbalance_by_risk.png
    ├── chart8_state_metrics.png
    ├── chart9_loan_vs_deposit.png
    ├── chart10_top10_customers.png
    ├── chart11_top_cities.png
    ├── chart12_age_distribution.png
    ├── chart13_gender_ratio.png
    └── chart14_gender_behavior.png
```

## How to Run

1. Open `banking_analysis.ipynb` in Jupyter Notebook / JupyterLab / VS Code.
2. Make sure `indian_bank_customers_10000_enhanced.csv` is in the **same folder** as the notebook.
3. Run all cells top to bottom (Kernel → Restart & Run All).
4. `clean_bank_customers.csv` and all 14 chart PNGs will be generated automatically.

**Libraries needed:** `pandas`, `numpy`, `matplotlib` 

## What Each Section Covers (mapped to Banking.pdf requirements)

| Notebook Section | Banking.pdf Project | What it does |
|---|---|---|
| 1 & 11. Data Cleaning + Data Quality Monitoring | Project 1, 11 | Detect NULLs, remove duplicates, validate age, fix missing income/occupation/CC balance/business lending, NULL bar chart |
| 2. Customer Segmentation | Project 2 | Group by Loyalty, Risk, Gender, State; identify High-Value / Risky / Low-Profit customers; bar charts, box plot, state income heatmap |
| 3. Credit Risk Analysis | Project 3 | Loans vs Income scatter, CC Balance vs Risk, red-flag detection (high loan+low income, multi-property+high debt) |
| 4 & 5. State/City Performance + Revenue | Project 4, 5 | State-wise deposits/loans/business lending, total revenue KPIs, loan vs deposit pie chart |
| 6. Customer Profitability | Project 6 | Loan-to-income ratio, profitability score, top 10 high-value customers |
| 7. Risk Exposure | Project 7 | High-risk customer count, total loan exposure |
| 8. Expansion Strategy | Project 8 | Top cities by customer count and avg income (branch expansion candidates) |
| 9. Demographics | Project 9 | Age group distribution, gender ratio |
| 10. Executive Overview | Project 10 | One-page summary: total customers, deposits, loan exposure, risk ratio |
| 12. Gender-based Financial Behavior | Project 12 | Compare avg income, loans, savings, CC balance by gender |

## Notes / Assumptions

- **Gender**: `GenderId` 1 = Male, 2 = Female (assumed, no legend was provided with raw data).
- **Risk Weighting**: 1 = Low risk, 5 = High risk.
- Missing **Occupation** → filled as "Unknown".
- Missing **Estimated Income** and **Credit Card Balance** → filled with median.
- Missing **Business Lending** → filled with 0 (assumed no business lending recorded).
- **Profitability Score** is a simple illustrative formula (deposits × 2% + loans × 9% − CC balance × 1%), not an official bank metric — dataset has no real revenue/interest column.
