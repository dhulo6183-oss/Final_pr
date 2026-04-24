
<div align="center">

# 🎓 Student Management System — SQL Project

> **A complete relational database project built with MySQL, covering real-world academic data management.**

![MySQL](https://img.shields.io/badge/MySQL-8.0-blue?style=for-the-badge&logo=mysql&logoColor=white)
![SQL](https://img.shields.io/badge/Language-SQL-orange?style=for-the-badge&logo=databricks&logoColor=white)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen?style=for-the-badge)
![Tables](https://img.shields.io/badge/Tables-7-purple?style=for-the-badge)
![Records](https://img.shields.io/badge/Records-70+-red?style=for-the-badge)

</div>

---

## 📌 Project Overview

This project demonstrates a fully functional **Student Management System** using MySQL. It models a university's academic data — students, faculty, departments, courses, enrollments, attendance, and grades — using proper relational design with foreign keys, constraints, and advanced SQL queries.

---

## 🗂️ Database Schema

```
d (Database)
├── Departments       → department_id, department_name
├── Students          → student_id, name, dob, gender, email, phone, address, admission_date, department_id
├── Faculty           → faculty_id, name, email, phone, department_id
├── Courses           → course_id, course_name, faculty_id
├── Enrollments       → enrollment_id, student_id, course_id, enrollment_date
├── Attendance        → attendance_id, student_id, course_id, attendance_date, status
└── Grades            → grade_id, student_id, course_id, marks_obtained, grade
```

---

## 📸 Database Screenshots

### 👨‍🎓 Students Table
![Students](s1.jpg)

---

### 🏛️ Departments Table
![Departments](d1.jpeg)

---

### 👨‍🏫 Faculty Table
![Faculty](f1.jpeg)

---

### 📚 Courses Table
![Courses](c1.jpeg)

---

### 📝 Enrollments Table
![Enrollments](e1.jpeg)

---

### 🗓️ Attendance Table
![Attendance](a1.jpeg)

---

### 🏆 Grades Table
![Grades](g1.jpeg)

---

## 🔗 Entity Relationships

```
Departments  ◄──── Students ────► Enrollments ────► Courses ◄──── Faculty
                      │                                  │
                      ▼                                  ▼
                  Attendance                           Grades
```

- **One Department** → Many Students / Faculty
- **One Student** → Many Enrollments, Attendance Records, Grades
- **One Faculty** → Many Courses
- **One Course** → Many Enrollments, Attendance Records, Grades

---

## ⚙️ SQL Concepts Covered

| # | Concept | Example Used |
|---|---------|--------------|
| 1 | 🏗️ DDL (CREATE, ALTER) | Tables with FK constraints |
| 2 | ✏️ CRUD Operations | INSERT, UPDATE, DELETE |
| 3 | 🔍 Clauses | WHERE, HAVING, LIMIT |
| 4 | ➕ Operators | AND, OR, NOT, IN |
| 5 | 📊 ORDER BY & GROUP BY | Sorted & grouped results |
| 6 | 🧮 Aggregate Functions | AVG, MAX, MIN, COUNT |
| 7 | 🔑 Keys | PRIMARY KEY, FOREIGN KEY, UNIQUE |
| 8 | 🔗 JOINs | INNER, LEFT, RIGHT, FULL OUTER |
| 9 | 📦 Subqueries | Nested SELECT statements |
| 10 | 📅 Date Functions | MONTH(), YEAR(), DATE_FORMAT() |
| 11 | 🔤 String Functions | UPPER(), TRIM(), IFNULL() |
| 12 | 🪟 Window Functions | RANK(), COUNT() OVER, PARTITION BY |
| 13 | 🔀 CASE Expressions | Performance & attendance categories |

---

## 🚀 Getting Started

### Prerequisites
- MySQL 8.0+ installed
- MySQL Workbench or any SQL client

### Steps to Run

```bash
# Step 1: Open MySQL CLI or Workbench
mysql -u root -p

# Step 2: Run the SQL file
source /path/to/students.sql;

# Step 3: Verify tables
USE d;
SHOW TABLES;
```

---

## 📊 Sample Query Highlights

### 🏅 Rank Students by Marks
```sql
SELECT student_id, marks_obtained,
  RANK() OVER (ORDER BY marks_obtained DESC) AS rank_no
FROM Grades;
```

### 📉 Attendance Below 75%
```sql
SELECT student_id,
  COUNT(CASE WHEN status='Present' THEN 1 END)*100/COUNT(*) AS attendance_pct
FROM Attendance
GROUP BY student_id
HAVING attendance_pct < 75;
```

### 🎯 Student Performance Category
```sql
SELECT student_id, marks_obtained,
  CASE
    WHEN marks_obtained > 90 THEN '🌟 Excellent'
    WHEN marks_obtained BETWEEN 75 AND 90 THEN '✅ Good'
    ELSE '⚠️ Needs Improvement'
  END AS performance
FROM Grades;
```

---

## 🧑‍🤝‍🧑 Sample Data Summary

| Table | Records |
|-------|---------|
| Departments | 10 |
| Students | 10 |
| Faculty | 10 |
| Courses | 10 |
| Enrollments | 10 |
| Attendance | 10 |
| Grades | 10 |

**Departments included:** Computer Science, Mechanical, Civil, Electrical, IT, AI, Data Science, Chemical, Automobile, Electronics

---

## 🙌 Author

> Built with 💙 using **MySQL** as part of a Database Management Systems (DBMS) learning project.

---

<div align="center">

⭐ **Star this repo if you found it helpful!** ⭐

</div>

