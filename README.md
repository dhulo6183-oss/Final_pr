Regional Sales Pipeline Dashboard – README

Project Overview

This project presents a complete Regional Sales Pipeline Analysis Dashboard for the year 2025.

The dashboard identifies:

Revenue bottlenecks
Cancellation patterns
Product performance
Regional performance
Revenue loss
Top sales agents

The project is designed using:

HTML
CSS
JavaScript
Chart.js
SQL
Dashboard Preview

Project Objective

The main objective of this project is to analyze business sales performance across different regions and identify areas causing revenue loss.

The dashboard helps management:

Improve sales performance
Reduce cancellations
Reduce returns
Increase completed revenue
Improve customer satisfaction
KPI Highlights
KPI	Value
Total Revenue	₹5.74 Cr
Gross Sales	₹57.5 Cr
Cancellation Rate	20.3%
Top Revenue Loss	₹22.7L
Top Category	Electronics
Worst Region	South
Dashboard Features
1. Monthly Gross Sales Trend

Shows monthly revenue trends for 2025.

Peak Months
May
July
November
Weak Months
April
August
2. Category Revenue Share
Category	Contribution
Electronics	63.45%
Furniture	24.66%
Sports	5.20%
Clothing	5.13%
Food	1.56%
3. Regional Cancellation & Return Analysis

The dashboard compares:

Cancellation %
Return %
Regional risk
Worst Performing Region

South region has:

Highest cancellation rate
Highest return rate
4. Top Sales Agents
Rank	Agent	Region	Revenue
1	Neha Gupta	North	₹77.1L
2	Divya Menon	South	₹62.9L
3	Ankit Joshi	East	₹60.5L
4	Rahul Mehta	East	₹54.3L
5	Vijay Kumar	North	₹52.8L
5. Revenue Loss Analysis

Top revenue loss products:

Laptop
Smartphone

Major issue:

Electronics returns
Technologies Used
Technology	Purpose
HTML5	Structure
CSS3	Styling
JavaScript	Functionality
Chart.js	Charts
SQL	Data Analysis
CSV	Dataset
Dataset Information
Dataset Name

RegionalSales2025.csv

Dataset Includes
2000 records
4 regions
5 categories
11 sales agents
12 months data
SQL Queries Used
Query 1 – Monthly Sales Trend
SELECT
    SUBSTR(Date, 1, 7) AS Month,
    COUNT(*) AS TotalOrders,
    SUM(
        CASE WHEN OrderStatus = 'Completed'
        THEN TotalAmount ELSE 0 END
    ) AS CompletedRevenue,
    SUM(TotalAmount) AS GrossSales
FROM RegionalSales2025
GROUP BY SUBSTR(Date, 1, 7)
ORDER BY Month;
Purpose

Analyzes monthly sales trends and identifies peak and weak months.

Query 2 – Cancellation & Return Percentage by Region
SELECT
    Region,
    COUNT(*) AS TotalOrders,
    SUM(CASE WHEN OrderStatus = 'Cancelled' THEN 1 ELSE 0 END) AS Cancellations,
    SUM(CASE WHEN OrderStatus = 'Returned' THEN 1 ELSE 0 END) AS Returns,
    ROUND(
        100.0 * SUM(CASE WHEN OrderStatus = 'Cancelled' THEN 1 ELSE 0 END)
        / COUNT(*), 2
    ) AS CancelPct,
    ROUND(
        100.0 * SUM(CASE WHEN OrderStatus = 'Returned' THEN 1 ELSE 0 END)
        / COUNT(*), 2
    ) AS ReturnPct
FROM RegionalSales2025
GROUP BY Region
ORDER BY CancelPct DESC;
Purpose

Finds the worst-performing region based on cancellations and returns.

Query 3 – Revenue Loss by Product & Region
SELECT
    Region,
    ProductName,
    COUNT(*) AS LostOrders,
    SUM(TotalAmount) AS RevenueLost
FROM RegionalSales2025
WHERE OrderStatus IN ('Cancelled', 'Returned')
GROUP BY Region, ProductName
ORDER BY RevenueLost DESC
LIMIT 10;
Purpose

