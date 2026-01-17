# 📘 Lecture 3: SELECT & SELECT DISTINCT Statements

> This lecture explains how to retrieve data from tables using the SELECT statement and how to remove duplicate values using SELECT DISTINCT.

---

## 🔹 SELECT Statement (Core Concept)

* `SELECT` is used to **retrieve data** from a database table
* It does **not modify data**
* It is the **most frequently used SQL command**

📌 Think of `SELECT` as **asking questions to the database**

---

## 🔹 Basic SELECT Syntax

```sql
SELECT column_name
FROM table_name;
```

### Example:

```sql
SELECT CustomerName, City
FROM Customers;
```

This query:

* Retrieves only **specific columns**
* Does not return unnecessary data
* Improves readability and performance

---

## 🔹 Selecting All Columns

To retrieve **every column** from a table:

```sql
SELECT *
FROM table_name;
```

📌 Use `*` carefully:

* Useful for learning and testing
* Not recommended in real projects due to performance and clarity issues

---

## 🔹 Why SELECT is Important

* Used in **data analysis**
* Used in **reports**
* Used in **applications (backend queries)**
* Foundation for advanced topics:

  * WHERE
  * JOIN
  * GROUP BY
  * HAVING

---

## 🔹 Duplicate Data Problem

* Tables often contain **repeated values**
* Example:

  * Many customers from the same country
* Sometimes we need:

  * **Only unique values**
  * **Summary-level data**

This is where `DISTINCT` is used.

---

## 🔹 SELECT DISTINCT Statement

* `DISTINCT` removes **duplicate values**
* Returns only **unique records**
* Works on **one or more columns**

### Syntax:

```sql
SELECT DISTINCT column_name
FROM table_name;
```

---

## 🔹 Example: SELECT vs SELECT DISTINCT

```sql
SELECT Country
FROM Customers;
```

➡ Returns **all countries**, including duplicates

```sql
SELECT DISTINCT Country
FROM Customers;
```

➡ Returns **each country only once**

📌 DISTINCT is applied **after data is selected**, before results are shown.

---

## 🔹 DISTINCT with Multiple Columns

```sql
SELECT DISTINCT City, Country
FROM Customers;
```

* Uniqueness is checked on **combined column values**
* Two rows are considered duplicates only if **all selected columns match**

---

## 🔹 SELECT DISTINCT with COUNT (Concept Only)

* Used to count **unique values**
* Very common in exams

```sql
SELECT COUNT(DISTINCT Country)
FROM Customers;
```

📌 This counts **how many different countries exist**, not total rows.

---

## 🔹 Common Mistakes (Very Important ⭐)

* Thinking `DISTINCT` removes duplicate rows from the table ❌
  → It only affects the **result**, not the data
* Using `DISTINCT` unnecessarily (performance impact)
* Confusing `DISTINCT` with `GROUP BY`

---

## 🔹 SELECT vs SELECT DISTINCT (Comparison)

| SELECT                 | SELECT DISTINCT            |
| ---------------------- | -------------------------- |
| Returns all values     | Returns only unique values |
| Allows duplicates      | Removes duplicates         |
| Faster                 | Slightly slower            |
| Used for detailed data | Used for summary data      |

---

## 🔹 Summary

* `SELECT` retrieves data from tables
* `SELECT *` retrieves all columns
* `SELECT DISTINCT` removes duplicate values
* DISTINCT works on selected columns
* COUNT(DISTINCT) is used to count unique values
* SELECT is the base of all SQL queries

---

## 🔹 Practice Questions (Exam-Oriented)

### Q1. What is the purpose of the SELECT statement?

**Answer:**
To retrieve data from one or more tables in a database.

---

### Q2. How do you select all columns from a table named `Students`?

**Answer:**

```sql
SELECT * FROM Students;
```

---

### Q3. What is the use of DISTINCT in SQL?

**Answer:**
DISTINCT is used to eliminate duplicate values from the query result.

---

### Q4. Write a query to display unique cities from a table `Customers`.

**Answer:**

```sql
SELECT DISTINCT City
FROM Customers;
```

---

### Q5. Does SELECT DISTINCT modify the table data?

**Answer:**
No. It only affects the query result, not the actual data.

---
