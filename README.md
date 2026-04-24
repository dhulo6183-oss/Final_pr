# 🎓 Student Management System — SQL Project

A complete relational database project built with **MySQL**, covering student records, faculty, courses, enrollments, attendance, and grades. Includes full CRUD operations, joins, window functions, aggregate queries, and more.

---

## 📁 Project Structure

```
student-management/
│
├── students.SQL            ← Main SQL file (DDL + DML + Queries)
│
├── tables/
│   ├── DEPARTMENTS.png     ← Screenshot: Departments table data
│   ├── STUDENTS.png        ← Screenshot: Students table data
│   ├── Faculty.png         ← Screenshot: Faculty table data
│   ├── Courses.png         ← Screenshot: Courses table data
│   ├── Enrollments.png     ← Screenshot: Enrollments table data
│   ├── Attendance.png      ← Screenshot: Attendance table data
│   └── Grades.png          ← Screenshot: Grades table data
│
└── README.md               ← This file
```

---

## 🗄️ Database Schema

### 1. `Departments`
Stores department information.

| Column          | Type        | Constraint  |
|-----------------|-------------|-------------|
| department_id   | INT         | PRIMARY KEY |
| department_name | VARCHAR(50) |             |

**Sample Data:** Computer Science, Mechanical, Civil, Electrical, IT, AI, Data Science, Chemical, Automobile, Electronics

---

### 2. `Students`
Stores student personal and academic details.

| Column         | Type         | Constraint                        |
|----------------|--------------|-----------------------------------|
| student_id     | INT          | PRIMARY KEY                       |
| name           | VARCHAR(50)  |                                   |
| dob            | DATE         |                                   |
| gender         | VARCHAR(10)  |                                   |
| email          | VARCHAR(100) |                                   |
| phone_number   | VARCHAR(15)  |                                   |
| address        | VARCHAR(100) |                                   |
| admission_date | DATE         |                                   |
| department_id  | INT          | FOREIGN KEY → Departments         |

**Sample Data:** 10 students from cities like Surat, Delhi, Mumbai, Pune — admitted on 2022-06-01.

---

### 3. `Faculty`
Stores faculty contact and department information.

| Column        | Type         | Constraint                |
|---------------|--------------|---------------------------|
| faculty_id    | INT          | PRIMARY KEY               |
| name          | VARCHAR(50)  |                           |
| email         | VARCHAR(100) |                           |
| phone_number  | VARCHAR(15)  |                           |
| department_id | INT          | FOREIGN KEY → Departments |

**Sample Data:** Dr Sharma, Dr Patel, Dr Khan, Dr Mehta, Dr Rao, Dr Singh, Dr Das, Dr Iyer, Dr Verma, Dr Joshi

---

### 4. `Courses`
Maps courses to faculty members.

| Column      | Type        | Constraint           |
|-------------|-------------|----------------------|
| course_id   | INT         | PRIMARY KEY          |
| course_name | VARCHAR(50) |                      |
| faculty_id  | INT         | FOREIGN KEY → Faculty|

**Sample Data:** DBMS, Thermodynamics, Structures, Circuits, AI Basics, ML, Data Mining, Chemistry, Automobile Engg, Electronics

---

### 5. `Enrollments`
Tracks which students are enrolled in which courses.

| Column          | Type | Constraint                         |
|-----------------|------|------------------------------------|
| enrollment_id   | INT  | PRIMARY KEY                        |
| student_id      | INT  | FOREIGN KEY → Students             |
| course_id       | INT  | FOREIGN KEY → Courses              |
| enrollment_date | DATE |                                    |
|                 |      | UNIQUE(student_id, course_id)      |

---

### 6. `Attendance`
Tracks daily attendance per student per course.

| Column          | Type        | Constraint            |
|-----------------|-------------|-----------------------|
| attendance_id   | INT         | PRIMARY KEY           |
| student_id      | INT         | FOREIGN KEY → Students|
| course_id       | INT         | FOREIGN KEY → Courses |
| attendance_date | DATE        |                       |
| status          | VARCHAR(10) | Present / Absent / Late|

---

### 7. `Grades`
Stores marks and letter grades per student per course.

| Column         | Type        | Constraint            |
|----------------|-------------|-----------------------|
| grade_id       | INT         | PRIMARY KEY           |
| student_id     | INT         | FOREIGN KEY → Students|
| course_id      | INT         | FOREIGN KEY → Courses |
| marks_obtained | INT         |                       |
| grade          | VARCHAR(2)  | A / B / C / D         |

