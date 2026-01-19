# 📘 Lecture 26: SQL Stored Procedures

## 🔹 What is a Stored Procedure?

- A **stored procedure** is a **saved SQL program** stored in the database
- It can be **executed repeatedly**
- Used to:
  - Reuse SQL code
  - Improve performance
  - Reduce network traffic
  - Apply business logic inside database

📌 Mostly used in **SQL Server**, but supported by other DBs with syntax changes.

---

## 🔹 Why Use Stored Procedures?

- Avoid writing the same query again and again
- Faster execution (precompiled)
- Better security (controlled access)
- Easy maintenance (change once, affect everywhere)

---

## 🔹 Basic Stored Procedure Syntax

```sql
CREATE PROCEDURE procedure_name
AS
sql_statement
GO;
````

---

## 🔹 Executing a Stored Procedure

```sql
EXEC procedure_name;
```

or

```sql
EXECUTE procedure_name;
```

---

## 🔹 Example: Simple Stored Procedure

```sql
CREATE PROCEDURE SelectAllCustomers
AS
SELECT * FROM Customers
GO;
```

Execute it:

```sql
EXEC SelectAllCustomers;
```

---

## 🔹 Stored Procedure with One Parameter ⭐

```sql
CREATE PROCEDURE GetCustomersByCity
    @City NVARCHAR(30)
AS
SELECT * FROM Customers
WHERE City = @City
GO;
```

Execute:

```sql
EXEC GetCustomersByCity @City = 'London';
```

📌 Parameters make procedures **dynamic**.

---

## 🔹 Stored Procedure with Multiple Parameters

```sql
CREATE PROCEDURE GetCustomersByCityAndPostal
    @City NVARCHAR(30),
    @PostalCode NVARCHAR(10)
AS
SELECT *
FROM Customers
WHERE City = @City AND PostalCode = @PostalCode
GO;
```

Execute:

```sql
EXEC GetCustomersByCityAndPostal
    @City = 'London',
    @PostalCode = 'WA1 1DP';
```

---

## 🔹 Key Concepts (Exam Important ⭐)

* Parameters start with `@`
* Data type must be specified
* `GO` marks end of procedure definition (SQL Server)
* Stored procedures can return result sets

---

## 🔹 Stored Procedure vs View ⭐

| Stored Procedure         | View               |
| ------------------------ | ------------------ |
| Accepts parameters       | No parameters      |
| Can contain logic        | Only SELECT        |
| Executed using EXEC      | Queried like table |
| Faster for complex logic | Simpler            |

---

## 🔹 Stored Procedure vs Function

| Stored Procedure           | Function                     |
| -------------------------- | ---------------------------- |
| Can return multiple values | Returns single value         |
| Can modify data            | Mostly used for calculations |
| Called using EXEC          | Used in SELECT               |

---

## 🔹 Common Mistakes (High Probability ⭐)

* Forgetting `GO`
* Missing parameter data types
* Confusing procedure with function
* Trying to use procedure inside SELECT
* Wrong parameter order during execution

---

## 🔹 Important Notes

* Stored procedures are **precompiled**
* Improve performance in large systems
* Can include:

  * SELECT
  * INSERT
  * UPDATE
  * DELETE
* Often used in enterprise applications

---

## 🔹 Summary

* Stored procedures store reusable SQL logic
* Created using CREATE PROCEDURE
* Executed using EXEC
* Can accept parameters
* Improve performance and security
* Widely used in SQL Server

---

## 🔹 Practice Questions (Exam-Oriented)

### Q1. What is the primary purpose of a stored procedure?

**Answer:**
To save reusable SQL code for repeated execution.

---

### Q2. How do you execute a stored procedure?

**Answer:**

```sql
EXEC procedure_name;
```

---

### Q3. Can stored procedures accept parameters?

**Answer:**
Yes, parameters allow dynamic behavior.

---

### Q4. Which symbol is used before parameter names?

**Answer:**
`@`

---

### Q5. Are stored procedures precompiled?

**Answer:**
Yes, which improves performance.

---

```

---