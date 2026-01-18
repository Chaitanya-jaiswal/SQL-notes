# 📘 Lecture 23: SQL INSERT INTO SELECT Statement

## 🔹 Purpose of INSERT INTO SELECT

- `INSERT INTO SELECT` is used to **copy data from one table and insert it into another existing table**
- The **target table must already exist**
- Existing records in the target table **remain unchanged**
- Commonly used for:
  - Data migration
  - Merging tables
  - Appending records

📌 **Important difference:**  
This command **does NOT create a new table**.

---

## 🔹 Basic Syntax

### Copy all columns

```sql
INSERT INTO table2
SELECT *
FROM table1
WHERE condition;
````

---

### Copy selected columns

```sql
INSERT INTO table2 (column1, column2, column3)
SELECT column1, column2, column3
FROM table1
WHERE condition;
```

---

## 🔹 How INSERT INTO SELECT Works (Concept)

* Reads data from the **source table**
* Inserts matching rows into the **target table**
* Column **order and data types must match**
* Number of columns in `INSERT` and `SELECT` must be the same

---

## 🔹 Copying Data Between Tables

```sql
INSERT INTO Customers (CustomerName, City, Country)
SELECT SupplierName, City, Country
FROM Suppliers;
```

➡ Copies supplier data into customers table
➡ Unfilled columns become `NULL`

---

## 🔹 Copying All Columns

```sql
INSERT INTO Customers
(CustomerName, ContactName, Address, City, PostalCode, Country)
SELECT SupplierName, ContactName, Address, City, PostalCode, Country
FROM Suppliers;
```

➡ Copies **complete records**.

---

## 🔹 Copying Data with Condition

```sql
INSERT INTO Customers (CustomerName, City, Country)
SELECT SupplierName, City, Country
FROM Suppliers
WHERE Country = 'Germany';
```

➡ Inserts **only German suppliers**.

---

## 🔹 INSERT INTO SELECT vs SELECT INTO ⭐ (Exam Favorite)

| INSERT INTO SELECT      | SELECT INTO             |
| ----------------------- | ----------------------- |
| Target table must exist | Creates new table       |
| Inserts data only       | Copies structure + data |
| Used to append data     | Used for backup         |
| Common in MySQL         | Common in SQL Server    |

---

## 🔹 Data Type Rules (Important ⭐)

* Source and target columns must have:

  * Compatible data types
  * Same logical meaning
* Mismatch → query fails

---

## 🔹 Common Mistakes (High Probability ⭐)

* Target table does not exist
* Column count mismatch
* Wrong column order
* Data type incompatibility
* Forgetting WHERE clause (copies all rows)

---

## 🔹 Important Notes

* Does NOT delete data from source table
* Existing records in target table stay intact
* Can be combined with:

  * WHERE
  * JOIN (advanced use)

---

## 🔹 Summary

* INSERT INTO SELECT copies data between tables
* Target table must already exist
* Structure is NOT copied
* WHERE controls inserted rows
* Used for data migration and merging
* Different from SELECT INTO

---

## 🔹 Practice Questions (Exam-Oriented)

### Q1. What is the purpose of INSERT INTO SELECT?

**Answer:**
To copy data from one table and insert it into another existing table.

---

### Q2. Does INSERT INTO SELECT create a table?

**Answer:**
No, the table must already exist.

---

### Q3. Write a query to copy Indian customers into `CustomersBackup`.

```sql
INSERT INTO CustomersBackup
SELECT *
FROM Customers
WHERE Country = 'India';
```

---

### Q4. What happens to existing data in target table?

**Answer:**
It remains unchanged.

---

### Q5. Which statement is used to create a new table while copying data?

**Answer:**
`SELECT INTO`

---

```

---