**Sample Data:** Marks range from 45 to 95; grades A, B, C, D assigned accordingly.

---

## 🔗 Entity Relationship Overview

```
Departments
    ├── Students (department_id)
    └── Faculty  (department_id)
           └── Courses (faculty_id)
                  ├── Enrollments (course_id) ←── Students (student_id)
                  ├── Attendance  (course_id) ←── Students (student_id)
                  └── Grades      (course_id) ←── Students (student_id)
```

---

## 📋 SQL Queries Reference

### 🔧 1. CRUD Operations

```sql
-- INSERT a new student (with NULL email)
INSERT INTO Students VALUES
(11,'Rohit','2003-01-01','Male',NULL,'9999999999','Surat','2023-06-01',1);

-- UPDATE phone number
UPDATE Students
SET phone_number = '8888888888'
WHERE student_id = 1;

-- DELETE a student
DELETE FROM Students WHERE student_id = 11;
```

---

### 🔍 2. SQL Clauses — WHERE, HAVING, LIMIT

```sql
-- Students in Computer Science department
SELECT s.*
FROM Students s
JOIN Departments d ON s.department_id = d.department_id
WHERE d.department_name = 'Computer Science';

-- Top 10 highest scoring students
SELECT * FROM Grades
ORDER BY marks_obtained DESC
LIMIT 10;

-- Students with attendance below 75%
SELECT student_id,
  COUNT(CASE WHEN status='Present' THEN 1 END)*100/COUNT(*) AS attendance_percentage
FROM Attendance
GROUP BY student_id
HAVING COUNT(CASE WHEN status='Present' THEN 1 END)*100/COUNT(*) < 75;
```

---

### ⚙️ 3. SQL Operators — AND, OR, NOT

```sql
-- Students with marks below 50 (failing)
SELECT g.student_id
FROM Grades g
WHERE marks_obtained < 50;

-- Students with marks > 90 OR marked Present
SELECT DISTINCT s.student_id
FROM Students s
LEFT JOIN Grades g ON s.student_id = g.student_id
LEFT JOIN Attendance a ON s.student_id = a.student_id
WHERE g.marks_obtained > 90 OR a.status = 'Present';

-- Faculty NOT assigned to any course
SELECT * FROM Faculty
WHERE faculty_id NOT IN (SELECT faculty_id FROM Courses);
```

---

### 📊 4. ORDER BY & GROUP BY

```sql
-- Alphabetical list of students
SELECT * FROM Students ORDER BY name;

-- Count students per department
SELECT department_id, COUNT(*) AS total_students
FROM Students
GROUP BY department_id;

-- Average marks per course
SELECT course_id, AVG(marks_obtained) AS avg_marks
FROM Grades
GROUP BY course_id;
```

---

### 🧮 5. Aggregate Functions

```sql
-- Average attendance count
SELECT AVG(att_count)
FROM (
  SELECT COUNT(*) AS att_count
  FROM Attendance
  WHERE status='Present'
  GROUP BY student_id
);

-- Highest & lowest marks per course
SELECT course_id,
  MAX(marks_obtained) AS highest,
  MIN(marks_obtained) AS lowest
FROM Grades
GROUP BY course_id;

-- Total students per department
SELECT department_id, COUNT(*)
FROM Students
GROUP BY department_id;
```

---

### 🔗 6. JOINs

```sql
-- INNER JOIN: Students with their department names
SELECT s.name, d.department_name
FROM Students s
INNER JOIN Departments d ON s.department_id = d.department_id;

-- LEFT JOIN: Students NOT enrolled in any course
SELECT s.*
FROM Students s
LEFT JOIN Enrollments e ON s.student_id = e.student_id
WHERE e.student_id IS NULL;

-- RIGHT JOIN: Courses without a faculty assigned
SELECT c.*
FROM Faculty f
RIGHT JOIN Courses c ON f.faculty_id = c.faculty_id
WHERE f.faculty_id IS NULL;

-- FULL OUTER JOIN (via UNION): All students with or without grades
SELECT s.student_id, g.grade
FROM Students s LEFT JOIN Grades g ON s.student_id = g.student_id
UNION
SELECT s.student_id, g.grade
FROM Students s RIGHT JOIN Grades g ON s.student_id = g.student_id;
```

---

### 🔄 7. Subqueries

