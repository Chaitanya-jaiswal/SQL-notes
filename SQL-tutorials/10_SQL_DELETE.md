# 📘 Lecture 10: DELETE Statement

> This lecture explains how to remove existing records from a database table using the DELETE statement.

---

## 🔹 Purpose of DELETE

* `DELETE` is used to **remove existing rows**
* It reduces the **number of records**
* Table structure **remains unchanged**

📌 Used when:

* Removing incorrect data
* Deleting old or unwanted records
* Cleaning datasets

---

## 🔹 Basic Syntax

```sql
DELETE FROM table_name
WHERE condition;
```

### Meaning:

* `DELETE FROM` → table to remove data from
* `WHERE` → specifies which rows to delete

---

## 🔹 Deleting a Single Record

```sql
DELETE FROM Customers
WHERE CustomerID = 1;
```

➡ Deletes **only one row** (usually identified by primary key).

---

## 🔹 Deleting Multiple Records

```sql
DELETE FROM Customers
WHERE Country = 'Mexico';
```

➡ Deletes **all customers from Mexico**.

📌 Number of deleted rows depends on `WHERE`.

---

## 🔹 DELETE Without WHERE (Very Dangerous ⚠️)

```sql
DELETE FROM Customers;
```

🚨 **Deletes ALL records from the table**

📌 Table still exists, but **no data remains**.

---

## 🔹 DELETE vs DROP (Very Important ⭐)

| DELETE                         | DROP                    |
| ------------------------------ | ----------------------- |
| Removes rows                   | Removes entire table    |
| Table structure remains        | Table structure deleted |
| Can use WHERE                  | Cannot use WHERE        |
| Reversible (with transactions) | Not reversible          |

---

## 🔹 DELETE vs TRUNCATE (Conceptual)

| DELETE              | TRUNCATE                 |
| ------------------- | ------------------------ |
| Row-by-row deletion | Deletes all rows at once |
| WHERE allowed       | WHERE not allowed        |
| Slower              | Faster                   |
| Transaction safe    | Not transaction safe     |

📌 TRUNCATE is covered later in DDL.

---

## 🔹 Best Practices (Exam + Real Use ⭐)

* Always check rows using `SELECT` before `DELETE`
* Use `WHERE` carefully
* Prefer deleting specific records
* Avoid DELETE without WHERE unless intentional

---

## 🔹 Common Mistakes (Exam Favorites ⭐)

* Forgetting WHERE clause
* Confusing DELETE with DROP
* Accidentally deleting all data
* Not backing up data

---

## 🔹 Summary

* DELETE removes records from a table
* WHERE controls which rows are deleted
* Without WHERE → all records are deleted
* DELETE does not remove table structure
* DROP removes the entire table

---

## 🔹 Practice Questions (Exam-Oriented)

### Q1. What is the purpose of DELETE statement?

**Answer:**
To remove existing records from a database table.

---

### Q2. Write a query to delete a student with ID 10.

```sql
DELETE FROM Students
WHERE StudentID = 10;
```

---

### Q3. What happens if WHERE is omitted in DELETE?

**Answer:**
All records in the table are deleted.

---

### Q4. Does DELETE remove the table structure?

**Answer:**
No, only the data is removed.

---

### Q5. Which command deletes the table completely?

**Answer:**
`DROP TABLE`

---