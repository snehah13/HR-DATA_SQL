
# HR Data SQL Practice – Oracle Live SQL

## 📌 Overview
This project contains a collection of SQL queries and examples using Oracle's **HR schema** on **Oracle Live SQL**.  
It is designed for practicing SQL concepts including data retrieval, filtering, grouping, joins, subqueries, aggregation, views, and query optimization techniques.

The HR schema contains sample data of employees, departments, jobs, locations, countries, and regions — perfect for learning relational database concepts.

---

## 📂 Dataset: Oracle HR Schema
The **HR schema** includes the following key tables:

| Table Name   | Description |
|--------------|-------------|
| **EMPLOYEES** | Employee details including name, salary, hire date, job, and department. |
| **DEPARTMENTS** | Department IDs, names, and managers. |
| **JOBS** | Job titles and salary ranges. |
| **LOCATIONS** | Office locations, cities, and countries. |
| **COUNTRIES** | Country codes and names. |
| **REGIONS** | Geographic regions for countries. |
etc

---

## 🛠 SQL Features Covered

1. **SELECT, WHERE, ORDER BY, GROUP BY**  
   - Filtering data  
   - Sorting results  
   - Grouping and counting

2. **JOINS**  
   - INNER JOIN  
   - LEFT JOIN  
   - RIGHT JOIN  

3. **Subqueries**  
   - Single-row subqueries  
   - Multi-row subqueries with `IN` and `HAVING`

4. **Aggregate Functions**  
   - `SUM`, `AVG`, `COUNT`, `MAX`, `MIN`etc

5. **Views**  
   - Creating reusable queries as views

6. **Optimization Techniques (Theory)**  
   - Understanding indexes (existing in HR schema)  
   - Using `EXPLAIN PLAN` for performance analysis
     
**No CREATE INDEX command in Live SQL (restricted privileges).

Existing HR schema indexes already help optimize queries.

Use EXPLAIN PLAN to check query execution steps.

---

## ▶ How to Run
1. Log in to [Oracle Live SQL](https://livesql.oracle.com/).
2. Use the default **HR schema**.
3. Copy and paste the SQL script from this repository.
4. Execute section by section to see results.
5. Use `EXPLAIN PLAN` to understand performance.

---

## 📈 Example Queries

```sql
-- List employees in department 90 ordered by salary
SELECT employee_id, first_name, last_name, salary
FROM employees
WHERE department_id = 90
ORDER BY salary DESC;

-- Departments where max salary exceeds 12000
SELECT department_id, department_name
FROM departments
WHERE department_id IN (
    SELECT department_id

**Author:** Sneha H  
**Dataset Source:** [https://livesql.oracle.com/ords/f?p=590:1000:1965933137343:::::]  
**License:** MIT
    FROM employees
    GROUP BY department_id

**Author:** Sneha H  
    HAVING MAX(salary) > 12000
);
