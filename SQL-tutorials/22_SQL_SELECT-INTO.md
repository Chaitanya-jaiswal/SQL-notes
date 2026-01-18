# 📘 Lecture 22: SQL SELECT INTO Statement

## 🔹 Purpose of SELECT INTO

- `SELECT INTO` is used to **copy data from an existing table into a new table**
- The **new table is created automatically**
- Both **structure and data** are copied
- Commonly used for:
  - Backups
  - Temporary tables
  - Data migration

📌 **Important:** The destination table **must not already exist**.

---

## 🔹 Basic Syntax

### Copy all columns

```sql
SELECT *
INTO new_table
FROM old_table
WHERE condition;
````

### Copy specific columns

```sql
SELECT column1, column2
INTO new_table
FROM old_table
WHERE condition;
```

---

## 🔹 How SELECT INTO Works (Concept)

* Reads data from `FROM` table
* Creates a **new table**
* Copies:

  * Column names
  * Data types
  * Selected rows
* Does **not** copy:

  * Constraints
  * Indexes
  * Primary / Foreign keys

---

## 🔹 Creating a Backup Table

```sql
SELECT *
INTO CustomersBackup
FROM Customers;
```

➡ Creates a **full backup** of the `Customers` table.

---

## 🔹 Copying Data with Condition

```sql
SELECT *
INTO CustomersGermany
FROM Customers
WHERE Country = 'Germany';
```

➡ Copies **only German customers** into a new table.

---

## 🔹 Copying Selected Columns Only

```sql
SELECT CustomerName, ContactName
INTO CustomersBackup
FROM Customers;
```

➡ New table contains **only selected columns**.

---

## 🔹 SELECT INTO with JOIN

```sql
SELECT Customers.CustomerName, Orders.OrderID
INTO CustomerOrderBackup
FROM Customers
LEFT JOIN Orders
ON Customers.CustomerID = Orders.CustomerID;
```

📌 Used to **combine data from multiple tables** into one new table.

---

## 🔹 Creating an Empty Table Using SELECT INTO ⭐

```sql
SELECT *
INTO NewTable
FROM OldTable
WHERE 1 = 0;
```

➡ Creates table **structure only**, no data.

📌 Very important **exam trick**.

---

## 🔹 SELECT INTO vs INSERT INTO SELECT (Exam Favorite ⭐)

| SELECT INTO             | INSERT INTO SELECT      |
| ----------------------- | ----------------------- |
| Creates new table       | Uses existing table     |
| Table must not exist    | Table must exist        |
| Copies structure + data | Copies only data        |
| Used for backup         | Used for appending data |

---

## 🔹 Common Mistakes (High Probability ⭐)

* Using SELECT INTO when table already exists
* Expecting constraints to be copied
* Confusing SELECT INTO with INSERT INTO SELECT
* Forgetting WHERE condition (copies all rows)

---

## 🔹 Important Notes

* Not supported in the same way by all databases
* Mostly used in **SQL Server**
* MySQL prefers `CREATE TABLE AS SELECT`

---

## 🔹 Summary

* SELECT INTO creates a **new table**
* Copies data from an existing table
* WHERE clause controls rows copied
* Can be used with JOIN
* `WHERE 1 = 0` creates empty table
* Table must not exist before execution

---

## 🔹 Practice Questions (Exam-Oriented)

### Q1. What is the purpose of SELECT INTO?

**Answer:**
To copy data from one table into a new table.

---

### Q2. Does SELECT INTO create a table?

**Answer:**
Yes, it automatically creates a new table.

---

### Q3. Write a query to copy only Indian customers.

```sql
SELECT *
INTO CustomersIndia
FROM Customers
WHERE Country = 'India';
```

---

### Q4. How do you create an empty table using SELECT INTO?

```sql
SELECT *
INTO NewTable
FROM OldTable
WHERE 1 = 0;
```

---

### Q5. Which command should be used if the destination table already exists?

**Answer:**
`INSERT INTO SELECT`

---

```

---
