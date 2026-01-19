# 📘 Lecture 27: SQL Comments

## 🔹 Purpose of SQL Comments

- Comments are used to **explain SQL code**
- They can also **disable (ignore) SQL statements**
- Comments are **not executed** by the database
- Useful for:
  - Code readability
  - Debugging
  - Temporarily disabling queries

📌 Comments do **not affect query results**.

---

## 🔹 Types of SQL Comments

SQL supports **two types of comments**:

1. Single-line comments  
2. Multi-line comments

---

## 🔹 Single-Line Comments (`--`)

- Starts with `--`
- Everything after `--` on the same line is ignored

### Example: Explanation

```sql
-- Select all customers
SELECT * FROM Customers;
````

---

### Example: Ignoring part of a line

```sql
SELECT * FROM Customers -- WHERE City = 'Berlin';
```

➡ `WHERE` clause is ignored.

---

### Example: Ignoring a full statement

```sql
-- SELECT * FROM Customers;
SELECT * FROM Products;
```

---

## 🔹 Multi-Line Comments (`/* */`)

* Starts with `/*` and ends with `*/`
* Can span **multiple lines**
* Used to comment large blocks of code

---

### Example: Multi-line explanation

```sql
/* Select all records
   from the Customers table */
SELECT * FROM Customers;
```

---

### Example: Ignoring multiple statements

```sql
/* SELECT * FROM Customers;
   SELECT * FROM Orders;
   SELECT * FROM Products; */
SELECT * FROM Suppliers;
```

---

## 🔹 Commenting Part of a Statement ⭐

```sql
SELECT CustomerName, /* City, */ Country
FROM Customers;
```

➡ Only `CustomerName` and `Country` are selected.

---

## 🔹 Comments Inside Conditions (Important ⭐)

```sql
SELECT *
FROM Customers
WHERE Country = 'USA'
AND (
    CustomerName LIKE 'L%'
    /* OR CustomerName LIKE 'R%' */
    OR CustomerName LIKE 'W%'
);
```

➡ Commented conditions are ignored.

---

## 🔹 SQL Comments Support

* Supported by:

  * MySQL
  * SQL Server
  * Oracle
  * PostgreSQL
* ❌ Not supported in **MS Access**

---

## 🔹 Common Mistakes (Exam Favorite ⭐)

* Forgetting to close `*/`
* Using `--` in MS Access
* Expecting comments to execute
* Using comments inside string literals

---

## 🔹 Best Practices

* Use comments to explain **complex logic**
* Avoid excessive commenting
* Keep comments short and meaningful
* Use multi-line comments for disabling code blocks

---

## 🔹 Summary

* SQL comments explain or disable code
* Single-line comments use `--`
* Multi-line comments use `/* */`
* Comments are ignored during execution
* Useful for debugging and documentation

---

## 🔹 Practice Questions (Exam-Oriented)

### Q1. What is the primary purpose of comments in SQL?

**Answer:**
To explain SQL code or prevent execution of statements.

---

### Q2. Which symbol is used for single-line comments?

**Answer:**
`--`

---

### Q3. How do you comment multiple lines in SQL?

**Answer:**
Using `/* ... */`

---

### Q4. Are SQL comments executed?

**Answer:**
No, they are ignored by the database.

---

### Q5. Are SQL comments supported in MS Access?

**Answer:**
No.

---

```

---
