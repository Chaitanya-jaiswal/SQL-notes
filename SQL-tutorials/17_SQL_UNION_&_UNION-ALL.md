# 📘 Lecture 17: SQL UNION & UNION ALL

---

## 🔹 Why UNION is Needed
- Sometimes data is stored in **different tables with the same structure**
- JOIN combines **columns**
- UNION combines **rows**
- Used when you want to **merge result sets vertically**

---

## 🔹 What is SQL UNION?

**UNION** combines the result of **two or more SELECT queries** into a single result set.

### Key Properties
- Removes **duplicate rows automatically**
- Works only with `SELECT`
- Result columns are taken from the **first SELECT**

---

## 🔹 Rules for Using UNION (Very Important)

To use UNION:
1. Same **number of columns**
2. Similar **data types**
3. Same **column order**

❌ Violating any rule → SQL error

---

## 🔹 UNION Syntax

```sql
SELECT column_name(s)
FROM table1
UNION
SELECT column_name(s)
FROM table2;
````

---

## 🔹 Basic UNION Example

```sql
SELECT City FROM Customers
UNION
SELECT City FROM Suppliers;
```

### Result

* Cities from **both tables**
* **Duplicate cities appear only once**

---

## 🔹 UNION with ORDER BY

```sql
SELECT City FROM Customers
UNION
SELECT City FROM Suppliers
ORDER BY City;
```

📌 `ORDER BY` applies to the **final combined result**, not individual queries.

---

## 🔹 UNION with WHERE Clause

```sql
SELECT City, Country
FROM Customers
WHERE Country = 'Germany'
UNION
SELECT City, Country
FROM Suppliers
WHERE Country = 'Germany';
```

### Notes

* Each `SELECT` has its **own WHERE**
* Filtering happens **before union**

---

## 🔹 UNION with Aliases (Important for Exams)

```sql
SELECT 'Customer' AS Type, ContactName, City, Country
FROM Customers
UNION
SELECT 'Supplier', ContactName, City, Country
FROM Suppliers;
```

### Why this is useful?

* Adds a **label column**
* Helps identify data source
* Alias exists **only during query execution**

---

## 🔹 What is SQL UNION ALL?

**UNION ALL** works like UNION, but:

* **Does NOT remove duplicates**
* Faster execution
* Keeps **all rows**

---

## 🔹 UNION ALL Syntax

```sql
SELECT column_name(s)
FROM table1
UNION ALL
SELECT column_name(s)
FROM table2;
```

---

## 🔹 UNION ALL Example

```sql
SELECT City FROM Customers
UNION ALL
SELECT City FROM Suppliers;
```

### Result

* Cities from both tables
* **Duplicate cities are preserved**

---

## 🔹 UNION ALL with WHERE

```sql
SELECT City, Country
FROM Customers
WHERE Country = 'Germany'
UNION ALL
SELECT City, Country
FROM Suppliers
WHERE Country = 'Germany';
```

---

## 🔹 UNION vs UNION ALL (High-Weightage)

| Feature            | UNION      | UNION ALL |
| ------------------ | ---------- | --------- |
| Removes duplicates | ✅ Yes      | ❌ No      |
| Performance        | Slower     | Faster    |
| Result size        | Smaller    | Larger    |
| Use case           | Clean data | Raw data  |

---

## 🔹 Common Mistakes to Avoid

❌ Different number of columns
❌ Different column order
❌ ORDER BY inside individual SELECT
❌ Confusing JOIN with UNION

---

## 🔹 JOIN vs UNION (Quick Revision)

| JOIN              | UNION              |
| ----------------- | ------------------ |
| Combines columns  | Combines rows      |
| Requires relation | No relation needed |
| Horizontal merge  | Vertical merge     |

---

## 🔹 Exam-Oriented Summary (Lecture 17)

* UNION merges result sets
* UNION removes duplicates
* UNION ALL keeps duplicates
* ORDER BY applies to final result
* WHERE applies to each SELECT
* Alias useful for labeling rows

---

## ✅ End of Lecture 17

```

---
