# 📘 Lecture 12: SQL Aggregate Functions

> This lecture explains aggregate functions, which perform calculations on multiple rows and return a single result.

---

## 🔹 What Are Aggregate Functions?

* Aggregate functions operate on **a set of rows**
* They return **one single value**
* Mostly used with:

  * `SELECT`
  * `WHERE`
  * `GROUP BY`

📌 Aggregate functions are used for **summary and analysis**, not detailed row data.

---

## 🔹 Common Aggregate Functions

| Function | Purpose           |
| -------- | ----------------- |
| MIN()    | Smallest value    |
| MAX()    | Largest value     |
| COUNT()  | Number of rows    |
| SUM()    | Total of values   |
| AVG()    | Average of values |

📌 Except `COUNT(*)`, aggregate functions **ignore NULL values**.

---

## 🔹 MIN() Function

### Concept

* Returns the **minimum value** in a column
* Works on numeric, date, and text values

```sql
SELECT MIN(Price)
FROM Products;
```

📌 Often used to find **lowest salary, price, score**, etc.

---

## 🔹 MAX() Function

### Concept

* Returns the **maximum value** in a column

```sql
SELECT MAX(Price)
FROM Products;
```

📌 Used for **highest salary, maximum marks**, etc.

---

## 🔹 COUNT() Function

### Concept

* Returns the **number of rows**
* Very common in exams

### Variations

#### 1️⃣ COUNT(*)

* Counts **all rows**
* Includes rows with NULL values

```sql
SELECT COUNT(*)
FROM Products;
```

#### 2️⃣ COUNT(column_name)

* Counts **non-NULL values only**

```sql
SELECT COUNT(ProductName)
FROM Products;
```

#### 3️⃣ COUNT(DISTINCT column)

* Counts **unique values**

```sql
SELECT COUNT(DISTINCT Country)
FROM Customers;
```

---

## 🔹 SUM() Function

### Concept

* Returns the **total sum** of a numeric column

```sql
SELECT SUM(Quantity)
FROM OrderDetails;
```

📌 Used in:

* Total sales
* Total marks
* Total quantity

---

## 🔹 SUM() with Expression

```sql
SELECT SUM(Price * Quantity)
FROM OrderDetails;
```

📌 Very important real-world use case (billing, revenue).

---

## 🔹 AVG() Function

### Concept

* Returns the **average value**
* NULL values are ignored

```sql
SELECT AVG(Price)
FROM Products;
```

📌 Used to find:

* Average marks
* Average salary
* Average price

---

## 🔹 Aggregate Functions with WHERE

* `WHERE` filters rows **before aggregation**

```sql
SELECT AVG(Price)
FROM Products
WHERE CategoryID = 1;
```

---

## 🔹 Aggregate Functions with GROUP BY (Preview ⭐)

* Used to apply aggregate functions **group-wise**
* Detailed lecture comes next

```sql
SELECT CategoryID, AVG(Price)
FROM Products
GROUP BY CategoryID;
```

📌 Without `GROUP BY`, aggregate functions work on **entire table**.

---

## 🔹 Alias with Aggregate Functions

* Improves readability
* Common in exams

```sql
SELECT AVG(Price) AS AveragePrice
FROM Products;
```

---

## 🔹 Important Rules (Exam Gold ⭐⭐⭐)

* Aggregate functions **cannot be used in WHERE**
* Use them in:

  * SELECT
  * HAVING (later topic)
* NULL values are ignored (except COUNT(*))

---

## 🔹 Common Mistakes (Very Important ⭐)

* Using aggregate functions in WHERE
* Confusing COUNT(*) and COUNT(column)
* Forgetting GROUP BY
* Expecting AVG to include NULL values

---

## 🔹 Summary

* Aggregate functions summarize data
* MIN and MAX find extreme values
* COUNT counts rows
* SUM totals numeric values
* AVG calculates mean
* Used heavily with GROUP BY
* Ignore NULL values (except COUNT*)

---

## 🔹 Practice Questions (Exam-Oriented)

### Q1. What is an aggregate function?

**Answer:**
A function that performs calculations on multiple rows and returns a single value.

---

### Q2. Write a query to find the highest salary.

```sql
SELECT MAX(Salary)
FROM Employees;
```

---

### Q3. Difference between COUNT(*) and COUNT(column)?

**Answer:**
COUNT(*) counts all rows, while COUNT(column) ignores NULL values.

---

### Q4. Write a query to find total sales.

```sql
SELECT SUM(Amount)
FROM Sales;
```

---

### Q5. Does AVG() include NULL values?

**Answer:**
No, NULL values are ignored.

---
