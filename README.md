# 📊 Excel Data Intelligence Project

> **A comprehensive Excel-based data analytics project showcasing advanced spreadsheet techniques, business intelligence, and data storytelling — built entirely in Microsoft Excel without any external BI tools.**

---

![Excel](https://img.shields.io/badge/Microsoft_Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Data_Intelligence-blue?style=for-the-badge)
![Sheets](https://img.shields.io/badge/Analysis_Tabs-10%2B-orange?style=for-the-badge)

---

## 📁 Project Structure

```
Excel_Final_Pr/
├── PR. Final Project.xlsx            # Main Excel workbook (all analysis + dashboard)
└── Screenshots/
    ├── Dashboard.png                 # Interactive KPI dashboard
    ├── 1_Date_Time.png               # Date & Time engineering
    ├── 2_Filter.png                  # Dynamic FILTER function
    ├── 3_ConditionalFormating.png    # Conditional formatting with icon sets
    ├── 4_WhatIF.png                  # Goal Seek & Scenario Manager
    ├── 5_Regression.png              # Linear regression analysis
    ├── 6_Storytelling.png            # Data storytelling insights
    ├── 7_HighValueCustomer.png       # Customer segmentation
    ├── 8_PivotTables.png             # Pivot tables & charts
    ├── 9_MatchingNames.png           # Text functions & name matching
    └── 10_Final_Report.png           # Executive summary report
```

---

## 🎯 Project Overview

This project demonstrates a **complete data analytics workflow** built entirely in Microsoft Excel — from raw transaction data to an interactive business intelligence dashboard.

It covers date/time engineering, dynamic filtering, conditional logic, scenario planning, regression analysis, pivot reporting, and customer segmentation — all culminating in an executive-ready insights report and a live dashboard.

### 📊 Key Business Metrics

| Metric | Value |
|---|---|
| 💰 Total Revenue | ₹2,29,192.47 |
| 📦 Total Quantity Sold | 753 Units |
| 👥 Total Customers | 250 |
| 🏆 Highest Customer Spend | ₹15,659.65 |
| 🌏 Top Region | East — ₹59,288.39 |
| 📦 Best-Selling Product | Bookshelf — 102 Units |

---

## 🖥️ Data Intelligence Dashboard

The final dashboard integrates all analysis into a single, fully interactive view — built 100% natively in Excel without any external BI tools.

![Dashboard](./Screenshots/Dashboard.png)

**Dashboard Components:**

| Component | Description |
|---|---|
| 📊 Product Wise Sales Quantity | Bar chart comparing all 10 products |
| 🥧 Region Wise Revenue Distribution | Pie chart across 5 regions |
| 📈 Monthly Revenue Trend | Line chart showing Jan–Dec seasonality |
| 🔢 Live KPI Tiles | Revenue, Quantity, Customers, Top Spend |
| 🎛️ Interactive Slicers | Filter by Category, Region & Customer Segment |

> The entire dashboard updates automatically when slicers are applied — no manual refresh needed.

---

## 🛠️ Features & Techniques

### 1️⃣ Date & Time Engineering

![Date & Time](./Screenshots/1_Date_Time.png)

Dynamic date columns were engineered to enable time-based analysis and ensure the workbook stays live with every open.

**Formulas Used:**

| Formula | Purpose |
|---|---|
| `TODAY()` | Captures the current date dynamically |
| `NOW()` | Records the current date and timestamp |
| `EOMONTH()` | Computes the last day of each transaction month |
| `Customer_Age_Days` | Days since each customer first transacted (791–1747 days range) |
| `Timestamp` | Logs the exact moment of data refresh |

> These formulas ensure the workbook stays live and auto-updates with every open, eliminating manual date maintenance.

---

### 2️⃣ FILTER Function — Multi-Value Dynamic Returns

![Filter Function](./Screenshots/2_Filter.png)

Using Excel's modern `FILTER()` function to return entire rows matching business criteria without copy-paste or manual sorting.

```excel
=FILTER(TransactionTable, [Category]="Electronics", "No Results")
```

**Capabilities:**

| Feature | Detail |
|---|---|
| Dynamic output | Returns all matching rows automatically |
| Multi-condition support | AND / OR logic within one formula |
| Zero maintenance | Results auto-expand as new data is added |
| Fallback handling | Shows "No Results" when no match is found |

> Requires Excel 365 or Excel 2021+. Older versions will show `#NAME?` — see Getting Started for compatibility notes.

---

### 3️⃣ Conditional Formatting — Visual Data Signals

![Conditional Formatting](./Screenshots/3_ConditionalFormating.png)

Applied **icon sets and color scales** on the `Total_Amount` column to create instant visual cues for transaction value classification.

**Icon Set Rules:**

| Icon | Tier | Amount Range |
|---|---|---|
| 🟢 Green Arrow ↑ | High-value transaction | ₹2,699.97 – ₹3,599.96 |
| 🟡 Yellow Arrow → | Mid-range transaction | ₹1,800 – ₹2,699.96 |
| 🔴 Red Arrow ↓ | Lower-value transaction | Below ₹1,800 |

> Allows managers to scan hundreds of rows and instantly identify outliers — without reading every number individually.

---

### 4️⃣ What-If Analysis — Goal Seek & Scenario Manager

![What-If Analysis](./Screenshots/4_WhatIF.png)

Two powerful planning tools implemented side-by-side to support business decision-making under different assumptions.

**Goal Seek:**
- Target Revenue set to ₹5,000
- Back-calculated required Quantity = **20 units** at ₹250/unit
- Useful for reverse-engineering sales targets from financial goals

**Scenario Manager — 3 Business Scenarios:**

| Scenario | Unit Price | Quantity | Projected Revenue |
|---|---|---|---|
| 🟡 Normal Case | ₹250 | 10 Units | ₹2,500 |
| 🟢 Best Case | Higher Price | Higher Volume | Maximized |
| 🔴 Worst Case | Lower Price | Lower Volume | Minimized |

> Scenario Manager enables leadership to compare outcomes side-by-side without altering the original model — ideal for budget planning and sales forecasting.

---

### 5️⃣ Regression Analysis

![Regression Analysis](./Screenshots/5_Regression.png)

A **simple linear regression** was performed using Excel's Data Analysis ToolPak to quantify the relationship between Quantity Sold and Total Revenue.

**Regression Output:**

| Statistic | Value | Interpretation |
|---|---|---|
| Multiple R | 0.458 | Moderate positive correlation |
| R Square | 0.210 | 21% of revenue variance explained by quantity |
| Adjusted R² | 0.207 | Adjusted for sample size |
| Standard Error | 919.61 | Average prediction error in ₹ |
| Observations | 250 | Full dataset used |
| F-Statistic | 65.86 | Model is statistically significant |
| Significance F | 2.26E-14 | p < 0.0001 ✅ Highly significant |

**Regression Equation:**

```
Revenue = -148.85 + (353.79 × Quantity)
```

> Each additional unit sold is associated with approximately **₹354 in additional revenue**. The model is statistically significant at the 99.99% confidence level.

---

### 6️⃣ Data Storytelling

![Storytelling Insights](./Screenshots/6_Storytelling.png)

A pivot table was transformed into a **narrative insights block** — converting raw numbers into human-readable business language for non-technical stakeholders.

**Product Sales Ranking:**

| Rank | Product | Units Sold |
|---|---|---|
| 🥇 1st | Bookshelf | 102 Units |
| 🥈 2nd | Smartphone | 96 Units |
| 🥉 3rd | Keyboard | 89 Units |
| … | … | … |
| Last | Coffee Maker | 39 Units |

**Auto-Generated Business Insights:**
1. Most purchased product is **Bookshelf** with total sales quantity of **102 units.**
2. **Smartphone** is the second most purchased product with **96 units** sold.
3. **Coffee Maker** is the least purchased product with only **39 units** sold.

> Data storytelling bridges the gap between raw pivot output and executive-ready communication — the same numbers, presented as business language.

---

### 7️⃣ High-Value Customer Segmentation

![High-Value Customers](./Screenshots/7_HighValueCustomer.png)

Customers classified using an `IF`-based formula on cumulative spending to enable targeted marketing and retention strategies.

**Segmentation Formula:**

```excel
=IF(TotalSpending > 5000, "High Value", "Regular")
```

**Top High-Value Customers:**

| Customer | Total Spend | Segment |
|---|---|---|
| Mark Carter | ₹15,659.65 | 🏆 High Value |
| Edward Mitchell | ₹11,919.77 | 🏆 High Value |
| Barbara Young | ₹10,649.80 | 🏆 High Value |
| Patricia Moore | ₹9,799.73 | 🏆 High Value |
| Paul Baker | ₹8,309.74 | 🏆 High Value |

**Segmentation Use Cases:**
- Targeted marketing campaigns for High Value customers
- Personalized retention offers and loyalty programs
- CRM data enrichment and sales team prioritization

---

### 8️⃣ Pivot Tables & Charts

![Pivot Tables](./Screenshots/8_PivotTables.png)

Multiple pivot tables and linked charts built for multi-dimensional analysis across product, region, and time dimensions.

**Charts Created:**

| Chart Type | Dimension | Purpose |
|---|---|---|
| 📊 Bar Chart | Product Wise | Units sold comparison across all 10 products |
| 📈 Line Chart | Monthly Trend | Revenue pattern from January to December |
| 🥧 Pie Chart | Region Wise | Revenue share distribution across 5 regions |

**Regional Revenue Breakdown:**

| Region | Revenue | Rank |
|---|---|---|
| East | ₹59,288.39 | 🥇 Highest |
| North | ₹50,808.31 | 2nd |
| West | ₹41,408.68 | 3rd |
| Central | ₹41,288.34 | 4th |
| South | ₹36,398.75 | 🔻 Lowest |

**Interactive Slicers Added For:**
- `Category` — Appliances / Electronics / Furniture
- `Region` — Central / East / North / South / West
- `Customer_Segment` — Basic / Premium / Standard

> All slicers are linked to every chart on the dashboard — selecting one filter updates all visuals simultaneously.

---

### 9️⃣ Matching Names & Text Functions

![Matching Names](./Screenshots/9_MatchingNames.png)

Cross-list name matching and abbreviation generation using native Excel text formulas — useful for deduplication and CRM data cleaning.

**Formulas Used:**

```excel
# Cross-list matching — returns name if found in both lists, else "-"
=IF(ISNUMBER(MATCH(List1, List2, 0)), List1, "-")

# Initials abbreviation generator
=LEFT(FirstName, 1) & LEFT(LastName, 1)
```

**Outputs:**
- Common names flagged across two customer lists (e.g., Susan Green appears in both)
- Initials generated for all 250 customers (e.g., Paul Baker → `PB`)

**Use Cases:**
- Deduplication of customer records across CRM systems
- List reconciliation between sales and marketing databases
- Generating display names or user IDs from full names

---

### 🔟 Final Insights Report

![Final Report](./Screenshots/10_Final_Report.png)

An executive summary sheet consolidating all analysis into a single-page, printable report for leadership review.

**KPI Summary:**

| KPI | Value |
|---|---|
| 💰 Total Revenue | ₹2,29,192.47 |
| 📦 Total Quantity Sold | 753 Units |
| 👥 Total Customers | 250 |
| 🏆 Highest Customer Spend | ₹15,659.65 |

**Key Business Insights:**

| # | Insight |
|---|---|
| 1 | 📦 Most purchased product is **Bookshelf** with **102 units** sold |
| 2 | 🌏 **East region** generated the highest revenue of **₹59,288.39** |
| 3 | 📉 **South region** generated the lowest revenue of **₹36,398.75** |
| 4 | 💎 Customers spending above **₹5,000** classified as High Value |
| 5 | 📅 Monthly sales **peaked in April** — **September** recorded the lowest revenue |
| 6 | 📊 **Electronics** and **Furniture** categories drove the majority of revenue |
| 7 | 🔢 Regression confirms every extra unit sold adds ~**₹354 in revenue** |

---

## 🧰 Complete Excel Skills Reference

| Category | Techniques Used |
|---|---|
| **Date & Time** | `TODAY()`, `NOW()`, `EOMONTH()`, date arithmetic, customer age calculation |
| **Dynamic Arrays** | `FILTER()` with multi-condition logic, spill ranges, fallback values |
| **Conditional Formatting** | Icon sets (directional arrows), color scales, threshold-based rules |
| **What-If Analysis** | Goal Seek (reverse calculation), Scenario Manager (3 business scenarios) |
| **Statistical Analysis** | Linear Regression via ToolPak — R², F-statistic, p-value interpretation |
| **Pivot Tables** | Multi-table, grouped by product / region / month, with slicers |
| **Charts** | Bar, Line, Pie — with custom titles, axis labels, and formatting |
| **Slicers** | Category, Region, Customer Segment — linked across all dashboard charts |
| **Text Functions** | `LEFT()`, `ISNUMBER()`, `MATCH()`, string concatenation for initials |
| **Logical Functions** | `IF()`, nested conditions for segmentation |
| **Data Storytelling** | Narrative insight blocks auto-generated from pivot output |

---

## 🚀 Getting Started

### Prerequisites

| Requirement | Version |
|---|---|
| Microsoft Excel | 2019 or Microsoft 365 (recommended) |
| Dynamic Array Support | Excel 365 or Excel 2021+ (required for `FILTER()`) |
| Data Analysis ToolPak | Free add-in built into Excel (must be enabled) |

### Setup Steps

1. **Clone or download** this repository to your local machine
2. Open **`PR. Final Project.xlsx`** in Microsoft Excel
3. Enable the **Data Analysis ToolPak:**
   `File → Options → Add-ins → Manage: Excel Add-ins → Go → Check "Analysis ToolPak" → OK`
4. Enable **macros** if prompted on file open
5. Navigate using the **sheet tabs** at the bottom to explore each analysis section
6. Open the **Dashboard** sheet and use the **slicers** to interact with all charts

> ⚠️ **Compatibility Note:** `FILTER()` and dynamic array functions require **Excel 365 or Excel 2021+**. On older versions (Excel 2016/2019), these cells will show `#NAME?` errors. All other features — Pivot Tables, Conditional Formatting, What-If Analysis, Regression — are fully compatible with Excel 2016+.

---

## 📷 Screenshots Overview

| Sheet | Description | File |
|---|---|---|
| Dashboard | Full interactive KPI dashboard | `Screenshots/Dashboard.png` |
| Sheet 1 | Date & Time Engineering | `Screenshots/1_Date_Time.png` |
| Sheet 2 | Dynamic FILTER Function | `Screenshots/2_Filter.png` |
| Sheet 3 | Conditional Formatting | `Screenshots/3_ConditionalFormating.png` |
| Sheet 4 | What-If Analysis | `Screenshots/4_WhatIF.png` |
| Sheet 5 | Regression Analysis | `Screenshots/5_Regression.png` |
| Sheet 6 | Data Storytelling | `Screenshots/6_Storytelling.png` |
| Sheet 7 | High-Value Customer Segmentation | `Screenshots/7_HighValueCustomer.png` |
| Sheet 8 | Pivot Tables & Charts | `Screenshots/8_PivotTables.png` |
| Sheet 9 | Name Matching & Text Functions | `Screenshots/9_MatchingNames.png` |
| Sheet 10 | Final Insights Report | `Screenshots/10_Final_Report.png` |

---

## 👤 Author

**Devan Patel**
*Data Analytics · Microsoft Excel · Business Intelligence*

---

## 📄 License

This project is created for **educational and portfolio purposes.**
Feel free to use it as a reference or learning resource with attribution.

---

## ⭐ Support

If you found this project useful or learned something from it, consider giving it a **star** ⭐ — it helps others discover it too!

---

> *"Data is the new oil — this project is the refinery."*
