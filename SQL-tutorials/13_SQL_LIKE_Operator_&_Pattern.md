# 📘 Lecture 13: LIKE Operator & Pattern Matching

> This lecture explains how to search text data using patterns with the LIKE operator.

---

## 🔹 Purpose of LIKE Operator

* `LIKE` is used to **search for patterns** in text columns
* It works inside the `WHERE` clause
* Mostly used with **strings (VARCHAR / TEXT)**

📌 Used when exact match (`=`) is **not sufficient**

---

## 🔹 LIKE vs = (Important Difference ⭐)

| =            | LIKE            |
| ------------ | --------------- |
| Exact match  | Pattern match   |
| No wildcards | Uses wildcards  |
| Faster       | Slightly slower |
| Fixed value  | Flexible search |

---

## 🔹 Wildcards Used with LIKE

| Wildcard | Meaning                       |
| -------- | ----------------------------- |
| `%`      | Zero, one, or many characters |
| `_`      | Exactly one character         |

📌 Wildcards define **how the pattern behaves**

---

## 🔹 Starts With Pattern

```sql
SELECT *
FROM Customers
WHERE CustomerName LIKE 'A%';
```

➡ Names that **start with A**

---

## 🔹 Ends With Pattern

```sql
SELECT *
FROM Customers
WHERE CustomerName LIKE '%a';
```

➡ Names that **end with a**

---

## 🔹 Contains Pattern

```sql
SELECT *
FROM Customers
WHERE CustomerName LIKE '%or%';
```

➡ Names that **contain “or”**

---

## 🔹 Using `_` (Single Character Match)

```sql
SELECT *
FROM Customers
WHERE City LIKE 'L_nd__';
```

➡ Matches:

* L + any char + nd + any two chars
* Example: **London**

---

## 🔹 Combining `%` and `_`

```sql
SELECT *
FROM Customers
WHERE CustomerName LIKE 'A__%';
```

➡ Names starting with **A** and **at least 3 characters long**

---

## 🔹 Position-Based Matching

```sql
SELECT *
FROM Customers
WHERE CustomerName LIKE '_r%';
```

➡ Names with **r as the second character**

---

## 🔹 LIKE with AND / OR

```sql
SELECT *
FROM Customers
WHERE CustomerName LIKE 'A%' OR CustomerName LIKE 'B%';
```

➡ Names starting with **A or B**

---

## 🔹 LIKE Without Wildcards

```sql
WHERE Country LIKE 'Spain';
```

➡ Works same as `=`
📌 Rarely used, but valid

---

## 🔹 Case Sensitivity (Conceptual)

* Case sensitivity depends on:

  * Database
  * Collation settings
* MySQL is usually **case-insensitive**
* PostgreSQL is **case-sensitive**

---

## 🔹 Common Mistakes (Exam Favorites ⭐)

* Using LIKE on numeric columns
* Forgetting wildcards
* Confusing `_` with `%`
* Expecting LIKE to be fast on large tables
* Not understanding position of `%`

---

## 🔹 Summary

* LIKE is used for pattern matching
* `%` matches many characters
* `_` matches exactly one character
* Used inside WHERE clause
* Useful for text searches
* Slower than `=` due to pattern matching

---

## 🔹 Practice Questions (Exam-Oriented)

### Q1. What is the purpose of LIKE operator?

**Answer:**
To search for a specified pattern in a column.

---

### Q2. Write a query to find names starting with “S”.

```sql
SELECT *
FROM Students
WHERE Name LIKE 'S%';
```

---

### Q3. Write a query to find names containing “an”.

```sql
SELECT *
FROM Students
WHERE Name LIKE '%an%';
```

---

### Q4. What does `_` represent in LIKE?

**Answer:**
Exactly one character.

---

### Q5. Difference between `%` and `_`?

**Answer:**
`%` matches multiple characters, `_` matches a single character.

---
