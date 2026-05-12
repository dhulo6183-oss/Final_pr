# 📊 Regional Sales Pipeline Analysis — Bottleneck Identification
**Project:** Unlocking Revenue — Identifying Bottlenecks in Regional Sales  
**Dataset:** `RegionalSales2025.csv` | **Period:** January–December 2025  
**Prepared by:** Business Analyst | Red & White Skill Education

---

## 🖼️ Dashboard Screenshot

![Regional Sales Pipeline Dashboard](p1.png)

> *Interactive Power BI–style dashboard showing KPIs, monthly sales trend, category revenue share, regional bottleneck rates, top agents, and revenue loss breakdown.*

---

## 📁 Project Structure

```
RegionalSales-BottleneckAnalysis/
├── RegionalSales2025.csv          # Source dataset (2,000 rows)
├── SalesBottleneck.sql            # 7 SQL analysis queries with result summaries
├── ExecutiveSummary.txt           # Full written business analysis
├── BottleneckDashboard.html       # Interactive Power BI–style HTML dashboard
├── p1.png                         # Dashboard screenshot
└── README.md                      # This file
```

---

## 🎯 Business Objective

A retail chain with operations across **4 regions** (East, West, North, South) was experiencing inconsistent sales performance. This project surfaces:
- Which regions have the highest cancellation and return rates
- Which products are driving the most revenue loss
- Which sales agents are top performers — and who needs coaching
- Seasonal trends impacting monthly revenue

---

## 📈 Key KPIs at a Glance

| Metric | Value |
|---|---|
| Total Orders | 2,000 |
| Completed Sales | 1,393 (69.65%) |
| Total Revenue (Completed) | ₹5,74,15,519 (~₹5.74 Cr) |
| Gross Sales (All Statuses) | ~₹57.5 Cr |
| Cancellation Rate | ~20.3% avg across regions |
| Return Rate | ~10.65% overall |
| Average Order Value | ₹37,270 |
| Most Returned Product | Laptop |

---

## 🔍 Key Findings

### 1. 🔴 Bottleneck Region — South
- Highest cancellation rate: **24.26%** and return rate: **14.99%**
- Combined, **39.25%** of South's orders generate no revenue
- Agents **Lakshmi Rao** and **Suresh Babu** flagged for performance coaching

### 2. 🟠 Underperforming Region — West
- Second-highest cancellation rate: **23.06%**
- Laptop revenue loss in West alone: **₹14,55,432**

### 3. 💻 Highest Revenue Loss — Electronics
- **Laptop** is the top revenue-loss product across all 4 regions
- East region lost **₹22,70,475** on Laptop cancellations/returns alone
- Smartphones contributed **₹13,02,085** in revenue loss in East

### 4. ✅ Best Performer — North Region
- Lowest cancellation rate: **13.44%** | Lowest return rate: **7.94%**
- Home of the **#1 agent by revenue**: Neha Gupta (₹77.1L)

### 5. 📦 Category Insights
| Category | Revenue | Share | Avg Order Value |
|---|---|---|---|
| Electronics | ₹3.64 Cr | 63.45% | ₹1,20,050 |
| Furniture | ₹1.42 Cr | 24.66% | ₹54,327 |
| Sports | ₹29.8L | 5.20% | ₹11,205 |
| Clothing | ₹29.5L | 5.13% | ₹10,508 |
| Food | ₹8.97L | 1.56% | ₹3,060 |

### 6. 📅 Monthly Trends
- **Peak months:** November (₹58.9L), July (₹58.1L), May (₹57.8L)
- **Weak months:** April (₹32.6L), August (₹37.8L)

### 7. 🏆 Top 5 Sales Agents
| Rank | Agent | Region | Completed Revenue |
|---|---|---|---|
| 1 | Neha Gupta | North | ₹77.1L |
| 2 | Divya Menon | South | ₹62.9L |
| 3 | Ankit Joshi | East | ₹60.5L |
| 4 | Rahul Mehta | East | ₹54.3L |
| 5 | Vijay Kumar | North | ₹52.8L |

---

## 🛠️ SQL Queries Covered (`SalesBottleneck.sql`)

| # | Query | Purpose |
|---|---|---|
| 1 | Monthly Sales Trend | Identify seasonal peaks and dips |
| 2 | Cancel & Return % by Region | Find bottleneck regions |
| 3 | Revenue Loss by Region & Product | Quantify financial damage |
| 4 | Avg Order Value by Category | Compare category profitability |
| 5 | Top 5 Sales Agents | Rank by completed revenue |
| 6 | Category Contribution % | Share of total revenue |
| 7 | High-Return Customers | Flag at-risk customers (≥2 returns) |

---

## 📊 Dashboard

The file `BottleneckDashboard.html` is a **self-contained interactive dashboard** built with Chart.js, featuring:
- 4 KPI summary cards
- Monthly gross sales bar chart (with peak/dip colour coding)
- Category revenue share donut chart
- Regional cancellation & return rate bar chart
- Top 5 agents leaderboard
- Revenue loss table by region & product

> Open directly in any browser — no server or dependencies required.

---

## ✅ Recommended Actions

### Immediate (0–1 Month)
- Flag all South & West cancellations for manager review
- Initiate customer satisfaction calls for returned Electronics
- Set up a weekly dashboard monitoring Cancel% by Region + Agent

### Short-Term (1–3 Months)
- Run training workshops for South agents using North's success model (Neha Gupta as mentor)
- Introduce a **Laptop Assurance Program** (extended warranty, easy exchange)
- Launch April/August-specific promotions for Clothing & Sports

### Long-Term (3–6 Months)
- Revise Sales Agent KPIs to include **Net Completed Revenue** (not just orders booked)
- Expand Sports & Clothing categories — similar revenue, lower risk than Electronics
- Evaluate Food category strategic fit: continue only if bundling can raise AOV to ₹5,000+

---

## 💡 Estimated Revenue Recovery Potential

> Addressing the South bottleneck, Electronics returns, and April/August dip alone could recover an estimated **₹60–75 Lakhs** in annual revenue and improve completion rate from **69.65% → 78–82%**.

---

## 🧰 Tools & Technologies

![SQL](https://img.shields.io/badge/SQL-SQLite%2FMySQL-blue?style=flat-square)
![HTML](https://img.shields.io/badge/Dashboard-HTML%20%2B%20Chart.js-orange?style=flat-square)
![CSV](https://img.shields.io/badge/Data-CSV%202000%20rows-green?style=flat-square)

- **Data:** CSV (2,000 transactions, 11 columns)
- **Analysis:** SQL (SQLite / MySQL compatible)
- **Visualisation:** HTML + Chart.js (no framework dependencies)
- **Reporting:** Plain-text executive summary

---

*© 2025 Business Analyst Report — Red & White Skill Education*
