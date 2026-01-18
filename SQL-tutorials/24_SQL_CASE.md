# 📘 Lecture 24: SQL CASE Expression

## 🔹 Purpose of CASE Expression

- `CASE` is used to **apply conditional logic in SQL**
- Works like **if–else / switch-case**
- Returns a **value based on conditions**
- Used inside:
  - SELECT
  - ORDER BY
  - UPDATE
  - WHERE (limited cases)

📌 CASE **does not change data**, it only changes query output.

---

## 🔹 Basic CASE Syntax

```sql
CASE
    WHEN condition1 THEN result1
    WHEN condition2 THEN result2
    ELSE result
END
````

* Conditions are checked **top to bottom**
* First TRUE condition is executed
* If no condition matches:

  * ELSE value is returned
  * If ELSE is missing → returns `NULL`

---

## 🔹 CASE in SELECT Statement

```sql
SELECT OrderID, Quantity,
CASE
    WHEN Quantity > 30 THEN 'High'
    WHEN Quantity = 30 THEN 'Medium'
    ELSE 'Low'
END AS QuantityLevel
FROM OrderDetails;
```

➡ Creates a **derived column** based on conditions.

---

## 🔹 CASE with Alias ⭐

* CASE results should usually be given an alias
* Makes output readable and exam-friendly

```sql
CASE
    WHEN marks >= 40 THEN 'Pass'
    ELSE 'Fail'
END AS Result
```

---

## 🔹 CASE in ORDER BY (Important ⭐)

```sql
SELECT CustomerName, City, Country
FROM Customers
ORDER BY
CASE
    WHEN City IS NULL THEN Country
    ELSE City
END;
```

➡ Sorts by **City**, but uses **Country** when City is NULL.

---

## 🔹 Simple CASE vs Searched CASE

### 1️⃣ Searched CASE (Most Common)

```sql
CASE
    WHEN condition THEN result
END
```

### 2️⃣ Simple CASE

```sql
CASE column
    WHEN value1 THEN result1
    WHEN value2 THEN result2
END
```

📌 Exams usually focus on **searched CASE**.

---

## 🔹 CASE vs WHERE (Concept Check ⭐)

| CASE                      | WHERE                 |
| ------------------------- | --------------------- |
| Returns conditional value | Filters rows          |
| Used in SELECT / ORDER BY | Used to restrict rows |
| Does not remove rows      | Removes rows          |

---

## 🔹 Common Mistakes (High Probability ⭐)

* Forgetting `END`
* Missing alias
* Wrong condition order
* Expecting CASE to filter rows
* Forgetting ELSE → NULL values appear

---

## 🔹 Important Notes

* CASE stops evaluating after first TRUE condition
* ELSE is optional but recommended
* Can be nested (not recommended in exams)
* Improves readability over complex IF logic

---

## 🔹 Summary

* CASE applies conditional logic in SQL
* Returns a value based on conditions
* Works like if–else
* Used in SELECT and ORDER BY
* ELSE handles unmatched cases
* Does not modify table data

---

## 🔹 Practice Questions (Exam-Oriented)

### Q1. What is the purpose of CASE expression?

**Answer:**
To return a value based on conditional logic.

---

### Q2. What happens if no CASE condition matches and ELSE is missing?

**Answer:**
NULL is returned.

---

### Q3. Write a CASE to label marks as Pass/Fail.

```sql
CASE
    WHEN Marks >= 40 THEN 'Pass'
    ELSE 'Fail'
END
```

---

### Q4. Can CASE be used in ORDER BY?

**Answer:**
Yes, to apply conditional sorting.

---

### Q5. Does CASE filter rows from a table?

**Answer:**
No, it only affects the output value.

---

```

---
