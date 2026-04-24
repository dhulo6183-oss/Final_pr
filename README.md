<div align="center">

# 🎓 Student Management System
### — MySQL Database Project —

<br>

![MySQL](https://img.shields.io/badge/MySQL-8.0+-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-DDL%20%7C%20DML%20%7C%20DQL-F97316?style=for-the-badge&logo=databricks&logoColor=white)
![Status](https://img.shields.io/badge/Status-Complete%20✓-22C55E?style=for-the-badge)
![Tables](https://img.shields.io/badge/Tables-7-6366F1?style=for-the-badge)
![License](https://img.shields.io/badge/License-Academic-EC4899?style=for-the-badge)

<br>

> 💡 **A fully normalized relational database** designed to manage Students, Faculty, Courses,  
> Enrollments, Attendance & Grades — covering every core SQL concept from DDL to Window Functions.

</div>

---

## 📌 Table of Contents

| # | Section |
|---|---------|
| 1 | [Project Overview](#-project-overview) |
| 2 | [Project Structure](#-project-structure) |
| 3 | [ER Diagram](#-er-diagram) |
| 4 | [Table: Departments](#1--departments) |
| 5 | [Table: Students](#2--students) |
| 6 | [Table: Faculty](#3--faculty) |
| 7 | [Table: Courses](#4--courses) |
| 8 | [Table: Enrollments](#5--enrollments) |
| 9 | [Table: Attendance](#6--attendance) |
| 10 | [Table: Grades](#7--grades) |
| 11 | [SQL Concepts Covered](#-sql-concepts-covered) |
| 12 | [Key Queries](#-key-queries-snapshot) |
| 13 | [Constraints Summary](#-constraints--keys-summary) |
| 14 | [How to Run](#-how-to-run) |

---

## 🚀 Project Overview

This project implements a **complete Student Management System** using **MySQL**. It models a real-world academic institution with 7 interlinked tables:

- 🏢 **10 Departments** — Computer Science, Mechanical, Civil, Electrical, IT, AI, Data Science, Chemical, Automobile, Electronics
- 🎓 **10 Students** — Full personal & academic records
- 👩‍🏫 **10 Faculty Members** — Assigned to departments and courses
- 📚 **10 Courses** — Each taught by a dedicated faculty member
- 📋 **Enrollments** — With composite UNIQUE key to prevent duplicates
- 📅 **Attendance** — Daily tracking with Present / Absent / Late
- 🏆 **Grades** — Marks + Letter Grade per student per course

---

## 📁 Project Structure

```
StudentManagementSystem/
│
├── 📄 students.SQL          ← Full schema + seed data + all SQL queries
├── 📘 README.md             ← Project documentation (this file)
│
└── 📂 ss/                   ← Screenshots of all MySQL table outputs
    ├── 🖼️ DEPARTMENTS.png
    ├── 🖼️ STUDENTS.png
    ├── 🖼️ Faculty.png
    ├── 🖼️ Courses.png
    ├── 🖼️ Enrollments.png
    ├── 🖼️ Attendance.png
    └── 🖼️ Grades.png
```

---

## 🗄️ ER Diagram

```
┌──────────────────┐          ┌─────────────────────────────────────────────┐
│   DEPARTMENTS    │◄─────────│                  STUDENTS                    │
│──────────────────│          │─────────────────────────────────────────────│
│ department_id PK │          │ student_id PK                                │
│ department_name  │          │ name, dob, gender, email                     │
└────────▲─────────┘          │ phone_number, address, admission_date        │
         │                    │ department_id FK                             │
         │                    └──────────────┬──────────────────────────────┘
         │                                   │
  ┌──────┴────────┐              ┌───────────▼────────────┐
  │    FACULTY    │              │      ENROLLMENTS        │
  │───────────────│              │────────────────────────│
  │ faculty_id PK │              │ enrollment_id PK        │
  │ name, email   │              │ student_id FK           │
  │ phone_number  │              │ course_id FK            │
  │ dept_id FK    │              │ enrollment_date         │
  └──────┬────────┘              │ UNIQUE(student,course)  │
         │                       └────────────────────────┘
  ┌──────▼────────┐
  │    COURSES    │──────────────┬──────────────────────────┐
  │───────────────│              │                          │
  │ course_id PK  │    ┌─────────▼──────────┐   ┌──────────▼──────────┐
  │ course_name   │    │    ATTENDANCE       │   │       GRADES         │
  │ faculty_id FK │    │────────────────────│   │─────────────────────│
  └───────────────┘    │ attendance_id PK    │   │ grade_id PK          │
                       │ student_id FK       │   │ student_id FK        │
                       │ course_id FK        │   │ course_id FK         │
                       │ attendance_date     │   │ marks_obtained       │
                       │ status              │   │ grade                │
                       └─────────────────────┘   └──────────────────────┘
```

---

## 📊 Tables — Schema · Data · Screenshots

---

### 1. 🏢 Departments

> Stores all academic departments in the institution.

**Schema:**

| Column | Type | Constraint | Description |
|--------|------|-----------|-------------|
| `department_id` | INT | `PRIMARY KEY` | Unique department identifier |
| `department_name` | VARCHAR(50) | NOT NULL | Name of the department |

**Data:**

| department_id | department_name |
|:---:|:---|
| 1 | Computer Science |
| 2 | Mechanical |
| 3 | Civil |
| 4 | Electrical |
| 5 | IT |
| 6 | AI |
| 7 | Data Science |
| 8 | Chemical |
| 9 | Automobile |
| 10 | Electronics |

**📸 Screenshot:**

![Departments](ss/DEPARTMENTS.png)

---

### 2. 🎓 Students

> Stores complete personal and academic information for every student.

**Schema:**

| Column | Type | Constraint | Description |
|--------|------|-----------|-------------|
| `student_id` | INT | `PRIMARY KEY` | Unique student identifier |
| `name` | VARCHAR(50) | — | Full name |
| `dob` | DATE | — | Date of birth |
| `gender` | VARCHAR(10) | — | Male / Female |
| `email` | VARCHAR(100) | — | Email address |
| `phone_number` | VARCHAR(15) | — | Contact number |
| `address` | VARCHAR(100) | — | Residential address |
| `admission_date` | DATE | — | Date of admission |
| `department_id` | INT | `FK → Departments` | Enrolled department |

**Data:**

| student_id | name | dob | gender | email | phone | address | admission_date | dept_id |
|:---:|:---|:---:|:---:|:---|:---:|:---:|:---:|:---:|
| 1 | Amit | 2002-01-01 | Male | amit@gmail.com | 9876543210 | Surat | 2022-06-01 | 1 |
| 2 | Riya | 2002-02-02 | Female | riya@gmail.com | 9876543211 | Delhi | 2022-06-01 | 1 |
| 3 | Rahul | 2002-03-03 | Male | rahul@gmail.com | 9876543212 | Mumbai | 2022-06-01 | 2 |
| 4 | Sneha | 2002-04-04 | Female | sneha@gmail.com | 9876543213 | Pune | 2022-06-01 | 3 |
| 5 | Karan | 2002-05-05 | Male | karan@gmail.com | 9876543214 | Surat | 2022-06-01 | 1 |
| 6 | Neha | 2002-06-06 | Female | neha@gmail.com | 9876543215 | Delhi | 2022-06-01 | 2 |
| 7 | Vikas | 2002-07-07 | Male | vikas@gmail.com | 9876543216 | Mumbai | 2022-06-01 | 1 |
| 8 | Pooja | 2002-08-08 | Female | pooja@gmail.com | 9876543217 | Surat | 2022-06-01 | 4 |
| 9 | Arjun | 2002-09-09 | Male | arjun@gmail.com | 9876543218 | Delhi | 2022-06-01 | 1 |
| 10 | Meera | 2002-10-10 | Female | meera@gmail.com | 9876543219 | Pune | 2022-06-01 | 3 |

**📸 Screenshot:**

![Students](ss/STUDENTS.png)

---

### 3. 👩‍🏫 Faculty

> Stores all faculty members and their department assignments.

**Schema:**

| Column | Type | Constraint | Description |
|--------|------|-----------|-------------|
| `faculty_id` | INT | `PRIMARY KEY` | Unique faculty identifier |
| `name` | VARCHAR(50) | — | Full name |
| `email` | VARCHAR(100) | — | Email address |
| `phone_number` | VARCHAR(15) | — | Contact number |
| `department_id` | INT | `FK → Departments` | Assigned department |

**Data:**

| faculty_id | name | email | phone_number | department_id |
|:---:|:---|:---|:---:|:---:|
| 1 | Dr Sharma | sharma@gmail.com | 9123456780 | 1 |
| 2 | Dr Patel | patel@gmail.com | 9123456781 | 2 |
| 3 | Dr Khan | khan@gmail.com | 9123456782 | 3 |
| 4 | Dr Mehta | mehta@gmail.com | 9123456783 | 4 |
| 5 | Dr Rao | rao@gmail.com | 9123456784 | 5 |
| 6 | Dr Singh | singh@gmail.com | 9123456785 | 6 |
| 7 | Dr Das | das@gmail.com | 9123456786 | 7 |
| 8 | Dr Iyer | iyer@gmail.com | 9123456787 | 8 |
| 9 | Dr Verma | verma@gmail.com | 9123456788 | 9 |
| 10 | Dr Joshi | joshi@gmail.com | 9123456789 | 10 |

**📸 Screenshot:**

![Faculty](ss/Faculty.png)

---

### 4. 📚 Courses

> Stores all courses offered and the faculty assigned to teach each one.

**Schema:**

| Column | Type | Constraint | Description |
|--------|------|-----------|-------------|
| `course_id` | INT | `PRIMARY KEY` | Unique course identifier |
| `course_name` | VARCHAR(50) | — | Name of the course |
| `faculty_id` | INT | `FK → Faculty` | Teaching faculty |

**Data:**

| course_id | course_name | faculty_id |
|:---:|:---|:---:|
| 1 | DBMS | 1 |
| 2 | Thermodynamics | 2 |
| 3 | Structures | 3 |
| 4 | Circuits | 4 |
| 5 | AI Basics | 5 |
| 6 | ML | 6 |
| 7 | Data Mining | 7 |
| 8 | Chemistry | 8 |
| 9 | Automobile Engg | 9 |
| 10 | Electronics | 10 |

**📸 Screenshot:**

![Courses](ss/Courses.png)

---

### 5. 📝 Enrollments

> Tracks which student enrolled in which course. A composite `UNIQUE` key prevents duplicate enrollments.

**Schema:**

| Column | Type | Constraint | Description |
|--------|------|-----------|-------------|
| `enrollment_id` | INT | `PRIMARY KEY` | Unique enrollment ID |
| `student_id` | INT | `FK → Students` | Enrolled student |
| `course_id` | INT | `FK → Courses` | Enrolled course |
| `enrollment_date` | DATE | — | Date of enrollment |
| *(composite)* | — | `UNIQUE(student_id, course_id)` | Prevents duplicate enrollment |

**Data:**

| enrollment_id | student_id | course_id | enrollment_date |
|:---:|:---:|:---:|:---:|
| 1 | 1 | 1 | 2022-07-01 |
| 2 | 2 | 2 | 2022-07-02 |
| 3 | 3 | 3 | 2022-07-03 |
| 4 | 4 | 4 | 2022-07-04 |
| 5 | 5 | 5 | 2022-07-05 |
| 6 | 6 | 6 | 2022-07-06 |
| 7 | 7 | 7 | 2022-07-07 |
| 8 | 8 | 8 | 2022-07-08 |
| 9 | 9 | 9 | 2022-07-09 |
| 10 | 10 | 10 | 2022-07-10 |

**📸 Screenshot:**

![Enrollments](ss/Enrollments.png)

---

### 6. 📅 Attendance

> Records daily attendance per student per course with Present / Absent / Late status.

**Schema:**

| Column | Type | Constraint | Description |
|--------|------|-----------|-------------|
| `attendance_id` | INT | `PRIMARY KEY` | Unique attendance record |
| `student_id` | INT | `FK → Students` | Student reference |
| `course_id` | INT | `FK → Courses` | Course reference |
| `attendance_date` | DATE | — | Date of class |
| `status` | VARCHAR(10) | — | `Present` / `Absent` / `Late` |

**Data:**

| attendance_id | student_id | course_id | attendance_date | status |
|:---:|:---:|:---:|:---:|:---:|
| 1 | 1 | 1 | 2022-07-02 | ✅ Present |
| 2 | 2 | 2 | 2022-07-03 | ❌ Absent |
| 3 | 3 | 3 | 2022-07-04 | ✅ Present |
| 4 | 4 | 4 | 2022-07-05 | ⏰ Late |
| 5 | 5 | 5 | 2022-07-06 | ✅ Present |
| 6 | 6 | 6 | 2022-07-07 | ❌ Absent |
| 7 | 7 | 7 | 2022-07-08 | ✅ Present |
| 8 | 8 | 8 | 2022-07-09 | ⏰ Late |
| 9 | 9 | 9 | 2022-07-10 | ✅ Present |
| 10 | 10 | 10 | 2022-07-11 | ❌ Absent |

**📸 Screenshot:**

![Attendance](ss/Attendance.png)

---

### 7. 🏆 Grades

> Stores the marks and letter grade each student received per course.

**Schema:**

| Column | Type | Constraint | Description |
|--------|------|-----------|-------------|
| `grade_id` | INT | `PRIMARY KEY` | Unique grade record |
| `student_id` | INT | `FK → Students` | Student reference |
| `course_id` | INT | `FK → Courses` | Course reference |
| `marks_obtained` | INT | — | Marks scored (out of 100) |
| `grade` | VARCHAR(2) | — | A / B / C / D |

**Data:**

| grade_id | student_id | course_id | marks_obtained | grade | performance |
|:---:|:---:|:---:|:---:|:---:|:---|
| 1 | 1 | 1 | 85 | 🥇 A | Excellent |
| 2 | 2 | 2 | 75 | 🥈 B | Good |
| 3 | 3 | 3 | 65 | 🥉 C | Average |
| 4 | 4 | 4 | 55 | D | Below Average |
| 5 | 5 | 5 | 95 | 🥇 A | Excellent |
| 6 | 6 | 6 | 45 | D | Below Average |
| 7 | 7 | 7 | 88 | 🥇 A | Excellent |
| 8 | 8 | 8 | 70 | 🥈 B | Good |
| 9 | 9 | 9 | 92 | 🥇 A | Excellent |
| 10 | 10 | 10 | 60 | 🥉 C | Average |

**📸 Screenshot:**

![Grades](ss/Grades.png)

---

## 🧠 SQL Concepts Covered

| # | Concept | Topics Practiced |
|:---:|:---|:---|
| 1 | **DDL** | `CREATE TABLE`, `PRIMARY KEY`, `FOREIGN KEY`, `UNIQUE` |
| 2 | **CRUD Operations** | `INSERT`, `UPDATE`, `DELETE`, `SELECT` |
| 3 | **Clauses** | `WHERE`, `HAVING`, `LIMIT`, `ORDER BY`, `GROUP BY` |
| 4 | **Operators** | `AND`, `OR`, `NOT`, `IN`, `BETWEEN`, `IS NULL` |
| 5 | **Aggregate Functions** | `AVG()`, `COUNT()`, `MAX()`, `MIN()` |
| 6 | **JOINs** | `INNER JOIN`, `LEFT JOIN`, `RIGHT JOIN`, `FULL OUTER` via UNION |
| 7 | **Subqueries** | Scalar and correlated subqueries |
| 8 | **Date Functions** | `MONTH()`, `YEAR()`, `CURDATE()`, `DATE_FORMAT()` |
| 9 | **String Functions** | `UPPER()`, `TRIM()`, `IFNULL()` |
| 10 | **Window Functions** | `RANK() OVER`, `COUNT() OVER`, `PARTITION BY` |
| 11 | **CASE Expressions** | Performance labels, attendance categorization |

---

## ⚡ Key Queries Snapshot

```sql
-- 🏅 Rank students by marks
SELECT student_id, marks_obtained,
  RANK() OVER (ORDER BY marks_obtained DESC) AS rank_no
FROM Grades;
```

```sql
-- 📊 Attendance category per student
SELECT student_id,
  CASE
    WHEN COUNT(CASE WHEN status='Present' THEN 1 END)*100/COUNT(*) > 80 THEN 'Regular'
    WHEN COUNT(CASE WHEN status='Present' THEN 1 END)*100/COUNT(*) BETWEEN 50 AND 80 THEN 'Irregular'
    ELSE 'Defaulter'
  END AS category
FROM Attendance
GROUP BY student_id;
```

```sql
-- 🔗 Students with their departments (INNER JOIN)
SELECT s.name, d.department_name
FROM Students s
INNER JOIN Departments d ON s.department_id = d.department_id;
```

```sql
-- 📈 Students scoring above average (Subquery)
SELECT * FROM Grades
WHERE marks_obtained > (SELECT AVG(marks_obtained) FROM Grades);
```

```sql
-- 🎯 Performance label using CASE
SELECT student_id, marks_obtained,
  CASE
    WHEN marks_obtained > 90 THEN 'Excellent'
    WHEN marks_obtained BETWEEN 75 AND 90 THEN 'Good'
    ELSE 'Needs Improvement'
  END AS performance
FROM Grades;
```

---

## 🔐 Constraints & Keys Summary

| Table | Primary Key | Foreign Key(s) | Special Constraint |
|:---|:---:|:---|:---|
| `Departments` | department_id | — | — |
| `Students` | student_id | department_id → Departments | — |
| `Faculty` | faculty_id | department_id → Departments | — |
| `Courses` | course_id | faculty_id → Faculty | — |
| `Enrollments` | enrollment_id | student_id, course_id | `UNIQUE(student_id, course_id)` |
| `Attendance` | attendance_id | student_id, course_id | — |
| `Grades` | grade_id | student_id, course_id | — |

---

## 🚀 How to Run

```bash
# Step 1 — Open MySQL
mysql -u root -p

# Step 2 — Run the SQL file
SOURCE /path/to/students.SQL;

# Step 3 — Verify
USE d;
SHOW TABLES;
```

**Expected output:**
```
+─────────────────+
| Tables_in_d     |
+─────────────────+
| Attendance      |
| Courses         |
| Departments     |
| Enrollments     |
| Faculty         |
| Grades          |
| Students        |
+─────────────────+
```

---

<div align="center">

### 🌟 Built with passion for learning SQL 🌟

![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white)
![Normalized](https://img.shields.io/badge/Database-Normalized-success?style=flat-square)
![Academic](https://img.shields.io/badge/Project-Academic-blueviolet?style=flat-square)

> *"Data is the new oil — and SQL is the refinery."*

⭐ **If this project helped you, give it a star!** ⭐

</div>