```sql
-- Students with marks above class average
SELECT *
FROM Grades
WHERE marks_obtained > (SELECT AVG(marks_obtained) FROM Grades);

-- Students absent more than 10 times
SELECT student_id
FROM Attendance
WHERE status='Absent'
GROUP BY student_id
HAVING COUNT(*) > 10;
```

---

### 📅 8. Date Functions

```sql
-- Extract month from attendance date
SELECT MONTH(attendance_date) AS month FROM Attendance;

-- Years since student admission
SELECT student_id,
  YEAR(CURDATE()) - YEAR(admission_date) AS years
FROM Students;

-- Format date as DD-MM-YYYY
SELECT DATE_FORMAT(attendance_date,'%d-%m-%Y') FROM Attendance;
```

---

### 🔤 9. String Functions

```sql
-- Uppercase faculty names
SELECT UPPER(name) FROM Faculty;

-- Trim whitespace from student names
SELECT TRIM(name) FROM Students;

-- Replace NULL emails with placeholder
SELECT IFNULL(email,'Email Not Provided') FROM Students;
```

---

### 🪟 10. Window Functions

```sql
-- Rank students by marks (highest first)
SELECT student_id, marks_obtained,
  RANK() OVER (ORDER BY marks_obtained DESC) AS rank_no
FROM Grades;

-- Cumulative attendance count per student
SELECT student_id,
  COUNT(*) OVER (PARTITION BY student_id) AS total_attendance
FROM Attendance;

-- Running total of enrollments per month
SELECT MONTH(enrollment_date) AS month,
  COUNT(*) OVER (ORDER BY MONTH(enrollment_date)) AS running_total
FROM Enrollments;
```

---

### 🔀 11. CASE Expressions

```sql
-- Student performance category based on marks
SELECT student_id, marks_obtained,
  CASE
    WHEN marks_obtained > 90 THEN 'Excellent'
    WHEN marks_obtained BETWEEN 75 AND 90 THEN 'Good'
    ELSE 'Needs Improvement'
  END AS performance
FROM Grades;

-- Attendance regularity category
SELECT student_id,
  CASE
    WHEN COUNT(CASE WHEN status='Present' THEN 1 END)*100/COUNT(*) > 80 THEN 'Regular'
    WHEN COUNT(CASE WHEN status='Present' THEN 1 END)*100/COUNT(*) BETWEEN 50 AND 80 THEN 'Irregular'
    ELSE 'Defaulter'
  END AS category
FROM Attendance
GROUP BY student_id;
```

---

## 🖼️ Table Screenshots

| Table        | Preview File            | Description                              |
|--------------|-------------------------|------------------------------------------|
| Departments  | `tables/DEPARTMENTS.png`| 10 engineering departments               |
| Students     | `tables/STUDENTS.png`   | 10 students with personal/dept info      |
| Faculty      | `tables/Faculty.png`    | 10 faculty members with contact info     |
| Courses      | `tables/Courses.png`    | 10 courses mapped to faculty             |
| Enrollments  | `tables/Enrollments.png`| Student-course enrollment records        |
| Attendance   | `tables/Attendance.png` | Attendance records (Present/Absent/Late) |
| Grades       | `tables/Grades.png`     | Marks and letter grades per student      |

---

## ⚙️ How to Run

1. Open MySQL Workbench or any MySQL client.
2. Run the full `students.SQL` file:
   ```sql
   SOURCE /path/to/students.SQL;
   ```
3. Or execute section by section — DDL first, then DML inserts, then queries.

---

## 📌 Key Concepts Covered

| Concept             | Description                                      |
|---------------------|--------------------------------------------------|
| DDL                 | CREATE TABLE with PRIMARY KEY, FOREIGN KEY, UNIQUE|
| DML                 | INSERT, UPDATE, DELETE                           |
| Clauses             | WHERE, HAVING, LIMIT, ORDER BY, GROUP BY         |
| Operators           | AND, OR, NOT, IN, NOT IN                         |
| Joins               | INNER, LEFT, RIGHT, FULL OUTER (via UNION)       |
| Aggregate Functions | COUNT, AVG, MAX, MIN                             |
| Subqueries          | Scalar & correlated subqueries                   |
| Date Functions      | MONTH(), YEAR(), CURDATE(), DATE_FORMAT()        |
| String Functions    | UPPER(), TRIM(), IFNULL()                        |
| Window Functions    | RANK(), COUNT() OVER PARTITION BY                |
| CASE Expressions    | Conditional logic inside SELECT                  |

---

## 👨‍💻 Author

Built as a complete SQL learning project demonstrating core relational database concepts using a Student Management System domain.
