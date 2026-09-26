# 🦈 Shark Tank India — Investment Analysis Dashboard

An interactive Power BI dashboard analyzing 3 seasons of Shark Tank India — covering deal patterns, industry performance, investor behavior, and equity/debt structuring across 478 startup pitches.

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=flat&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-Data%20Modeling-blue)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)

---

## 📊 Overview

This dashboard breaks down Shark Tank India's investment activity to answer a core question: **what actually drives a deal from pitch to funding?** It covers industry trends, deal conversion rates, shark participation patterns, and the equity-vs-debt mix of accepted deals — across two report pages.

## 🗂️ Dataset

- **Source:** Shark Tank India dataset (Seasons 1–3), cleaned CSV
- **Rows:** 478 startup pitches
- **Key fields:** Season/Episode number, Industry, Ask Amount, Valuation, Received/Accepted Offer, Total Deal Amount/Equity/Debt, per-shark investment amount & equity, Number of Sharks in Deal

## 🛠️ Tech Stack

- **Power BI Desktop** — data modeling, DAX measures, report design
- **Power Query (M)** — data cleaning and table shaping
- **DAX** — custom measures for KPIs, ratios, and aggregations

## 📈 Dashboard Pages

### Page 1 — Investment Overview
| Visual | Insight |
|---|---|
| KPI Cards | Total Investment, Total Pitches, Accepted Deals, Total Offers |
| Investment by Industry | Which industries attract the most shark capital |
| Total Pitches by Season | Pitch volume trend across seasons |
| Deal vs No-Deal Split | Overall pitch-to-deal conversion rate |
| Investment Share by Number of Sharks in Deal | How co-investment among sharks affects deal size |

### Page 2 — Deal Dynamics
| Visual | Insight |
|---|---|
| Pitch-to-Deal Funnel | Where pitches drop off in the deal pipeline |
| Deal Size vs Acceptance Rate by Industry | Industries with the best risk/reward profile |
| Average Ask Amount by Industry | Valuation expectations by sector |
| Equity vs Debt Split by Season | How deal structuring has shifted over time |

## 🧮 Key DAX Measures

```DAX
Total Investment = SUM('SharkTank'[Total Deal Amount])

Startups Got Investment = 
CALCULATE(
    DISTINCTCOUNT('SharkTank'[Startup Name]),
    'SharkTank'[Accepted Offer] = 1
)

Average Investment per Deal Startup = 
DIVIDE([Total Investment], [Startups Got Investment])

Deal Conversion Rate = 
DIVIDE([Startups Got Investment], [Total Startups])

Total Episodes = 
COUNTROWS(
    SUMMARIZE('SharkTank', 'SharkTank'[Season Number], 'SharkTank'[Episode Number])
)
```

## ❓ Business Questions Answered

- Which industries attract the most investment, and which are pitched often but rarely funded?
- What percentage of pitches convert into an actual deal?
- Do multi-shark deals tend to be larger, or does co-investment mean thinner individual stakes?
- Which industries offer the best combination of high deal size and high acceptance rate?
- Has the equity-vs-debt structure of deals shifted across seasons?
- At what stage of the pitch process do most founders drop off — no offer, or offer rejected?

## 🎨 Design

- Dark navy/teal theme with a custom background
- Custom Power BI theme JSON for consistent colors, fonts, and card styling across both pages
- Chart titles and KPI cards styled for readability against the background art

## 📷 Preview

*(Add dashboard screenshots here — drag image files into this repo and reference them like below)*

```markdown
![Page 1 - Investment Overview](screenshots/page1.png)
![Page 2 - Deal Dynamics](screenshots/page2.png)
```

## 🚀 How to Use

1. Clone this repository
2. Open `shark_tank_investment_analysis_dashboard.pbix` in Power BI Desktop
3. If prompted, update the data source path to point to your local copy of the CSV
4. Explore both report pages using the slicers/filters and Reset Filters button

---

## 👤 Author

**Azli Khan**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/azli-khan07)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Azli45)

*Built as a data analysis and Power BI practice project using the Shark Tank India dataset.*
