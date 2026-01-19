# 📘 Lecture 25: SQL NULL Functions

## 🔹 Why NULL Functions Are Needed

- `NULL` represents **missing or unknown data**
- Any arithmetic operation with `NULL` returns `NULL`
- NULL functions are used to **replace NULL with a default value**
- Very important for:
  - Calculations
  - Reports
  - Avoiding NULL results

---

## 🔹 Common NULL Handling Functions

Different databases use different functions, but the **goal is the same**:
➡ Replace `NULL` with a meaningful value.

---

## 🔹 IFNULL() – MySQL

```sql
IFNULL(expression, replacement)
````

* Returns `replacement` if expression is `NULL`
* Otherwise returns the expression

```sql
SELECT IFNULL(UnitsOnOrder, 0)
FROM Products;
```

---

## 🔹 ISNULL() – SQL Server

```sql
ISNULL(expression, replacement)
```

* Works same as IFNULL
* Used only in **SQL Server**

```sql
SELECT ISNULL(UnitsOnOrder, 0)
FROM Products;
```

---

## 🔹 COALESCE() – Standard SQL ⭐

```sql
COALESCE(value1, value2, value3, ...)
```

* Returns the **first non-NULL value**
* Supported by:

  * MySQL
  * SQL Server
  * Oracle
  * PostgreSQL
* **Most portable and exam-preferred**

```sql
SELECT COALESCE(UnitsOnOrder, 0)
FROM Products;
```

---

## 🔹 NVL() – Oracle

```sql
NVL(expression, replacement)
```

* Oracle equivalent of IFNULL / ISNULL

```sql
SELECT NVL(UnitsOnOrder, 0)
FROM Products;
```

---

## 🔹 NULL Functions in Calculations ⭐

Without NULL handling:

```sql
UnitPrice * (UnitsInStock + UnitsOnOrder)
```

➡ Result becomes `NULL` if `UnitsOnOrder` is NULL ❌

Correct approach:

```sql
UnitPrice * (UnitsInStock + COALESCE(UnitsOnOrder, 0))
```

➡ Calculation works correctly ✅

---

## 🔹 Comparison of NULL Functions (Exam Favorite ⭐)

| Function   | Database Support |
| ---------- | ---------------- |
| IFNULL()   | MySQL            |
| ISNULL()   | SQL Server       |
| NVL()      | Oracle           |
| COALESCE() | All major DBs    |

---

## 🔹 NULL Functions vs IS NULL

| IS NULL            | NULL Functions            |
| ------------------ | ------------------------- |
| Used for filtering | Used for replacing values |
| Returns TRUE/FALSE | Returns actual value      |
| Used in WHERE      | Used in SELECT            |

---

## 🔹 Common Mistakes (High Probability ⭐)

* Using `=` to compare NULL
* Forgetting NULL handling in calculations
* Using DB-specific functions in wrong DB
* Ignoring COALESCE (most portable)

---

## 🔹 Important Notes

* COALESCE can take **multiple values**
* First non-NULL value is returned
* NULL functions **do not modify data**
* Only affect query result

---

## 🔹 Summary

* NULL breaks calculations
* NULL functions replace missing values
* IFNULL → MySQL
* ISNULL → SQL Server
* NVL → Oracle
* COALESCE → works everywhere
* COALESCE is most recommended

---

## 🔹 Practice Questions (Exam-Oriented)

### Q1. Why are NULL functions used?

**Answer:**
To replace NULL values and avoid NULL results in calculations.

---

### Q2. Which function is supported by all major databases?

**Answer:**
`COALESCE()`

---

### Q3. Which function is used in SQL Server to replace NULL?

**Answer:**
`ISNULL()`

---

### Q4. Write a query to replace NULL stock values with 0.

```sql
SELECT COALESCE(UnitsInStock, 0)
FROM Products;
```

---

### Q5. Does COALESCE change table data?

**Answer:**
No, it only changes the query output.

---

```

---
