# 🎓 Student Database Management System

A MySQL-based relational database project for managing students, faculty, courses, enrollments, attendance, and grades in an academic institution.

---

## 📁 Project Structure

```
students.SQL       → Full SQL script (schema + data + queries)
README.md          → Project documentation
screenshots/       → Table output screenshots
```

---

## 🗄️ Database Schema

The database `d` contains **7 tables** with relational integrity enforced via foreign keys.

### Entity Relationship Overview

```
Departments ──< Students >── Enrollments ──< Courses >── Faculty
                    │                             │
                Attendance                     Grades
```

---

## 📊 Tables & Screenshots

### 1. Departments
Stores all academic departments offered by the institution.

| Column | Type | Description |
|--------|------|-------------|
| department_id | INT (PK) | Unique department ID |
| department_name | VARCHAR(50) | Name of the department |

![Departments Table](d1.png)

---

### 2. Students
Contains personal and academic information of all enrolled students.

| Column | Type | Description |
|--------|------|-------------|
| student_id | INT (PK) | Unique student ID |
| name | VARCHAR(50) | Student name |
| dob | DATE | Date of birth |
| gender | VARCHAR(10) | Gender |
| email | VARCHAR(100) | Email address |
| phone_number | VARCHAR(15) | Phone number |
| address | VARCHAR(100) | Residential address |
| admission_date | DATE | Date of admission |
| department_id | INT (FK) | References Departments |

![Students Table](s1.png)

---

### 3. Faculty
Stores details of faculty members and their department assignments.

| Column | Type | Description |
|--------|------|-------------|
| faculty_id | INT (PK) | Unique faculty ID |
| name | VARCHAR(50) | Faculty name |
| email | VARCHAR(100) | Email address |
| phone_number | VARCHAR(15) | Phone number |
| department_id | INT (FK) | References Departments |

![Faculty Table](f1.png)

---

### 4. Courses
Contains course information along with the assigned faculty member.

| Column | Type | Description |
|--------|------|-------------|
| course_id | INT (PK) | Unique course ID |
| course_name | VARCHAR(50) | Name of the course |
| faculty_id | INT (FK) | References Faculty |

![Courses Table](c1.png)

---

### 5. Enrollments
Tracks which students are enrolled in which courses, with a unique constraint on (student_id, course_id).

| Column | Type | Description |
|--------|------|-------------|
| enrollment_id | INT (PK) | Unique enrollment ID |
| student_id | INT (FK) | References Students |
| course_id | INT (FK) | References Courses |
| enrollment_date | DATE | Date of enrollment |

![Enrollments Table](e1.png)

---

### 6. Attendance
Records daily attendance status for each student per course.

| Column | Type | Description |
|--------|------|-------------|
| attendance_id | INT (PK) | Unique record ID |
| student_id | INT (FK) | References Students |
| course_id | INT (FK) | References Courses |
| attendance_date | DATE | Date of class |
| status | VARCHAR(10) | Present / Absent / Late |

![Attendance Table](a1.png)

---

### 7. Grades
Stores marks and grade obtained by students in each course.

| Column | Type | Description |
|--------|------|-------------|
| grade_id | INT (PK) | Unique grade record ID |
| student_id | INT (FK) | References Students |
| course_id | INT (FK) | References Courses |
| marks_obtained | INT | Marks scored |
| grade | VARCHAR(2) | Letter grade (A/B/C/D) |

![Grades Table](g1.png)

---

## ⚙️ SQL Features Covered

| # | Feature | Description |
|---|---------|-------------|
| 1 | **DDL** | CREATE TABLE, PRIMARY KEY, FOREIGN KEY, UNIQUE |
| 2 | **DML** | INSERT, UPDATE, DELETE |
| 3 | **Clauses** | WHERE, HAVING, LIMIT, ORDER BY, GROUP BY |
| 4 | **Operators** | AND, OR, NOT, IN, IS NULL |
| 5 | **Aggregate Functions** | COUNT, AVG, MAX, MIN |
| 6 | **JOINs** | INNER, LEFT, RIGHT, FULL OUTER (via UNION) |
| 7 | **Subqueries** | Nested SELECT statements |
| 8 | **Date Functions** | MONTH(), YEAR(), CURDATE(), DATE_FORMAT() |
| 9 | **String Functions** | UPPER(), TRIM(), IFNULL() |
| 10 | **Window Functions** | RANK(), COUNT() OVER, PARTITION BY |
| 11 | **CASE Expressions** | Conditional logic in SELECT |

---

## 🚀 How to Run

1. Make sure MySQL is installed and running.
2. Open MySQL shell or MySQL Workbench.
3. Run the script:

```bash
mysql -u root -p < students.SQL
```

Or paste the SQL content directly into your MySQL client.

---

## 📋 Sample Queries

### Students in Computer Science
```sql
SELECT s.*
FROM Students s
JOIN Departments d ON s.department_id = d.department_id
WHERE d.department_name = 'Computer Science';
```

### Top Scoring Students
```sql
SELECT * FROM Grades
ORDER BY marks_obtained DESC
LIMIT 10;
```

### Student Performance Classification
```sql
SELECT student_id, marks_obtained,
  CASE
    WHEN marks_obtained > 90 THEN 'Excellent'
    WHEN marks_obtained BETWEEN 75 AND 90 THEN 'Good'
    ELSE 'Needs Improvement'
  END AS performance
FROM Grades;
```

### Rank Students by Marks
```sql
SELECT student_id, marks_obtained,
  RANK() OVER (ORDER BY marks_obtained DESC) AS rank_no
FROM Grades;
```

---

## 🗂️ Sample Data

- **10 Departments**: Computer Science, Mechanical, Civil, Electrical, IT, AI, Data Science, Chemical, Automobile, Electronics  
- **10 Students**: Amit, Riya, Rahul, Sneha, Karan, Neha, Vikas, Pooja, Arjun, Meera  
- **10 Faculty Members**: Dr. Sharma, Dr. Patel, Dr. Khan, Dr. Mehta, Dr. Rao, Dr. Singh, Dr. Das, Dr. Iyer, Dr. Verma, Dr. Joshi  
- **10 Courses**: DBMS, Thermodynamics, Structures, Circuits, AI Basics, ML, Data Mining, Chemistry, Automobile Engg, Electronics  

---

## 👨‍💻 Tech Stack

- **Database**: MySQL 8+
- **Language**: SQL
- **Tools**: MySQL Workbench / CLI

---

*Project created for learning and demonstrating core SQL concepts in an academic management context.*
