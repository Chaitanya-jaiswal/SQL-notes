# 📘 Lecture 17: SQL JOINs

---

## 🔹 Why SQL JOINs Are Needed
- Data in databases is stored in **multiple normalized tables**
- JOINs help **combine related data** from different tables
- Based on **common columns** (usually Primary Key ↔ Foreign Key)

Example:
- `Customers` table → customer details  
- `Orders` table → order details  
- JOIN → customer name + order date  

---

## 🔹 What is an SQL JOIN?
A **JOIN** is used to combine rows from two or more tables based on a **related column**.

```sql
SELECT column_name(s)
FROM table1
JOIN table2
ON table1.column = table2.column;
````

---

## 🔹 Types of SQL JOINs

| JOIN Type       | Description                                    |
| --------------- | ---------------------------------------------- |
| INNER JOIN      | Only matching rows from both tables            |
| LEFT JOIN       | All rows from left table + matching right rows |
| RIGHT JOIN      | All rows from right table + matching left rows |
| FULL OUTER JOIN | All rows from both tables                      |
| SELF JOIN       | Table joined with itself                       |

---

## 🔹 SQL JOINs – Visual Overview

![SQL JOIN Venn Diagram](images/joins-venn.png)

**Explanation:**

* **INNER JOIN** → Intersection only
* **LEFT JOIN** → Entire left table + match
* **RIGHT JOIN** → Entire right table + match
* **FULL JOIN** → All records from both tables

---

## 🔹 INNER JOIN

### 📌 Concept

* Returns **only rows that have matching values in both tables**
* Unmatched rows are excluded

### Syntax

```sql
SELECT column_name(s)
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

### Example

```sql
SELECT Products.ProductName, Categories.CategoryName
FROM Products
INNER JOIN Categories
ON Products.CategoryID = Categories.CategoryID;
```

### 📝 Notes

* `JOIN` and `INNER JOIN` mean the same
* Most commonly used JOIN

---

## 🔹 LEFT JOIN (LEFT OUTER JOIN)

### 📌 Concept

* Returns **all rows from the left table**
* Matching rows from the right table
* Non-matching right values → `NULL`

### Syntax

```sql
SELECT column_name(s)
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```

### Example

```sql
SELECT Customers.CustomerName, Orders.OrderID
FROM Customers
LEFT JOIN Orders
ON Customers.CustomerID = Orders.CustomerID;
```

### 📝 Notes

* Keeps all records from left table
* Used when **missing related data is important**

---

## 🔹 RIGHT JOIN (RIGHT OUTER JOIN)

### 📌 Concept

* Returns **all rows from the right table**
* Matching rows from the left table
* Non-matching left values → `NULL`

### Syntax

```sql
SELECT column_name(s)
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```

### 📝 Notes

* Less commonly used
* Can be rewritten as LEFT JOIN by swapping tables

---

## 🔹 FULL OUTER JOIN

### 📌 Concept

* Returns **all rows from both tables**
* Includes matching and non-matching rows
* Missing values appear as `NULL`

### Syntax

```sql
SELECT column_name(s)
FROM table1
FULL OUTER JOIN table2
ON table1.column = table2.column;
```

### Example

```sql
SELECT Customers.CustomerName, Orders.OrderID
FROM Customers
FULL OUTER JOIN Orders
ON Customers.CustomerID = Orders.CustomerID;
```

### 📝 Notes

* Can return **large result sets**
* Not supported in MySQL directly (needs UNION workaround)

---

## 🔹 SQL JOIN Behavior (Detailed – Exam Oriented)

![SQL JOIN Detailed Diagram](images/UI25E.jpg)

**Key Takeaways:**

* INNER JOIN → Only common rows
* LEFT JOIN → Left + common
* RIGHT JOIN → Right + common
* FULL JOIN → Everything

---

## 🔹 SELF JOIN

### 📌 Concept

* A table is joined **with itself**
* Uses **table aliases** to differentiate

### Syntax

```sql
SELECT column_name(s)
FROM table A, table B
WHERE condition;
```

### Example

```sql
SELECT A.CustomerName AS Customer1,
       B.CustomerName AS Customer2,
       A.City
FROM Customers A, Customers B
WHERE A.CustomerID <> B.CustomerID
AND A.City = B.City;
```

### 📝 Use Cases

* Comparing rows within the same table
* Finding duplicates or relationships inside one table

---

## 🔹 Quick Exam Summary

* JOIN combines data from multiple tables
* INNER JOIN → matching rows only
* LEFT JOIN → all left + matching right
* RIGHT JOIN → all right + matching left
* FULL JOIN → all records
* SELF JOIN → table joined with itself
* JOIN condition written using `ON`

---

## ✅ End of Lecture 17

```

---
