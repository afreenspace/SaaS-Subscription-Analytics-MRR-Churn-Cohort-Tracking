# SaaS Subscription Analytics — MRR, Churn & Cohort Retention

An Excel-based analytics project simulating the monthly revenue analysis performed by Revenue Operations / Business Analyst teams at subscription-based (SaaS) companies. Built as part of a self-directed data analyst portfolio.

## 📁 Repository Structure
SaaS-Subscription-Analytics-MRR-Churn-Cohort-Tracking/
├── Data/
│ └── SaaS_Subscription_Data.xlsx
├── Screenshots/
│ ├── Key_Metrics_Dashboard.png
│ ├── Cohort_Retention.png
│ ├── Plan_Region_Summary.png
│ └── Waterfall_Data.png
├── README.md
└── LICENSE

## 📌 Overview

Subscription revenue isn't static — every month, customers join, upgrade, downgrade, and cancel. This project tracks that movement end-to-end: from raw subscription events to a full KPI dashboard, using a synthetic-but-realistic dataset modeled on how real SaaS billing systems (e.g. Stripe, Chargebee) export data.

**Business question answered:** *Is this company actually growing, and which customers/plans/channels are driving growth or leaking revenue?*

## 📸 Dashboard Preview

**KPI Dashboard & Active Customers Trend**
![Key Metrics Dashboard](Screenshots/Key_Metrics_Dashboard.png)

**Cohort Retention Heatmap**
![Cohort Retention](Screenshots/Cohort_Retention.png)

**Plan / Region / Channel Breakdown**
![Plan Region Summary](Screenshots/Plan_Region_Summary.png)

**MRR Waterfall (Month-over-Month Bridge)**
![Waterfall Data](Screenshots/Waterfall_Data.png)

## 📁 Dataset

- **320 customers**, **24 months** of history (Jan 2024 – Dec 2025)
- **~3,200 subscription ledger rows** — one row per customer per active month
- Two linked tables:

- `Customer_Master` — customer ID, signup date (cohort), plan at signup, acquisition channel, region, industry
- `Subscription_Ledger` — customer ID, month, plan, MRR, event type (New / Renewal / Upgrade / Downgrade / Churn)
- Simulated with realistic SaaS behavior: lower-tier plans churn faster than higher tiers, a subset of customers upgrade over time, and revenue movement isn't perfectly clean (a small reconciliation gap exists between categories, as in real billing data)

## 🛠️ Methodology

| Stage | What was built |
|---|---|
| 1. Data generation | Synthetic subscription ledger modeled on real SaaS billing exports |
| 2. Data structuring | Excel Tables, verified date typing, clean sheet architecture |
| 3. Core metrics | SUMIFS / COUNTIFS / AVERAGEIFS for active customers, total MRR, avg MRR per customer |
| 4. MRR movement | New / Expansion / Contraction / Churned MRR, using a Prior-Month-MRR lookup pattern |
| 5. Churn & growth rates | Monthly customer churn rate and MRR growth rate |
| 6. Cohort retention | 21-cohort × 12-month retention matrix, conditional-formatted as a heatmap |
| 7. Waterfall chart | Month-over-month MRR bridge (Starting → New → Expansion → Contraction → Churn → Ending) |
| 8. Dashboard | KPI cards, trend charts, and Plan/Region/Acquisition Channel breakdowns |

## 🔍 Key Findings

- **Acquisition freeze, not just churn:** New customer acquisition dropped to **zero** for three consecutive months (Oct–Dec 2025), while churn continued unabated — the customer count decline traced back to a stalled acquisition funnel, not just elevated churn.
- **Churn running hot:** Monthly churn rates ranged from ~5–10%, above the 2–5% typical healthy-SaaS benchmark, with cohort retention confirming this wasn't isolated to one signup period.
- **Revenue concentration:** Enterprise-tier customers make up ~24% of the active base but generate over half of total MRR — a small, high-value segment worth prioritizing for retention efforts.
- **Channel performance:** Organic Search outperforms paid channels on revenue contribution, not just customer volume — suggesting acquisition spend could be reallocated.

## 📊 Tools & Techniques

- Excel Tables & structured references
- SUMIFS, COUNTIFS, AVERAGEIFS, XLOOKUP, EDATE
- Cohort retention analysis (matrix-style, INDEX/MATCH pattern)
- MRR waterfall charting
- Conditional formatting (heatmaps)
- KPI dashboard design with trend visualizations

## 📂 Files

- `Data/SaaS_Subscription_Data.xlsx` — full workbook (raw data, ledger, cohort matrix, dashboard, charts)
- `Screenshots/` — dashboard preview images (KPI view, cohort heatmap, plan/region breakdown, MRR waterfall)

## 👤 Author

Built by Afreen as part of a self-taught data analyst portfolio, targeting data analyst roles at MNCs (TCS, Infosys, Accenture, Capgemini). Third project in the series, following an IT Service Desk SLA Compliance dashboard.

## ▶ Usage

- Open `Data/SaaS_Subscription_Data.xlsx` in Excel (desktop) to view the dashboard, cohort matrix, and supporting tables.
- Typical sheets: `Raw_Data`, `Customer_Master`, `Subscription_Ledger`, `Cohort_Retention`, `Dashboard`.
- All metrics are computed with Excel formulas (SUMIFS/COUNTIFS/XLOOKUP/EDATE); no external code is required.

## 📄 License

This repository is distributed under the MIT License. See `LICENSE` for details.
