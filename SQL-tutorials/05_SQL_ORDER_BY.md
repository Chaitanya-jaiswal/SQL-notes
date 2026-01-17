# 📘 Lecture 5: ORDER BY Clause

> This lecture explains how to sort query results using the ORDER BY clause.

---

## 🔹 Purpose of ORDER BY

* `ORDER BY` is used to **sort the result set**
* Sorting can be:

  * **Ascending**
  * **Descending**
* It affects **only the output**, not the stored data

📌 Think of `ORDER BY` as arranging data **for better readability**.

---

## 🔹 Basic Syntax

```sql
SELECT column_name
FROM table_name
ORDER BY column_name;
```

### Example:

```sql
SELECT *
FROM Products
ORDER BY Price;
```

➡ Sorts products by **price in ascending order**.

---

## 🔹 Default Sorting Order

* By default, `ORDER BY` sorts data in **ascending order**
* Ascending means:

  * Numbers → smallest to largest
  * Text → A to Z

```sql
ORDER BY column_name;
```

is same as:

```sql
ORDER BY column_name ASC;
```

---

## 🔹 DESC (Descending Order)

* Used to sort data from **highest to lowest**
* Keyword: `DESC`

### Example:

```sql
SELECT *
FROM Products
ORDER BY Price DESC;
```

➡ Most expensive product appears first.

---

## 🔹 Sorting Text Data

* String values are sorted **alphabetically**
* Case sensitivity depends on database system (collation)

### Example:

```sql
SELECT *
FROM Products
ORDER BY ProductName;
```

---

## 🔹 ORDER BY with Multiple Columns

* Sorting happens **column by column**
* First column → primary sort
* Second column → secondary sort

### Example:

```sql
SELECT *
FROM Customers
ORDER BY Country, CustomerName;
```

➡ Sorted by:

1. Country
2. CustomerName (if country is same)

---

## 🔹 Mixing ASC and DESC

Different sorting directions can be applied to different columns.

```sql
SELECT *
FROM Customers
ORDER BY Country ASC, CustomerName DESC;
```

---

## 🔹 ORDER BY with WHERE (Very Common ⭐)

* `WHERE` filters rows
* `ORDER BY` sorts filtered results

```sql
SELECT *
FROM Customers
WHERE Country = 'India'
ORDER BY CustomerName;
```

📌 **Logical order (important for exams):**

1. FROM
2. WHERE
3. SELECT
4. ORDER BY

---

## 🔹 Common Mistakes (Exam Favorites ⭐)

* Writing `ORDER BY` before `WHERE`
* Forgetting `DESC` when reverse order is required
* Assuming ORDER BY changes table data ❌
* Using column names that are not selected (allowed but confusing)

---

## 🔹 ORDER BY vs WHERE (Quick Difference)

| WHERE                    | ORDER BY             |
| ------------------------ | -------------------- |
| Filters rows             | Sorts rows           |
| Limits data              | Arranges data        |
| Mandatory for conditions | Optional             |
| Executes before ORDER BY | Executes after WHERE |

---

## 🔹 Summary

* ORDER BY sorts query results
* Default order is ascending
* DESC is used for descending order
* Can sort by multiple columns
* Used after WHERE clause
* Does not modify table data

---

## 🔹 Practice Questions (Exam-Oriented)

### Q1. What is the use of ORDER BY clause?

**Answer:**
To sort the result set in ascending or descending order.

---

### Q2. Write a query to sort employees by salary in descending order.

```sql
SELECT *
FROM Employees
ORDER BY Salary DESC;
```

---

### Q3. Can ORDER BY be used with multiple columns?

**Answer:**
Yes, sorting is applied column by column.

---

### Q4. Does ORDER BY change the actual data in the table?

**Answer:**
No, it only affects the displayed result.

---

### Q5. Which clause is executed first: WHERE or ORDER BY?

**Answer:**
WHERE is executed before ORDER BY.

---