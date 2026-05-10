# 🛡️ RiskPulse — Insurance Intelligence Platform

> **A 3-page interactive Power BI dashboard that transforms raw insurance data into clear, actionable intelligence for risk decision-makers.**

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)
![Data Modeling](https://img.shields.io/badge/Data%20Modeling-217346?style=for-the-badge&logo=microsoftexcel&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)

---

## 📌 Project Overview

Insurance companies manage thousands of policies across multiple regions, risk categories, and customer demographics. The challenge is not collecting data — it's making that data **fast, visual, and useful** for analysts and decision-makers.

**RiskPulse** solves this by providing a fully interactive, drill-through enabled intelligence platform with:
- Executive-level KPI summaries
- Policy-level deep dive with dynamic filtering
- Behavioral risk driver analysis

---

## 🖥️ Dashboard Preview

| Page | Description |
|------|-------------|
| 📊 Risk Overview Dashboard | KPIs, regional breakdowns, premium vs claim trends |
| 🔍 Risk Deep Dive | Policy-level data table with heatmap risk scoring |
| 📈 Risk Drivers & Behavior | Behavioral patterns, demographics, violation trends |

---

## 📊 Page 1 — Risk Overview Dashboard

**Goal:** Give leadership a bird's-eye view of the entire insurance portfolio.

### Key Metrics (KPI Cards)
| Metric | Value |
|--------|-------|
| Total Policies | 50,000 |
| Avg Risk Score | 40.96 |
| Loss Ratio | 1.75 |
| High Risk % | 52.08% |
| Total Premium | $3,673M |

### Visuals Included
- 🍩 **Donut Chart** — Total Policies by Risk Category (High / Medium / Low)
- 📈 **Dual Line Area Chart** — Premium vs Claim Amount by Age Band
- 📊 **Bar Chart** — Premium and Claim by Risk Category
- 🗂️ **Matrix Table** — Drill-through by Region → Gender → Risk Level
- 📉 **Bar Chart** — Loss Ratio by Region

### Filters Available
`Region` | `Income Band` | `Risk Category`

---

## 🔍 Page 2 — Risk Deep Dive

**Goal:** Enable analysts to investigate individual policies with granular filtering.

### Key Metrics (KPI Cards)
| Metric | Value |
|--------|-------|
| Total Policies (High Risk) | 26,041 |
| Avg Risk Score | 63.54 |
| Loss Ratio | 2.04 |
| High Risk % | 52.08% |
| Total Premium | $3,01,14,89,718 |

### Features
- **Policy-Level Table** with columns: PolicyID, CustomerID, Gender, Age Band, Driving Experience, Smoker, Risk Score, Loss Ratio, Accident Band, Claims Count, Total Premium, Total Claim Amt, Income Band
- **Heatmap-style Risk Scoring** — color-coded cells for instant risk pattern recognition
- **7+ Dynamic Filters**: Region, Income Band, Risk Category, Age Band, BMI Category, Accident Band, Driving Experience

---

## 📈 Page 3 — Risk Drivers & Behavior Analysis

**Goal:** Uncover what behavioral and demographic factors drive risk in the portfolio.

### Key Metrics (KPI Cards)
| Metric | Value |
|--------|-------|
| Total Policies (High Risk) | 26,041 |
| Avg Risk Score | 63.54 |
| Loss Ratio | 2.04 |
| High Risk % | 52.08% |
| Total Premium | $3,011M |

### Visuals Included
- 🍩 **Donut Chart** — Loss Ratio by Income Band (High / Medium / Low)
- 📋 **Table** — Top 10 High Risk Score Levels by Customer Count
- 📊 **Bar Chart** — Total Policies by BMI Category
- 📈 **Area Chart** — Total Customers & Avg Risk Score by Driving Experience Band
- 📉 **Area Chart** — Traffic Violations and Risk Profile
- 📊 **Combo Chart** — Customer Age Groups and Risk Levels

### Toggle Buttons
`Loss Ratio` | `Income Band` | `Avg Risk Score` | `Chronic Condition`

### Filters Available
`Region` | `Income Band` | `Risk Category` | `Gender`

---

## 💡 Key Insights

| # | Insight |
|---|---------|
| 1 | 🔴 **West region** has the highest Loss Ratio at **3.12** — highest risk exposure |
| 2 | 🟢 **South region** is most profitable with a Loss Ratio of just **0.57** |
| 3 | ⚠️ **High Risk policies** account for **52%** of the entire portfolio |
| 4 | 🚗 **Veteran Drivers (21+ yrs)** form the largest customer segment (23,860 customers) |
| 5 | 📉 Risk score drops consistently as driving experience increases |
| 6 | 🚬 Smokers show a higher average risk score across all age bands |

---

## 🎨 Design System

| Element | Value |
|---------|-------|
| Primary Background | `#0A1628` (Navy) |
| Accent Color | `#EF9F27` (Gold/Amber) |
| Risk High Color | `#E05A2B` (Salmon-Orange) |
| Risk Low Color | `#C8D8A8` (Soft Green) |
| Font Style | Clean sans-serif, white on dark |
| Layout | 3-page navigation with persistent left sidebar |

**Design Principles:**
- Executive KPIs always pinned at the top
- Heatmap color encoding for quick risk scanning
- Drill-through enabled for all region/gender/category breakdowns
- Consistent branding across all 3 pages

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|------|---------|
| **Power BI Desktop** | Dashboard development & publishing |
| **DAX** | Calculated columns, measures, KPI logic |
| **Power Query (M)** | Data transformation & cleaning |
| **Data Modeling** | Star schema relationships |
| **Custom Visuals** | Enhanced chart types |

---

## 📁 Project Structure

```
RiskPulse-Insurance-Intelligence/
│
├── 📂 Dashboard/
│   ├── 01_Risk_Overview.png
│   ├── 02_Risk_Deep_Dive.png
│   └── 03_Risk_Drivers_Behavior.png
└── README.md
```

---

## 📐 DAX Measures (Sample)

```dax
-- Loss Ratio
Loss Ratio = DIVIDE([Total Claim Amount], [Total Premium], 0)

-- Avg Risk Score
Avg Risk Score = AVERAGE(Insurance[RiskScore])

-- High Risk %
High Risk % = 
DIVIDE(
    CALCULATE(COUNTROWS(Insurance), Insurance[RiskCategory] = "High Risk"),
    COUNTROWS(Insurance),
    0
) * 100

-- Total Premium
Total Premium = SUM(Insurance[TotalPremium])
```

---

## 📊 Dataset Overview

| Column | Description |
|--------|-------------|
| PolicyID | Unique policy identifier |
| CustomerID | Customer reference |
| Gender | Male / Female |
| Age Band | Age group (18-20 to 71-75) |
| Driving Experience Band | New Driver to Veteran Driver |
| Smoker | Yes / No |
| Risk Score | 0–100 composite risk score |
| Loss Ratio | Claim Amount / Premium |
| Accident Band | No Accidents / 1 Accident / 2+ |
| Claims Count | Number of claims filed |
| Total Premium | Policy premium amount |
| Total Claim Amt | Total claims amount |
| Income Band | High / Medium / Low |
| BMI Category | Underweight / Normal / Overweight / Obese |
| Region | East / West / North / South |

---

## 🤝 Connect With Me

If you found this project useful or have feedback, feel free to connect:

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/yourprofile)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/data-analyst-harsh-son)

> ⭐ **If you like this project, please give it a star — it helps others discover it!**

---

## 📄 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

---

*Built with ❤️ using Power BI | Designed for Insurance Analytics & Risk Intelligence*
