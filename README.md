<div align="center">

```
╔══════════════════════════════════════════════════════════════╗
║                                                              ║
║   ██████╗  █████╗ ████████╗ █████╗                          ║
║   ██╔══██╗██╔══██╗╚══██╔══╝██╔══██╗                         ║
║   ██║  ██║███████║   ██║   ███████║                         ║
║   ██║  ██║██╔══██║   ██║   ██╔══██║                         ║
║   ██████╔╝██║  ██║   ██║   ██║  ██║                         ║
║   ╚═════╝ ╚═╝  ╚═╝   ╚═╝   ╚═╝  ╚═╝                         ║
║                                                              ║
║         S T O R Y   E N G I N E   v1.0                      ║
║     "From Raw Tables → to Human Understanding"              ║
║                                                              ║
╚══════════════════════════════════════════════════════════════╝
```

![SQL](https://img.shields.io/badge/SQL-MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen?style=for-the-badge)
![Steps](https://img.shields.io/badge/Steps-17-orange?style=for-the-badge)
![Author](https://img.shields.io/badge/Author-Dhruv%20Prajapati-blueviolet?style=for-the-badge)

> *SQL isn't about querying databases. It's about asking the right questions.*

</div>

---

## ◈ The Philosophy

Most SQL tutorials teach you **syntax**.

This project teaches you **thinking**.

Every query here solves a real question a business analyst, data engineer, or product manager would actually ask. Each step transforms raw, silent data into something that speaks.

```
Raw Data  →  Query  →  Insight  →  Decision
   🗃️           🔍         💡          ✅
```

---

## ◈ Data Universe

```
┌─────────────────────────────────────────────────────┐
│                   THE DATA MODEL                    │
│                                                     │
│   ┌────────────┐         ┌────────────┐             │
│   │  customers │ ──────► │   orders   │             │
│   │            │  1 : N  │            │             │
│   │ • id       │         │ • id       │             │
│   │ • name     │         │ • cust_id  │             │
│   │ • email    │         │ • amount   │             │
│   └────────────┘         │ • date     │             │
│                          └────────────┘             │
│   ┌────────────┐                                    │
│   │  employees │  (standalone analytics)            │
│   │            │                                    │
│   │ • id       │                                    │
│   │ • name     │                                    │
│   │ • salary   │                                    │
│   │ • dept     │                                    │
│   └────────────┘                                    │
└─────────────────────────────────────────────────────┘
```

---

## ◈ The 17-Step Journey

Each step answers one real question. Together they form a complete story.

### 🔗 ACT I — Connecting the Data

| Step | Question | Technique | Visual |
|------|----------|-----------|--------|
| `01` | *"Who ordered what?"* | `INNER JOIN` | ![Step1](sc1.png) |
| `02` | *"Show all customers — even silent ones"* | `LEFT JOIN` | ![Step2](sc2.png) |
| `03` | *"Every order must appear"* | `RIGHT JOIN` | ![Step3](sc3.png) |
| `04` | *"Miss nothing — show the full universe"* | `FULL OUTER JOIN` | ![Step4](sc4.png) |

---

### 🧠 ACT II — Filtering for Meaning

| Step | Question | Technique | Visual |
|------|----------|-----------|--------|
| `05` | *"Who spends above average?"* | `Subquery + AVG()` | ![Step5](sc5.png) |
| `06` | *"Who earns more than the average salary?"* | `Subquery + AVG()` | ![Step6](sc6.png) |

---

### 🕒 ACT III — Understanding Time

| Step | Question | Technique | Visual |
|------|----------|-----------|--------|
| `07` | *"Break data across time dimensions"* | `YEAR()`, `MONTH()` | ![Step7](sc7.png) |
| `08` | *"How old is each order?"* | `DATEDIFF()` | ![Step8](sc8.png) |
| `09` | *"Make dates readable for humans"* | `DATE_FORMAT()` | ![Step9](sc9.png) |

---

### 🔤 ACT IV — Cleaning the Data

| Step | Question | Technique | Visual |
|------|----------|-----------|--------|
| `10` | *"Build full names from parts"* | `CONCAT()` | ![Step10](sc10.png) |
| `11` | *"Fix inconsistent values in the table"* | `REPLACE()` | ![Step11](sc11.png) |
| `12` | *"Standardize text casing"* | `UPPER()`, `LOWER()` | ![Step12](sc12.png) |
| `13` | *"Remove invisible noise from strings"* | `TRIM()` | ![Step13](sc13.png) |

---

### 📊 ACT V — Advanced Analytics

| Step | Question | Technique | Visual |
|------|----------|-----------|--------|
| `14` | *"How does revenue grow over time?"* | `SUM() OVER()` Window | ![Step14](sc14.png) |
| `15` | *"Who are the top and bottom performers?"* | `RANK() OVER()` | ![Step15](sc15.png) |
| `16` | *"Apply tiered discount rules"* | `CASE WHEN` | ![Step16](sc16.png) |
| `17` | *"Classify employees by salary band"* | `CASE WHEN` | ![Step17](sc17.png) |

---

## ◈ SQL Concepts at a Glance

<details>
<summary><b>🔗 JOIN Types — Connecting Tables</b></summary>

```sql
-- INNER: Only rows that match in both tables
SELECT * FROM customers c
INNER JOIN orders o ON c.id = o.customer_id;

-- LEFT: All customers, even those without orders
SELECT * FROM customers c
LEFT JOIN orders o ON c.id = o.customer_id;

-- RIGHT: All orders, even if customer data is missing
SELECT * FROM customers c
RIGHT JOIN orders o ON c.id = o.customer_id;

-- FULL: Everything from both sides (no row left behind)
SELECT * FROM customers c
LEFT JOIN orders o ON c.id = o.customer_id
UNION
SELECT * FROM customers c
RIGHT JOIN orders o ON c.id = o.customer_id;
```

</details>

<details>
<summary><b>🧠 Subqueries — Dynamic Filtering</b></summary>

```sql
-- "Who spends more than average?"
SELECT customer_name, total_amount
FROM orders
WHERE total_amount > (
    SELECT AVG(total_amount) FROM orders
);

-- "Who earns above average salary?"
SELECT name, salary
FROM employees
WHERE salary > (
    SELECT AVG(salary) FROM employees
);
```

</details>

<details>
<summary><b>🕒 Date Intelligence</b></summary>

```sql
-- Extract time dimensions
SELECT YEAR(order_date), MONTH(order_date), COUNT(*) FROM orders
GROUP BY YEAR(order_date), MONTH(order_date);

-- Days since order
SELECT order_id, DATEDIFF(NOW(), order_date) AS days_old FROM orders;

-- Human-readable format
SELECT DATE_FORMAT(order_date, '%D %M %Y') AS readable_date FROM orders;
```

</details>

<details>
<summary><b>🔤 String Functions — Cleaning Text</b></summary>

```sql
-- Build full names
SELECT CONCAT(first_name, ' ', last_name) AS full_name FROM customers;

-- Fix bad data
SELECT REPLACE(city, 'Mmbai', 'Mumbai') FROM customers;

-- Remove invisible spaces
SELECT TRIM(email) FROM customers;

-- Standardize casing
SELECT UPPER(name), LOWER(email) FROM employees;
```

</details>

<details>
<summary><b>📊 Window Functions — Analytics Without Collapsing Rows</b></summary>

```sql
-- Running total (cumulative revenue)
SELECT order_id, amount,
    SUM(amount) OVER (ORDER BY order_date) AS running_total
FROM orders;

-- Rank orders by amount
SELECT order_id, amount,
    RANK() OVER (ORDER BY amount DESC) AS rank_position
FROM orders;
```

</details>

<details>
<summary><b>🧮 CASE WHEN — Business Logic in SQL</b></summary>

```sql
-- Tiered discounts
SELECT order_id, amount,
    CASE
        WHEN amount > 10000 THEN 'Premium — 20% off'
        WHEN amount > 5000  THEN 'Gold — 10% off'
        ELSE 'Standard — No discount'
    END AS discount_tier
FROM orders;

-- Salary classification
SELECT name, salary,
    CASE
        WHEN salary > 80000 THEN 'Senior'
        WHEN salary > 50000 THEN 'Mid-Level'
        ELSE 'Junior'
    END AS band
FROM employees;
```

</details>

---

## ◈ Skills You Walk Away With

```
After completing this project, you can:

  ✦  Connect multiple tables with the right JOIN for the job
  ✦  Write subqueries that dynamically filter with AVG / MAX / MIN
  ✦  Work with dates — extract, format, calculate distance
  ✦  Clean dirty data with TRIM, REPLACE, UPPER / LOWER
  ✦  Build window functions for running totals and rankings
  ✦  Encode business rules directly into SQL with CASE logic
  ✦  Think in terms of "what question does this query answer?"
```

---

## ◈ How to Run

```bash
# 1. Clone or download the project
git clone https://github.com/dhruv/sql-data-story-engine

# 2. Open your MySQL client (Workbench, DBeaver, CLI)

# 3. Import the SQL file
mysql -u root -p < sql_lab.sql

# 4. Run queries step by step — follow the 17-step journey
```

> Tested on **MySQL 8.0+**. Compatible with MariaDB.

---

## ◈ Project Structure

```
sql-data-story-engine/
│
├── 📄 sql_lab.sql          ← All 17 queries, commented
├── 📸 sc1.png – sc17.png  ← Output screenshots per step
└── 📖 README.md            ← You are here
```

---

## ◈ What Makes This Different

| Typical SQL Tutorial | This Project |
|----------------------|--------------|
| "Here's SELECT syntax" | "Here's a real business question" |
| Isolated examples | Connected 17-step narrative |
| Memorize functions | Understand when and why to use each |
| Just gets it working | Thinks about data quality & cleaning |
| No business context | Discounts, salary bands, rankings |

---

<div align="center">

---

*"Data is just noise until someone asks the right question."*

**Built with curiosity. Driven by logic.**

---

**👨‍💻 Dhruv Prajapati**

![Made with SQL](https://img.shields.io/badge/Made%20with-SQL-4479A1?style=flat-square&logo=mysql&logoColor=white)
![Love](https://img.shields.io/badge/Made%20with-%E2%9D%A4-red?style=flat-square)

</div>
