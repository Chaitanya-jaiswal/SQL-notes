# 📘 Lecture 15: SQL IN & BETWEEN Operators

> This lecture covers **set-based filtering** and **range-based filtering** in SQL using `IN` and `BETWEEN`.

---

## 🔹 SQL IN Operator

### ✅ What is `IN`?

* Used to **match a column against multiple values**
* Acts as a **shorter version of multiple OR conditions**
* Makes queries **cleaner and readable**

---

### 🔹 Syntax

```sql
SELECT columns
FROM table
WHERE column IN (value1, value2, value3);
```

---

### 🔹 Example

```sql
SELECT *
FROM Customers
WHERE Country IN ('Germany', 'France', 'UK');
```

➡ Returns customers from **any one** of the listed countries

---

### 🔹 IN vs OR (Concept)

```sql
-- Using OR
WHERE Country = 'Germany' OR Country = 'France' OR Country = 'UK';

-- Using IN (preferred)
WHERE Country IN ('Germany', 'France', 'UK');
```

📌 **IN is cleaner and recommended**

---

### 🔹 NOT IN

Used to **exclude** multiple values.

```sql
SELECT *
FROM Customers
WHERE Country NOT IN ('Germany', 'France', 'UK');
```

---

### 🔹 IN with Subquery (IMPORTANT ⭐)

```sql
SELECT *
FROM Customers
WHERE CustomerID IN (
    SELECT CustomerID FROM Orders
);
```

➡ Customers **who have placed orders**

---

### 🔹 NOT IN with Subquery

```sql
SELECT *
FROM Customers
WHERE CustomerID NOT IN (
    SELECT CustomerID FROM Orders
);
```

➡ Customers **who have NOT placed orders**

---

### ⚠️ IN + NULL (Exam Trap)

* `NOT IN` fails if subquery returns `NULL`
* Prefer `NOT EXISTS` (later topic)

---

## 🔹 SQL BETWEEN Operator

### ✅ What is `BETWEEN`?

* Used to select values **within a range**
* Works with:

  * Numbers
  * Dates
  * Text (alphabetical)
* **Inclusive** → start and end values included

---

### 🔹 Syntax

```sql
SELECT columns
FROM table
WHERE column BETWEEN value1 AND value2;
```

---

### 🔹 Numeric Example

```sql
SELECT *
FROM Products
WHERE Price BETWEEN 10 AND 20;
```

➡ Includes **10 and 20**

---

### 🔹 NOT BETWEEN

```sql
SELECT *
FROM Products
WHERE Price NOT BETWEEN 10 AND 20;
```

---

### 🔹 BETWEEN with AND / IN

```sql
SELECT *
FROM Products
WHERE Price BETWEEN 10 AND 20
AND CategoryID IN (1, 2, 3);
```

---

### 🔹 BETWEEN with Text (Alphabetical)

```sql
SELECT *
FROM Products
WHERE ProductName BETWEEN 'Apple' AND 'Mango';
```

📌 Based on **dictionary order**

---

### 🔹 BETWEEN with Dates (VERY IMPORTANT ⭐)

```sql
SELECT *
FROM Orders
WHERE OrderDate BETWEEN '2023-01-01' AND '2023-01-31';
```

📌 Date format depends on DB, but logic is same

---

## 🔹 IN vs BETWEEN (Comparison)

| Feature             | IN              | BETWEEN          |
| ------------------- | --------------- | ---------------- |
| Purpose             | Multiple values | Range of values  |
| Uses OR logic       | ✅               | ❌                |
| Range-based         | ❌               | ✅                |
| Works with subquery | ✅               | ❌                |
| Inclusive           | Depends         | Always inclusive |

---

## 🔹 Common Mistakes (Exam Traps ⚠️)

* Writing `BETWEEN 20 AND 10` (wrong order)
* Assuming BETWEEN is exclusive
* Using IN for ranges
* Forgetting quotes for text/date
* Using NOT IN with NULL values

---

## 🔹 Summary

* `IN` → multiple specific values
* `NOT IN` → exclusion
* `BETWEEN` → inclusive range
* Works with numbers, text, dates
* Improves readability & performance

---

## 🔹 Practice Questions

### Q1. What does `IN` replace?

**Answer:** Multiple `OR` conditions

---

### Q2. Is `BETWEEN` inclusive?

**Answer:** Yes (includes both limits)

---

### Q3. Find employees with ID 2, 4, or 6

```sql
SELECT *
FROM Employees
WHERE EmpID IN (2, 4, 6);
```

---

### Q4. Find products priced between 100 and 500

```sql
SELECT *
FROM Products
WHERE Price BETWEEN 100 AND 500;
```

---

### Q5. Which is better for range queries?

**Answer:** `BETWEEN`

---