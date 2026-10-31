# Apply Filters to SQL Queries

## Project Description
In this activity, I used SQL queries to filter security logs and employee database tables. The objective was to investigate potential security incidents—such as after-hours failed logins—and filter employee details based on department and office criteria using relational and logical operators.

---

## SQL Queries Executed

### 1. After-Hours Failed Login Attempts
Queried the `log_in_attempts` table to find failed logins (`success = 0`) occurring after 18:00:
```sql
SELECT * 
FROM log_in_attempts 
WHERE login_time > '18:00' AND success = 0;
```

### 2. Login Attempts on Specific Dates
Filtered login logs for activity occurring on or after May 9, 2022 (2022-05-09):

```sql

SELECT * 
FROM log_in_attempts 
WHERE login_date >= '2022-05-09';
```
### 3. Login Attempts Outside of Mexico
Identified login attempts coming from locations outside of Mexico:

```sql

SELECT * 
FROM log_in_attempts 
WHERE country NOT LIKE 'MEX%';
```
### 4. Marketing Employees in East Offices
Queried employee records for staff in Marketing located in East-region offices:

```sql

SELECT * 
FROM employees 
WHERE department = 'Marketing' AND office LIKE 'EAST%';
```
### 5. Employees in Finance or Sales
Retrieved all employees belonging to either Finance or Sales using the OR operator:

```sql

SELECT * 
FROM employees 
WHERE department = 'Finance' OR department = 'Sales';
```
### 6. Employees Outside the IT Department
Filtered out IT personnel to audit non-IT employee records:

```sql
SELECT * 
FROM employees 
WHERE NOT department = 'IT';
```