Identifies products causing the highest revenue loss.

Query 4 – Average Order Value by Category
SELECT
    Category,
    COUNT(*) AS TotalOrders,
    ROUND(AVG(TotalAmount), 2) AS AvgOrderValue,
    SUM(TotalAmount) AS TotalSales
FROM RegionalSales2025
GROUP BY Category
ORDER BY AvgOrderValue DESC;
Purpose

Compares product categories based on average order value.

Query 5 – Top 5 Sales Agents
SELECT
    SalesAgent,
    Region,
    COUNT(CASE WHEN OrderStatus = 'Completed' THEN 1 END) AS CompletedOrders,
    SUM(
        CASE WHEN OrderStatus = 'Completed'
        THEN TotalAmount ELSE 0 END
    ) AS CompletedRevenue,
    ROUND(
        100.0 * COUNT(CASE WHEN OrderStatus = 'Completed' THEN 1 END)
        / COUNT(*), 1
    ) AS SuccessRate
FROM RegionalSales2025
GROUP BY SalesAgent, Region
ORDER BY CompletedRevenue DESC
LIMIT 5;
Purpose

Finds top-performing sales agents.

Query 6 – Category Contribution to Total Revenue
SELECT
    Category,
    SUM(
        CASE WHEN OrderStatus = 'Completed'
        THEN TotalAmount ELSE 0 END
    ) AS CategoryRevenue,
    ROUND(
        100.0 *
        SUM(CASE WHEN OrderStatus = 'Completed' THEN TotalAmount ELSE 0 END)
        / (
            SELECT SUM(TotalAmount)
            FROM RegionalSales2025
            WHERE OrderStatus = 'Completed'
        ),
        2
    ) AS ContributionPct
FROM RegionalSales2025
GROUP BY Category
ORDER BY CategoryRevenue DESC;
Purpose

Shows category-wise revenue contribution.

Query 7 – Customers with High Return Frequency
SELECT
    CustomerID,
    COUNT(*) AS ReturnCount,
    SUM(TotalAmount) AS TotalReturnedValue,
    GROUP_CONCAT(DISTINCT ProductName) AS ReturnedProducts
FROM RegionalSales2025
WHERE OrderStatus = 'Returned'
GROUP BY CustomerID
HAVING COUNT(*) >= 2
ORDER BY ReturnCount DESC;
Purpose

Identifies customers with frequent product returns.

KPI Summary Query
SELECT
    COUNT(CASE WHEN OrderStatus = 'Completed' THEN 1 END) AS TotalCompletedSales,
    SUM(CASE WHEN OrderStatus = 'Completed'
             THEN TotalAmount ELSE 0 END) AS TotalRevenue,
    COUNT(CASE WHEN OrderStatus = 'Cancelled' THEN 1 END) AS TotalCancellations,
    COUNT(CASE WHEN OrderStatus = 'Returned' THEN 1 END) AS TotalReturns,
    ROUND(AVG(TotalAmount), 2) AS AvgOrderValue
FROM RegionalSales2025;
Key Business Insights
South Region Issues
Highest cancellation rate
Highest return rate
Biggest bottleneck
Electronics Category
Highest revenue contributor
Highest revenue loss
Seasonal Trend

Weak months:

April
August

Peak months:

May
July
November
Future Improvements
Add Power BI integration
Add live database support
Add filters and drill-down analysis
Add predictive analytics
Project Files
File Name	Description
RegionalSales2025.csv	Dataset
SalesBottleneck.sql	SQL queries
ExecutiveSummary.txt	Summary report
regional_sales_dashboard_clean.html	Dashboard
p1.png	Dashboard image
How to Run
Step 1

Download all project files.

Step 2

Open:

regional_sales_dashboard_clean.html
Step 3

Dashboard opens in browser.

Learning Outcomes

This project demonstrates:

Data analytics
Dashboard development
SQL analysis
Business intelligence
KPI tracking
Data visualization
Author

Business Analyst Project
Prepared for educational and analytical purposes.
