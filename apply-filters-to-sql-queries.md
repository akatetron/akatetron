# Apply Filters to SQL Queries 🗄️

## Objective
Demonstrate how SQL filters can be used to investigate security incidents,
analyze suspicious login attempts, and manage employee system access.

## Tools Used
- SQL (MySQL)
- `log_in_attempts` table
- `employees` table

---

## Tasks & Queries

### 1️⃣ Retrieve After Hours Failed Login Attempts
**Scenario:** A potential security incident occurred after business hours (after 18:00).
All failed after-hours login attempts needed investigation.

**Query:**
```sql
SELECT *
FROM log_in_attempts
WHERE login_time > '18:00' AND success = FALSE;
```

**Explanation:**
- `WHERE login_time > '18:00'` filters for attempts after business hours
- `AND success = FALSE` filters for only failed attempts
- Combined `AND` operator narrows results to suspicious activity only

---

### 2️⃣ Retrieve Login Attempts on Specific Dates
**Scenario:** A suspicious event occurred on 2022-05-09. Login activity
on that date and the day before needed investigation.

**Query:**
```sql
SELECT *
FROM log_in_attempts
WHERE login_date = '2022-05-09' OR login_date = '2022-05-08';
```

**Explanation:**
- `OR` operator captures activity across both dates
- Returns all login attempts from either date for full investigation scope

---

### 3️⃣ Retrieve Login Attempts Outside of Mexico
**Scenario:** Investigation revealed suspicious login attempts
originating from outside Mexico.

**Query:**
```sql
SELECT *
FROM log_in_attempts
WHERE NOT country LIKE 'MEX%';
```

**Explanation:**
- `NOT` operator excludes Mexico from results
- `LIKE 'MEX%'` accounts for both `MEX` and `MEXICO` representations in dataset
- `%` wildcard matches any characters following MEX

---

### 4️⃣ Retrieve Employees in Marketing (East Building)
**Scenario:** Team needed to update computers for Marketing department
employees in the East building.

**Query:**
```sql
SELECT *
FROM employees
WHERE department = 'Marketing' AND office LIKE 'East%';
```

**Explanation:**
- `AND` operator filters for both conditions simultaneously
- `LIKE 'East%'` matches all East building office numbers

---

### 5️⃣ Retrieve Employees in Finance or Sales
**Scenario:** Different security update needed for Finance and Sales departments.

**Query:**
```sql
SELECT *
FROM employees
WHERE department = 'Finance' OR department = 'Sales';
```

**Explanation:**
- `OR` operator used because employees from either department are needed
- Returns complete list across both departments

---

### 6️⃣ Retrieve All Employees Not in IT
**Scenario:** Security update needed for all employees outside
the Information Technology department.

**Query:**
```sql
SELECT *
FROM employees
WHERE NOT department = 'Information Technology';
```

**Explanation:**
- `NOT` operator excludes IT department from results
- Returns all other employees who need the security update

---

## Summary
Applied SQL filters to investigate security incidents and manage employee
system updates using two tables: `log_in_attempts` and `employees`.

**Operators used:**
- `AND` — both conditions must be true
- `OR` — either condition can be true
- `NOT` — excludes matching results
- `LIKE` with `%` wildcard — pattern matching

**Key takeaway:** SQL filtering is a powerful tool for SOC analysts to
quickly isolate suspicious activity and scope investigations efficiently.
