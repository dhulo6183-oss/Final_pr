# 📊 Excel Analyzer PR.2

> A complete Excel-based Sales Performance Analysis project using Pivot Tables, Conditional Formatting, What-If Analysis, Regression Analysis, Descriptive Statistics, and Interactive Charts.

![Excel](https://img.shields.io/badge/Microsoft_Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)
![Analysis](https://img.shields.io/badge/Type-Data_Analysis-blue?style=for-the-badge)

---

## 🚀 Project Overview

This project analyzes sales data using advanced Microsoft Excel features and data analysis techniques.  
The objective is to transform raw sales data into meaningful business insights through dashboards, visualizations, and statistical analysis.

**Key highlights:**
- 8 distinct analysis modules covering statistics, visualization, and business intelligence
- Interactive Excel dashboard with 4 live KPI metrics
- Automated customer segmentation using dynamic Excel formulas
- Full regression analysis pipeline using the Data Analysis ToolPak

---

## 🛠️ Tools & Technologies Used

| Tool / Feature | Purpose |
|---|---|
| Microsoft Excel | Core platform for all analysis |
| Pivot Tables | Regional and category-level aggregation |
| Conditional Formatting | Visual highlighting of KPIs and trends |
| What-If Analysis | Discount vs. Profit scenario modeling |
| Data Analysis ToolPak | Regression & Descriptive Statistics |
| Charts & Dashboards | Bar, Line, Pie charts + KPI dashboard |

### Excel Formulas Used

```excel
IF()        — Conditional logic for classification
FILTER()    — Dynamic data extraction by criteria
INDEX()     — Lookup values from a range by position
MATCH()     — Return position of a value in a range
NOW()       — Capture current date/time dynamically
```

---

## 📂 Project Structure

```bash
Excel Analyzer Pr 2/
│
├── Data_Analyzer.xlsx          ← Main workbook with all analysis sheets
│
└── Screenshots/
    ├── 1.png                   ← Top 10 Customers (Conditional Formatting)
    ├── 2.png                   ← What-If Analysis (Discount vs Profit)
    ├── 3.png                   ← Linear Regression Analysis
    ├── 4.png                   ← Descriptive Statistics Summary
    ├── 5.png                   ← Monthly Sales Growth with Trend Arrows
    ├── 6.png                   ← High Value Customer Identification
    ├── 7.png                   ← Bar Chart Analysis
    └── 8.png                   ← Pie Chart Analysis
```

---

## 📌 Features Implemented

### ✅ 1. Conditional Formatting
- Highlighted **Top 10 customers** based on total purchase amount using color scales and data bars.
- Applied **up/down arrow icons** in monthly growth analysis to indicate performance direction.

### ✅ 2. What-If Analysis
- Used Excel's **Scenario Manager** and **Data Tables** to simulate the impact of varying discount percentages on total profit.
- Identified the break-even discount threshold.

### ✅ 3. Linear Regression Analysis
- Performed regression analysis using the **Excel Data Analysis ToolPak**.
- Evaluated the relationship between sales variables.
- Extracted R², Slope, Intercept, and P-values for statistical validation.

### ✅ 4. Descriptive Statistics
- Generated a full statistical summary using the **Data Analysis ToolPak**, including:
  - Mean
  - Median
  - Standard Deviation
  - Minimum & Maximum
  - Variance
  - Kurtosis & Skewness

### ✅ 5. Monthly Sales Growth Analysis
- Created a month-over-month sales trend analysis.
- Added **conditional formatting icon sets** (up/down/flat arrows) to instantly signal growth or decline.

### ✅ 6. High Value Customer Identification
- Dynamically filtered and ranked high-value customers using:
  - `FILTER()` — to extract customers above revenue threshold
  - `INDEX()` + `MATCH()` — to retrieve customer details cross-sheet

### ✅ 7. Pivot Table Analysis
- Built pivot tables to summarize total sales by:
  - **Region** (North, South, East, West)
  - **Product Category** (Electronics, Books, etc.)
- Added slicers for interactive filtering.

### ✅ 8. Data Visualization & Dashboard
- Created the following chart types:
  - 📊 **Bar Chart** — Sales by Region / Category
  - 📈 **Line Chart** — Monthly Sales Trend
  - 🥧 **Pie Chart** — Category-wise Revenue Share
- Assembled all KPIs and charts into a single **interactive dashboard**.

---

## 📈 Dashboard KPIs

| KPI | Description |
|---|---|
| 💰 Total Sales | Sum of all revenue across the dataset |
| 📦 Total Quantity Sold | Aggregate units sold across all categories |
| 📊 Total Profit | Net profit after discounts and costs |
| 👥 Total Customers | Unique customer count in the dataset |

---

## 📷 Project Screenshots

### 🔹 1. Top 10 Customers — Conditional Formatting

![Top 10 Customers](Screenshots/1.png)

*Customers ranked by total purchase amount with color-scale highlighting.*

---

### 🔹 2. What-If Analysis — Discount vs. Profit

![What If Analysis](Screenshots/2.png)

*Scenario modeling showing how discount changes affect profit margins.*

---

### 🔹 3. Linear Regression Analysis

![Linear Regression](Screenshots/3.png)

*Regression output including R², coefficients, and significance values.*

---

### 🔹 4. Descriptive Statistics Summary

![Summary Statistics](Screenshots/4.png)

*Full statistical summary including mean, median, std deviation, and more.*

---

### 🔹 5. Monthly Sales Growth with Trend Indicators

![Monthly Growth](Screenshots/5.png)

*Month-over-month growth analysis with icon set arrows for quick trend reading.*

---

### 🔹 6. High Value Customer Identification

![High Value Customers](Screenshots/6.png)

*Dynamic filtering using FILTER(), INDEX(), and MATCH() to surface top customers.*

---

### 🔹 7. Bar Chart — Sales by Region / Category

![Bar Chart](Screenshots/7.png)

*Visual breakdown of sales performance across regions and categories.*

---

### 🔹 8. Pie Chart — Revenue Share by Category

![Pie Chart](Screenshots/8.png)

*Proportional view of revenue contribution by product category.*

---

## 📊 Key Insights

1. **West region** generated the strongest overall sales performance.
2. **Higher discounts negatively impacted profit** — every 5% discount increase reduced profit by approximately X%.
3. **Top 10 customers contributed ~60–70% of total revenue** — a classic Pareto distribution pattern.
4. **Sales showed seasonal variation** — peak months observed mid-year and year-end.
5. **Electronics and Books** were the highest-engagement product categories.

---

## 🎯 Learning Outcomes

Through this project, the following skills were developed:

- ✔️ Data cleaning and formatting in Excel
- ✔️ Statistical analysis using the Data Analysis ToolPak
- ✔️ Business data visualization with charts
- ✔️ Dashboard design combining KPIs and charts
- ✔️ Real-world sales data analysis
- ✔️ Advanced Excel formulas: `FILTER()`, `INDEX()`, `MATCH()`
- ✔️ Regression interpretation and What-If scenario modeling

---

## 📌 How to Use This Project

1. **Open** `Data_Analyzer.xlsx` in Microsoft Excel (2016 or later recommended).
2. **Enable** the Data Analysis ToolPak: `File → Options → Add-ins → Analysis ToolPak`.
3. Navigate between sheets using the sheet tabs at the bottom.
4. Use the **Dashboard** sheet for an overview of all KPIs and charts.
5. Interact with **Pivot Table slicers** to filter data by region or category.

---

## 🔧 Requirements

- Microsoft Excel 2016 / 2019 / 365 (Windows or Mac)
- Data Analysis ToolPak Add-in (free, built into Excel)
- Macros must be enabled for interactive dashboard functionality

---

## 📌 Conclusion

This project demonstrates how **Microsoft Excel** can be used as a powerful data analysis and business intelligence tool — without the need for external software.

By combining charts, pivot tables, regression analysis, statistical summaries, and dashboards, actionable insights were extracted from raw sales data, enabling data-driven business decisions.

---

## 👨‍💻 Author

**Devan Patel**

---

## ⭐ If you found this project useful, give it a star and share it!
