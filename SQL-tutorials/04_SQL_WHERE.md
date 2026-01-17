# 📘 Lecture 4: WHERE Clause

> This lecture explains how to filter records in SQL using conditions.

---

## 🔹 Purpose of WHERE Clause

* `WHERE` is used to **filter rows**
* It returns **only those records that satisfy a condition**
* Without `WHERE`, SQL operates on **all rows**

📌 Think of `WHERE` as applying a **condition or rule** to data.

---

## 🔹 Basic Syntax

```sql
SELECT column_name
FROM table_name
WHERE condition;
```

### Example:

```sql
SELECT *
FROM Customers
WHERE Country = 'Mexico';
```

➡ Returns only customers **from Mexico**.

---

## 🔹 WHERE with Different SQL Statements

`WHERE` is not limited to `SELECT`.

| Statement | Use of WHERE              |
| --------- | ------------------------- |
| SELECT    | Filter rows while reading |
| UPDATE    | Update selected rows only |
| DELETE    | Delete selected rows only |

📌 **Very important exam point**:
Without `WHERE`, `UPDATE` or `DELETE` affects **all records**.

---

## 🔹 Text vs Numeric Conditions

### Text Values

* Must be written inside **single quotes**

```sql
WHERE Country = 'India';
```

### Numeric Values

* **No quotes required**

```sql
WHERE CustomerID = 5;
```

---

## 🔹 Comparison Operators in WHERE

| Operator | Meaning               |
| -------- | --------------------- |
| =        | Equal                 |
| >        | Greater than          |
| <        | Less than             |
| >=       | Greater than or equal |
| <=       | Less than or equal    |
| <> or != | Not equal             |

### Example:

```sql
SELECT *
FROM Customers
WHERE CustomerID > 80;
```

---

## 🔹 Logical Meaning of WHERE

* Condition is evaluated **row by row**
* If condition is **true** → row is included
* If condition is **false** → row is ignored

---

## 🔹 WHERE vs SELECT DISTINCT (Concept Check ⭐)

* `WHERE` → filters **rows**
* `DISTINCT` → removes **duplicate values**
* Both can be used together in a query

---

## 🔹 Common Beginner Mistakes (Exam Favorite ⭐)

* Forgetting quotes for text values
* Using `=` instead of `LIKE` for patterns
* Forgetting WHERE in UPDATE / DELETE
* Writing invalid column names

---

## 🔹 Summary

* WHERE clause filters records
* Used with SELECT, UPDATE, DELETE
* Supports comparison operators
* Text values need quotes, numeric values don’t
* Prevents unwanted changes to entire tables

---

## 🔹 Practice Questions (Exam-Oriented)

### Q1. What is the purpose of the WHERE clause?

**Answer:**
To filter records that satisfy a specified condition.

---

### Q2. Write a query to select customers with ID greater than 10.

```sql
SELECT *
FROM Customers
WHERE CustomerID > 10;
```

---

### Q3. Can WHERE be used with DELETE?

**Answer:**
Yes. WHERE is used to specify which records should be deleted.

---

### Q4. What happens if WHERE is omitted in DELETE?

**Answer:**
All records in the table are deleted.

---
