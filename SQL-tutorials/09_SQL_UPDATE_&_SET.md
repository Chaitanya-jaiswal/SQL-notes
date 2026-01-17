# 📘 Lecture 9: UPDATE Statement

> This lecture explains how to modify existing records in a database table using the UPDATE statement.

---

## 🔹 Purpose of UPDATE

* `UPDATE` is used to **modify existing data**
* It changes **values inside rows**
* It does **not add new rows**

📌 Used when:

* Correcting wrong data
* Changing user details
* Updating status, price, marks, etc.

---

## 🔹 Basic Syntax

```sql
UPDATE table_name
SET column1 = value1, column2 = value2
WHERE condition;
```

### Meaning:

* `UPDATE` → table to be modified
* `SET` → new values
* `WHERE` → which rows to update

---

## 🔹 Updating a Single Record

```sql
UPDATE Customers
SET City = 'Frankfurt'
WHERE CustomerID = 1;
```

➡ Only **one row** is updated because of the `WHERE` condition.

📌 **Primary key is commonly used in WHERE** to target one record.

---

## 🔹 Updating Multiple Records

* `WHERE` decides **how many rows** are affected

```sql
UPDATE Customers
SET ContactName = 'Juan'
WHERE Country = 'Mexico';
```

➡ All customers **from Mexico** are updated.

---

## 🔹 Updating Multiple Columns

```sql
UPDATE Students
SET Age = 21, City = 'Delhi'
WHERE StudentID = 5;
```

📌 Multiple columns can be updated in **one query**.

---

## 🔹 UPDATE Without WHERE (Very Dangerous ⚠️)

```sql
UPDATE Customers
SET Country = 'India';
```

🚨 **All rows in the table will be updated**

📌 This is one of the **most important exam warnings**.

---

## 🔹 UPDATE with NULL Values

* Columns can be set to `NULL`

```sql
UPDATE Employees
SET Phone = NULL
WHERE EmployeeID = 10;
```

---

## 🔹 UPDATE vs INSERT (Quick Comparison)

| UPDATE                   | INSERT              |
| ------------------------ | ------------------- |
| Modifies existing rows   | Adds new rows       |
| Requires WHERE (usually) | Does not need WHERE |
| Data already exists      | Data is new         |

---

## 🔹 Common Mistakes (Exam Favorites ⭐)

* Forgetting WHERE clause
* Updating wrong rows
* Confusing UPDATE with INSERT
* Not checking affected rows
* Accidentally setting wrong values

---

## 🔹 Best Practices (Conceptual)

* Always test with `SELECT` before `UPDATE`
* Use `WHERE` carefully
* Update minimum required rows
* Avoid UPDATE without WHERE

---

## 🔹 Summary

* UPDATE modifies existing records
* SET defines new values
* WHERE selects rows to update
* Without WHERE → all rows are updated
* Multiple columns and rows can be updated

---

## 🔹 Practice Questions (Exam-Oriented)

### Q1. What is the purpose of UPDATE statement?

**Answer:**
To modify existing records in a table.

---

### Q2. Write a query to update salary of employee with ID 3.

```sql
UPDATE Employees
SET Salary = 50000
WHERE EmployeeID = 3;
```

---

### Q3. What happens if WHERE clause is omitted in UPDATE?

**Answer:**
All records in the table are updated.

---

### Q4. Can UPDATE modify multiple columns?

**Answer:**
Yes, multiple columns can be updated in one statement.

---

### Q5. Does UPDATE add new records?

**Answer:**
No, it only modifies existing records.

---