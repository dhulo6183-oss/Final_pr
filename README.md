<div align="center">

<br/>

```
███████╗███╗   ███╗██████╗ ██╗      ██████╗ ██╗   ██╗███████╗███████╗
██╔════╝████╗ ████║██╔══██╗██║     ██╔═══██╗╚██╗ ██╔╝██╔════╝██╔════╝
█████╗  ██╔████╔██║██████╔╝██║     ██║   ██║ ╚████╔╝ █████╗  █████╗  
██╔══╝  ██║╚██╔╝██║██╔═══╝ ██║     ██║   ██║  ╚██╔╝  ██╔══╝  ██╔══╝  
███████╗██║ ╚═╝ ██║██║     ███████╗╚██████╔╝   ██║   ███████╗███████╗
╚══════╝╚═╝     ╚═╝╚═╝     ╚══════╝ ╚═════╝    ╚═╝   ╚══════╝╚══════╝
              PERFORMANCE  ANALYSIS  DASHBOARD
```

<br/>

# 📊 Employee Performance Analysis Dashboard

**An enterprise-grade HR analytics project built entirely in Microsoft Excel**  
*Analyzing 5,000 employee records across performance, KPI scores, attendance, and promotion eligibility*

<br/>

![Excel](https://img.shields.io/badge/Platform-Microsoft%20Excel-217346?style=for-the-badge&logo=microsoftexcel&logoColor=white)
![Records](https://img.shields.io/badge/Dataset-5%2C000%20Records-0078D4?style=for-the-badge&logo=databricks&logoColor=white)
![Columns](https://img.shields.io/badge/Features-13%20Columns-FF6B35?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Complete-2ECC71?style=for-the-badge)
![Author](https://img.shields.io/badge/Author-Devan%20Patel-9B59B6?style=for-the-badge)

<br/>

</div>

---

## 📋 Table of Contents

- [Project Overview](#-project-overview)
- [Live Dashboard Metrics](#-live-dashboard-metrics)
- [Project Structure](#-project-structure)
- [Dataset Schema](#-dataset-schema)
- [Workflow & Methodology](#-workflow--methodology)
  - [Step 1 — Data Import](#step-1--data-import)
  - [Step 2 — Data Cleaning](#step-2--data-cleaning)
  - [Step 3 — Pivot Table Analysis](#step-3--pivot-table-analysis)
  - [Step 4 — Advanced Formulas](#step-4--advanced-formulas)
  - [Step 5 — Conditional Formatting](#step-5--conditional-formatting)
- [Interactive Dashboard](#-interactive-dashboard)
- [Key Insights & Findings](#-key-insights--findings)
- [Tools & Techniques](#️-tools--techniques)
- [Department Bonus Structure](#-department-bonus-structure)
- [Screenshots Gallery](#-screenshots-gallery)
- [Author](#-author)

---

## 🎯 Project Overview

This project delivers a **comprehensive HR analytics solution** built entirely within Microsoft Excel — from raw data ingestion to a fully interactive, slicer-driven dashboard. The dataset captures 5,000 employees across five departments, evaluated on 13 performance dimensions to derive actionable insights into workforce productivity, KPI achievement, attendance reliability, and promotion readiness.

> **Goal:** Transform raw HR data into a decision-ready analytics layer that empowers managers and HR leaders to identify top performers, detect attendance risks, allocate bonuses fairly, and build transparent promotion pipelines.

<br/>

| 🏷️ Attribute | 📝 Details |
|:---|:---|
| **Project Title** | Employee Performance Analysis Dashboard |
| **Dataset** | Employee Performance Dataset |
| **Total Records** | 5,000 employees |
| **Total Features** | 13 columns |
| **Departments Covered** | Finance · HR · IT · Marketing · Sales |
| **Platform** | Microsoft Excel (Pivot Tables, Formulas, Dashboard) |
| **Objective** | Multi-dimensional performance, KPI, attendance & promotion analysis |

---

## 📈 Live Dashboard Metrics

<div align="center">

| 👥 Total Employees | 📊 Avg Performance | 🎯 Avg KPI Score | 🗓️ Avg Attendance | ✅ Promotion Eligible |
|:---:|:---:|:---:|:---:|:---:|
| **5,000** | **74.78 / 100** | **77.38 / 100** | **87.47%** | **695 (13.9%)** |

</div>

---

## 📁 Project Structure

```
📦 EmployeesPerformance/
│
├── 📄 Employee_Performance_Dataset.csv        ← Raw source data (CSV format)
├── 📊 Employee_Performance_Dataset.xlsx       ← Full Excel workbook with dashboard
│
└── 📸 Screenshots/
    ├── 1.Imported_Dataset.png                 ← Step 1: Raw import with table formatting
    ├── 2.Checked_Duplicates.png               ← Step 2: Duplicate detection results
    ├── 3.1.Average_Performance.png            ← Pivot: Avg performance by department
    ├── 3.2.Promotion_Analysis.png             ← Pivot: Promotion eligibility counts
    ├── 3.3.KPI_Analysis.png                   ← Pivot: Avg KPI by job role
    ├── 3.4.Attendance_Analysis.png            ← Pivot: Avg attendance by department
    ├── 4.1.Advanced_Formulas.png              ← VLOOKUP + INDEX-MATCH formulas
    ├── 4.2.Advanced_Formula.png               ← IF + Nested IF classifications
    ├── 5.Conditional_Formatting.png           ← Data bars + icon sets applied
    ├── Dashboard.png                          ← Final interactive dashboard view
    └── Documentation.png                      ← Project summary sheet
```

---

## 🗂️ Dataset Schema

The dataset comprises **13 columns** capturing quantitative and qualitative employee performance dimensions:

| # | 📌 Column | 🔍 Description | 📐 Range / Type |
|:---:|:---|:---|:---|
| 1 | **Employee ID** | Unique identifier for each employee | Alphanumeric |
| 2 | **Name** | Full name of the employee | Text |
| 3 | **Department** | Business unit the employee belongs to | Finance / HR / IT / Marketing / Sales |
| 4 | **Job Role** | Specific role within the department | Text (categorical) |
| 5 | **Performance Score** | Composite numeric performance score | 0 – 100 |
| 6 | **KPI Score** | Key Performance Indicator achievement score | Numeric |
| 7 | **Attendance (%)** | Percentage of working days attended | 0% – 100% |
| 8 | **Peer Rating** | Peer-reviewed performance rating | 1.0 – 5.0 |
| 9 | **Task Completion (%)** | Percentage of assigned tasks completed | 0% – 100% |
| 10 | **Work Hours Logged** | Total hours logged during the period | Numeric (hours) |
| 11 | **Manager Feedback** | Quantitative rating from direct manager | Numeric scale |
| 12 | **Training Hours** | Hours invested in training and upskilling | Numeric (hours) |
| 13 | **Promotion Eligibility** | Final promotion readiness classification | Yes / No |

---

## 🔄 Workflow & Methodology

### Step 1 — Data Import

> **Objective:** Establish a clean, structured working environment before any analysis begins.

- Imported the raw **Employee Performance Dataset** into Excel with all **13 columns × 5,000 rows**
- Applied **Excel Table formatting** (`Ctrl + T`) to enable structured references and auto-filters
- Configured **column data types** appropriately (numbers, percentages, text) to prevent formula errors
- Enabled **AutoFilter** headers for rapid field-level filtering during exploration

📸 *Screenshot:* `Screenshots/1.Imported_Dataset.PNG

---

### Step 2 — Data Cleaning

> **Objective:** Validate data integrity before building any analytical layer.

| ✅ Check | 🔍 Method | 📋 Result |
|:---|:---|:---|
| **Duplicate Detection** | Excel → Data → Remove Duplicates (all columns) | ✅ **0 duplicates found** |
| **Missing Values** | COUNTBLANK() across all columns | ✅ **No missing values** |
| **Data Type Validation** | Column-by-column type check | ✅ **All types correctly formatted** |

> **Outcome:** The dataset is confirmed **clean, complete, and analysis-ready** — no imputation or removal required.

📸 *Screenshot:* `Screenshots/2.Checked_Duplicates.png`

---

### Step 3 — Pivot Table Analysis

Four dedicated pivot tables were built to extract department-level and role-level insights:

---

#### 3.1 · Average Performance Score by Department

> Calculated the mean performance score per department using a pivot table, visualized with a **clustered column chart**.

| 🏢 Department | 📊 Avg Performance Score |
|:---|:---:|
| 🥇 HR | **76** |
| 🥈 Finance | **75** |
| 🥉 IT | **75** |
| Sales | **74** |
| Marketing | **74** |

**Insight:** HR leads with an average of **76**, but the narrow 2-point range (74–76) across all departments signals a **remarkably consistent and evenly distributed workforce**.

📸 *Screenshot:* `Screenshots/3.1.Average_Performance.png`

---

#### 3.2 · Promotion Eligible Employees by Department

> Counted promotion-eligible employees per department to identify where talent advancement is concentrated.

| 🏢 Department | ✅ Eligible Employees |
|:---|:---:|
| 🥇 HR | **154** |
| Finance | **145** |
| Sales | **141** |
| Marketing | **136** |
| 🔻 IT | **129** |
| **TOTAL** | **695 / 5,000 (13.9%)** |

**Insight:** Only **13.9%** of the workforce meets promotion criteria. HR leads with the most eligible employees, while IT — despite the best attendance — has the fewest promotion-eligible staff.

📸 *Screenshot:* `Screenshots/3.2.Promotion_Analysis.png`

---

#### 3.3 · Average KPI Score by Job Role

> Ranked all job roles by average KPI score to identify top-performing and lower-performing role types.

| 🏅 Rank | 💼 Job Role | 🎯 Avg KPI Score |
|:---:|:---|:---:|
| 🥇 1 | Recruitment Specialist | **78.11** |
| 2 | Financial Analyst | **77.80** |
| 3 | Software Engineer | **77.60** |
| 4 | Sales Executive | **77.40** |
| 🔻 Last | Marketing Executive | **76.50** |
| — | **Overall Average** | **77.38** |

**Insight:** **Recruitment Specialists** lead KPI achievement at **78.11**, exceeding the overall average by **0.73 points**. The narrow spread (76.50–78.11) confirms consistent cross-role performance.

📸 *Screenshot:* `Screenshots/3.3.KPI_Analysis.png`

---

#### 3.4 · Average Attendance by Department

> Analyzed attendance patterns across departments, visualized with a **line chart** for trend clarity.

| 🏢 Department | 🗓️ Avg Attendance |
|:---|:---:|
| 🥇 IT | **87.66%** |
| Finance | **87.55%** |
| HR | **87.49%** |
| Sales | **87.40%** |
| 🔻 Marketing | **87.26%** |
| **Overall Average** | **87.47%** |

**Insight:** **IT** maintains the highest attendance rate at **87.66%**. The cross-department variance is minimal (< 0.40%), indicating **uniformly strong attendance culture** organization-wide.

📸 *Screenshot:* `Screenshots/3.4.Attendance_Analysis.png`

---

### Step 4 — Advanced Formulas

#### 4.1 · VLOOKUP & INDEX-MATCH

> **Purpose:** Enrich the dataset with department-specific bonus data and enable employee cross-referencing by ID.

**Formula Applied:**

```excel
-- VLOOKUP: Assign bonus based on Department
=VLOOKUP(C2, BonusTable, 2, FALSE)

-- INDEX-MATCH: Retrieve employee name by ID
=INDEX(NameColumn, MATCH(LookupID, IDColumn, 0))
```

**Bonus Lookup Table:**

| 🏢 Department | 💰 Bonus Amount |
|:---|:---:|
| 🥇 IT | **₹6,000** |
| Finance | **₹5,500** |
| Sales | **₹5,000** |
| Marketing | **₹4,500** |
| HR | **₹4,000** |

📸 *Screenshot:* `Screenshots/4.1.Advanced_Formulas.png`

---

#### 4.2 · IF & Nested IF — Workload & Performance Ratings

> **Purpose:** Derive two new classification columns to enrich employee profiling.

**Formula Applied:**

```excel
-- Workload Category: based on Work Hours Logged
=IF(WorkHours > Threshold, "High Workload", "Normal")

-- Performance Rating: nested classification on Performance Score
=IF(Score >= 90, "Excellent",
   IF(Score >= 75, "Good",
      IF(Score >= 60, "Average", "Poor")))
```

**Classification Output:**

| ⚡ Category | 📋 Criteria |
|:---|:---|
| **Excellent** | Performance Score ≥ 90 |
| **Good** | Performance Score 75 – 89 |
| **Average** | Performance Score 60 – 74 |
| **Poor** | Performance Score < 60 |
| **High Workload** | Work Hours > defined threshold |
| **Normal** | Work Hours ≤ defined threshold |

📸 *Screenshot:* `Screenshots/4.2.Advanced_Formula.png`

---

### Step 5 — Conditional Formatting

> **Purpose:** Add an instant visual intelligence layer to the raw data table for rapid scanning.

| 🎨 Format Applied | 📌 Column | 💡 Purpose |
|:---|:---|:---|
| **Gradient Data Bars** | Attendance (%) | Instantly spot low vs. high attendance employees |
| **Green Arrow ↑** | Peer Rating ≥ 4.0 | Highlights top peer-reviewed employees |
| **Orange Arrow →** | Peer Rating 3.0 – 3.9 | Flags average peer-rated employees |
| **Red Arrow ↓** | Peer Rating < 3.0 | Identifies employees needing attention |

📸 *Screenshot:* `Screenshots/5.Conditional_Formatting.png`

---

## 📊 Interactive Dashboard

> A **single-page, fully interactive Excel dashboard** consolidating all key metrics, charts, and filters — designed for non-technical HR stakeholders and executive leadership.

📸 *Screenshot:* `Screenshots/Dashboard.png`

### Dashboard Architecture

```
┌─────────────────────────────────────────────────────────────┐
│              EMPLOYEE PERFORMANCE DASHBOARD                  │
├──────────────┬──────────────┬─────────────┬─────────────────┤
│ Total        │ Avg          │ Avg KPI     │ Avg Attendance  │
│ Employees    │ Performance  │ Score       │                 │
│   5,000      │   74.78      │   77.38     │   87.47%        │
├──────────────┴──────────────┴─────────────┴─────────────────┤
│  Promotion   │  Performance by  │  KPI Score by            │
│  Eligible    │  Department      │  Job Role                │
│    695       │  [Column Chart]  │  [Bar Chart]             │
├──────────────┤                  ├──────────────────────────┤
│  Attendance  │                  │  Promotion Eligible      │
│  by Dept     │                  │  by Department           │
│  [Line Chart]│                  │  [Column Chart]          │
├──────────────┴──────────────────┴──────────────────────────┤
│  SLICERS:  [Job Role ▼]  [Department ▼]  [Promotion ▼]     │
└─────────────────────────────────────────────────────────────┘
```

### Dashboard Components

| 🧩 Component | 📋 Details |
|:---|:---|
| **KPI Cards (5)** | Total Employees · Avg Performance · Avg KPI · Avg Attendance · Promotion Count |
| **Column Chart** | Avg Performance Score by Department |
| **Bar Chart** | Avg KPI Score by Job Role |
| **Line Chart** | Avg Attendance by Department |
| **Column Chart** | Promotion Eligible Count by Department |
| **Slicer — Department** | Filter all visuals by Finance / HR / IT / Marketing / Sales |
| **Slicer — Job Role** | Filter by specific job function |
| **Slicer — Promotion** | Isolate eligible vs. non-eligible employees |

### How to Use the Dashboard

1. **Open** `Employee_Performance_Dataset.xlsx` in Microsoft Excel
2. **Navigate** to the `Dashboard` sheet tab
3. **Click** any slicer button to instantly filter all connected charts and KPI cards
4. **Combine** multiple slicers (e.g., *IT department + Promotion Eligible*) for granular views
5. **Reset** all filters by clicking the clear filter icon (✕) on each slicer

---

## 💡 Key Insights & Findings

<div align="center">

```
╔══════════════════════════════════════════════════════════════╗
║                   EXECUTIVE SUMMARY                         ║
╠══════════════════════════════════════════════════════════════╣
║  🏆  HR leads all departments in Avg Performance (76/100)   ║
║  📌  13.9% of the workforce is promotion-ready (695/5,000)  ║
║  🎯  Recruitment Specialists top KPI rankings (78.11)       ║
║  📅  IT has the best attendance of all departments (87.66%) ║
║  💰  IT receives the highest department bonus (₹6,000)      ║
║  📉  Performance scores are tightly clustered (74–76)       ║
╚══════════════════════════════════════════════════════════════╝
```

</div>

| # | 💡 Insight | 📌 Finding | 🔍 Implication |
|:---:|:---|:---|:---|
| 1 | **HR Leads Performance** | Avg score of **76** — highest across all departments | HR's internal standards and L&D investment may be driving above-average results |
| 2 | **Narrow Promotion Pipeline** | Only **695 / 5,000 (13.9%)** are eligible | Indicates high promotion bar; potential to review criteria or grow pipeline through targeted coaching |
| 3 | **Recruitment Specialists Dominate KPI** | Top KPI at **78.11** vs. overall avg of **77.38** | High accountability in recruitment roles translates directly to measurable output |
| 4 | **IT Tops Attendance & Bonus** | **87.66%** attendance + **₹6,000** bonus — both highest | IT remains a high-engagement, high-reward department; may inform retention strategies elsewhere |
| 5 | **Consistent Workforce** | All dept. performance scores in **74–76 range** | Minimal outliers; organization has a stable performance baseline — both an asset and a risk for top-talent differentiation |
| 6 | **Marketing Lags in Attendance** | Lowest attendance at **87.26%** | Marginal gap but consistent — warrants monitoring for scheduling, workload, or culture concerns |

---

## 🛠️ Tools & Techniques

| 🔧 Category | 📋 Details |
|:---|:---|
| **Platform** | Microsoft Excel (Desktop) |
| **Data Cleaning** | Duplicate detection · Missing value check · Data type validation · Table formatting |
| **Pivot Tables** | Avg Performance by Department · Promotion by Department · KPI by Role · Attendance by Department |
| **Formulas Used** | `VLOOKUP` · `INDEX-MATCH` · `IF` · Nested `IF` · `COUNTBLANK` |
| **Chart Types** | Clustered Column Chart · Horizontal Bar Chart · Line Chart |
| **Conditional Formatting** | Gradient Data Bars (Attendance) · Icon Sets with colored directional arrows (Peer Rating) |
| **Interactive Features** | PivotChart Slicers — Department · Job Role · Promotion Eligibility |
| **Documentation** | Dedicated project summary sheet for handoff and reference |

---

## 💰 Department Bonus Structure

Bonuses were assigned via `VLOOKUP` referencing the following lookup table:

| 🏢 Department | 💰 Bonus | 📊 Justification |
|:---|:---:|:---|
| 🥇 IT | **₹6,000** | Highest performance + best attendance |
| Finance | **₹5,500** | Strong KPI and reliable attendance |
| Sales | **₹5,000** | Revenue-generating role premium |
| Marketing | **₹4,500** | Brand and pipeline contribution |
| HR | **₹4,000** | Internal operations support role |

---

## 📸 Screenshots Gallery

| # | 🖼️ Screenshot | 📋 Description |
|:---:|:---|:---|
| 1 | `1.Imported_Dataset.png` | Raw dataset loaded with table formatting and auto-filters applied |
| 2 | `2.Checked_Duplicates.png` | Duplicate detection results — **zero duplicates confirmed** |
| 3.1 | `3.1.Average_Performance.png` | Pivot table + clustered column chart of avg performance by department |
| 3.2 | `3.2.Promotion_Analysis.png` | Promotion eligible employee count by department |
| 3.3 | `3.3.KPI_Analysis.png` | Avg KPI score ranked by job role |
| 3.4 | `3.4.Attendance_Analysis.png` | Avg attendance line chart across all departments |
| 4.1 | `4.1.Advanced_Formulas.png` | VLOOKUP for bonus assignment + INDEX-MATCH for employee lookup |
| 4.2 | `4.2.Advanced_Formula.png` | IF/Nested IF for workload classification and performance ratings |
| 5 | `5.Conditional_Formatting.png` | Data bars on attendance + arrow icon sets on peer ratings |
| — | `Dashboard.png` | **Final interactive dashboard — full consolidated view** |
| — | `Documentation.png` | Project documentation summary sheet |

---

## 👤 Author

<div align="center">

<br/>

**Devan Patel**

*HR Analytics · Data Analysis · Microsoft Excel*

<br/>

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](#)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-181717?style=for-the-badge&logo=github&logoColor=white)](#)
[![Portfolio](https://img.shields.io/badge/Portfolio-Visit-FF6B35?style=for-the-badge&logo=googlechrome&logoColor=white)](#)

<br/>

---

<sub>⭐ If this project added value to your work, consider giving the repository a star!</sub>

<br/>

</div>
