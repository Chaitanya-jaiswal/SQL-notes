# 📘 Lecture 11: Limiting Records (TOP, LIMIT, FETCH FIRST)

> This lecture explains how to restrict the number of rows returned by a SELECT query.

---

## 🔹 Why Do We Limit Records?

* Large tables may contain **thousands of rows**
* Fetching all rows:

  * Reduces performance
  * Is often unnecessary
* Limiting rows helps in:

  * Reports
  * Dashboards
  * Testing queries
  * Pagination

---

## 🔹 Concept: Limiting Result Set

SQL provides **different keywords** for limiting rows depending on the database system:

| Database               | Keyword     |
| ---------------------- | ----------- |
| SQL Server / MS Access | TOP         |
| MySQL                  | LIMIT       |
| Oracle (new)           | FETCH FIRST |
| Oracle (old)           | ROWNUM      |

📌 **Concept is same**, syntax differs.

---

## 🔹 SELECT TOP (SQL Server / MS Access)

* Returns the **first N rows**
* Applied after sorting (if ORDER BY is used)

```sql
SELECT TOP 5 *
FROM Customers;
```

➡ Returns **first 5 records** from the table.

---

## 🔹 LIMIT (MySQL)

* Used at the **end of the query**
* Most common in MySQL and PostgreSQL

```sql
SELECT *
FROM Customers
LIMIT 5;
```

➡ Returns **first 5 rows**.

---

## 🔹 FETCH FIRST (Oracle – Modern)

```sql
SELECT *
FROM Customers
FETCH FIRST 5 ROWS ONLY;
```

➡ Standard SQL-style row limiting.

---

## 🔹 Using LIMIT with WHERE

* WHERE filters rows
* LIMIT restricts number of filtered rows

```sql
SELECT *
FROM Customers
WHERE Country = 'Germany'
LIMIT 3;
```

➡ Returns **3 German customers**.

---

## 🔹 Using TOP / LIMIT with ORDER BY (Very Important ⭐)

* ORDER BY is applied **before** limiting
* Helps get:

  * Top salaries
  * Highest marks
  * Latest records

### Example (MySQL):

```sql
SELECT *
FROM Customers
ORDER BY CustomerName DESC
LIMIT 3;
```

➡ Returns **top 3 names in reverse alphabetical order**.

📌 Without ORDER BY → result order is unpredictable.

---

## 🔹 TOP with PERCENT (Conceptual)

* Used in SQL Server
* Returns **percentage of rows**

```sql
SELECT TOP 50 PERCENT *
FROM Customers;
```

➡ Returns **half of the table records**.

---

## 🔹 Logical Execution Order (Exam Favorite ⭐)

1. FROM
2. WHERE
3. SELECT
4. ORDER BY
5. LIMIT / TOP / FETCH

📌 Limiting always happens **at the end**.

---

## 🔹 Common Mistakes (Exam Favorites ⭐)

* Forgetting ORDER BY before LIMIT
* Assuming LIMIT gives “top” values automatically
* Mixing syntax of different databases
* Expecting last rows without ORDER BY

---

## 🔹 TOP / LIMIT vs WHERE

| WHERE                   | LIMIT / TOP     |
| ----------------------- | --------------- |
| Filters rows            | Restricts count |
| Based on condition      | Based on number |
| Mandatory for filtering | Optional        |

---

## 🔹 Summary

* Used to limit number of rows returned
* Improves performance
* Syntax differs across DBMS
* Works best with ORDER BY
* Applied after filtering and sorting

---

## 🔹 Practice Questions (Exam-Oriented)

### Q1. What is the purpose of SELECT TOP / LIMIT?

**Answer:**
To restrict the number of rows returned by a query.

---

### Q2. Write a MySQL query to get first 10 records from `Students`.

```sql
SELECT *
FROM Students
LIMIT 10;
```

---

### Q3. How do you get top 3 highest salaries?

```sql
SELECT *
FROM Employees
ORDER BY Salary DESC
LIMIT 3;
```

---

### Q4. Does LIMIT affect table data?

**Answer:**
No, it only affects the result set.

---

### Q5. Which clause is executed last: WHERE or LIMIT?

**Answer:**
LIMIT is executed last.

---
