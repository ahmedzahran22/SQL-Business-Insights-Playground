# 🚀 SQL Business Insights Playground

A practical and structured SQL guide focused on real-world data analysis scenarios.
This project goes beyond basic SQL syntax and demonstrates how SQL is used to extract insights from data.

---

## 📌 Project Overview

This repository covers:

* Database creation and table design
* Data manipulation (INSERT, UPDATE, DELETE)
* Data querying (SELECT, WHERE)
* Advanced SQL (JOIN, GROUP BY, HAVING)
* Real-world business use cases

---

## 🧱 Database Schema

### Employees Table

| Column     | Type     | Description     |
| ---------- | -------- | --------------- |
| id         | INT (PK) | Employee ID     |
| name       | VARCHAR  | Employee Name   |
| age        | INT      | Age             |
| salary     | INT      | Salary          |
| department | VARCHAR  | Department Name |

### Departments Table

| Column    | Type     | Description     |
| --------- | -------- | --------------- |
| dept_id   | INT (PK) | Department ID   |
| dept_name | VARCHAR  | Department Name |
| budget    | INT      | Budget          |

---

## ⚙️ Setup

```sql
CREATE DATABASE Company;
USE Company;

CREATE TABLE employees (
    id INT PRIMARY KEY,
    name VARCHAR(50),
    age INT,
    salary INT,
    department VARCHAR(50)
);

CREATE TABLE departments (
    dept_id INT PRIMARY KEY,
    dept_name VARCHAR(50),
    budget INT
);
```

---

## ➕ Insert Sample Data

```sql
INSERT INTO employees VALUES (1, 'Alice', 30, 5000, 'Engineering');
INSERT INTO employees VALUES (2, 'Bob', 25, 4000, 'Marketing');
INSERT INTO employees VALUES (3, 'Charlie', 35, 6000, 'Engineering');

INSERT INTO departments VALUES (1, 'Engineering', 50000);
INSERT INTO departments VALUES (2, 'Marketing', 30000);
```

---

## 🔍 Basic Queries

### Get all employees

```sql
SELECT * FROM employees;
```

### Get specific columns

```sql
SELECT name, salary FROM employees;
```

### Filter data

```sql
SELECT * FROM employees WHERE salary > 5000;
```

---

## 🔗 JOIN Example

```sql
SELECT e.name, d.dept_name
FROM employees e
JOIN departments d
ON e.department = d.dept_name;
```

---

## 📊 Aggregation

### Count employees per department

```sql
SELECT department, COUNT(*) 
FROM employees
GROUP BY department;
```

### Average salary

```sql
SELECT department, AVG(salary)
FROM employees
GROUP BY department;
```

---

## 🧠 Business Use Cases

### 1. Highest Paid Department

```sql
SELECT department, MAX(salary)
FROM employees
GROUP BY department;
```

### 2. Employees Above Average Salary

```sql
SELECT * FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```

---

## ⚡ Performance Tips

* Avoid using `SELECT *`
* Use indexes on frequently filtered columns
* Always filter using `WHERE` when possible

---

## 📁 Project Structure

```
SQL-Business-Insights-Playground/
│
├── README.md
├── schema.sql
├── data.sql
├── queries.sql
└── case_study.sql
```

---

## 💡 Future Improvements

* Add Window Functions (ROW_NUMBER, NTILE)
* Add real datasets
* Build dashboards using Power BI

---

## 👨‍💻 Author

Ahmed Zahran
