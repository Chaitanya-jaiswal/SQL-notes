# 📘 Lecture 2: SQL Syntax & Basic Structure

> This lecture focuses on how SQL queries are written, how tables are structured, and the fundamental rules every SQL user must follow.

---

## 🔹 SQL Statements (Core Idea)

* **SQL works through statements**
* Each statement performs **one specific action** on the database
* Statements are written using **keywords + identifiers**

### Example:

```sql
SELECT * FROM Customers;
```

This statement:

* Requests data (`SELECT`)
* From a table (`FROM Customers`)
* Returns all columns (`*`)

---

## 🔹 Basic Structure of an SQL Query

Most SQL queries follow this logical order:

```sql
SELECT column_name
FROM table_name
WHERE condition;
```

### Meaning:

* `SELECT` → What data you want
* `FROM` → Where the data is stored
* `WHERE` → Which rows to filter (optional)

📌 **Important:**
You write `SELECT` first, but internally SQL processes `FROM` first.

---

## 🔹 Database Tables (Concept)

* A **table** stores data in a structured format
* Data is organized using:

  * **Rows** → records
  * **Columns** → attributes

### Key Terms:

| Term   | Meaning                |
| ------ | ---------------------- |
| Table  | Data storage structure |
| Row    | Single record          |
| Column | Property/field         |

---

## 🔹 Identifiers in SQL

Identifiers are **names given by the user**:

* Table names
* Column names
* Database names

Rules:

* Should be meaningful
* Avoid SQL keywords as names
* Case does not matter in most DBMS

---

## 🔹 SQL Keywords

* Keywords have **predefined meaning**
* Examples:

  * SELECT
  * FROM
  * WHERE
  * INSERT
  * DELETE

📌 Keywords are **not case-sensitive**, but writing them in **UPPERCASE** improves readability and is industry standard.

---

## 🔹 Semicolon (`;`) in SQL

* Marks the **end of an SQL statement**
* Required when executing **multiple queries together**
* Recommended for consistency and clarity

```sql
SELECT * FROM Students;
```

---

## 🔹 Commonly Used SQL Commands (High Priority)

| Category           | Commands     |
| ------------------ | ------------ |
| Data Retrieval     | SELECT       |
| Data Insertion     | INSERT       |
| Data Modification  | UPDATE       |
| Data Removal       | DELETE       |
| Table Creation     | CREATE TABLE |
| Table Modification | ALTER TABLE  |
| Table Deletion     | DROP TABLE   |

📌 These commands are **most frequently asked in exams**.

---

## 🔹 Why SQL Syntax Matters

* Wrong syntax → query fails
* Correct syntax → faster and accurate results
* Helps maintain **data consistency**
* Makes queries **readable and reusable**

---

## 🔹 Common Beginner Mistakes (Exam Tip ⭐)

* Forgetting `FROM` clause
* Using wrong table or column names
* Missing semicolon
* Confusing `WHERE` with `HAVING`
* Writing conditions incorrectly

---

## 🔹 Summary

* SQL queries are written using a fixed structure
* Tables store data in rows and columns
* Keywords define the action of a query
* Identifiers name database objects
* Semicolon ends a SQL statement
* SELECT is the most important SQL command

---

## 🔹 Practice Questions (Exam-Oriented)

### Q1. What is SQL syntax?

**Answer:**
SQL syntax is the set of rules that define how SQL statements are written and executed.

---

### Q2. Write the general format of an SQL query.

**Answer:**

```sql
SELECT column_name
FROM table_name
WHERE condition;
```

---

### Q3. What are SQL keywords?

**Answer:**
SQL keywords are reserved words that have predefined meanings and are used to perform specific operations in SQL.

---

### Q4. Why are SQL keywords written in uppercase?

**Answer:**
To improve readability and maintain standard coding practices (not mandatory).
