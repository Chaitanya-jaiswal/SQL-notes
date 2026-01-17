# 📘 Lecture 1: Introduction to SQL

> This lecture introduces SQL, databases, and why SQL is essential for data management.

---

## 🔹 What is SQL?

**SQL (Structured Query Language)** is a standard language used to:
- Store data
- Retrieve data
- Manipulate data
- Control access to data

SQL is used with **Relational Database Management Systems (RDBMS)**.

---

## 🔹 What is a Database?

A **database** is an organized collection of data that allows:
- Easy access
- Efficient storage
- Fast retrieval
- Secure management

### Example:
A student database may store:
- Student ID
- Name
- Course
- Marks

---

## 🔹 What is DBMS?

**DBMS (Database Management System)** is software that:
- Manages databases
- Provides an interface between user and database
- Ensures data consistency and security

### Examples of DBMS:
- MySQL
- PostgreSQL
- Oracle
- SQL Server

---

## 🔹 Why Do We Need SQL?

Without SQL:
- Data handling would be slow
- Data would be duplicated
- Security would be difficult

With SQL:
- Data is stored in tables
- Queries are fast and structured
- Data integrity is maintained

---

## 🔹 Characteristics of SQL

- Declarative language (you specify *what* you want, not *how*)
- Easy to learn
- ANSI standard
- Works with large amounts of data
- Used by almost all RDBMS

---

## 🔹 SQL vs DBMS vs RDBMS

| Term | Description |
|----|----|
| SQL | Language to interact with databases |
| DBMS | Software to manage databases |
| RDBMS | DBMS based on relational model (tables) |

---

## 🔹 What is RDBMS?

**RDBMS (Relational DBMS)** stores data in:
- Tables (relations)
- Rows (records)
- Columns (attributes)

Each table has:
- A **primary key**
- Defined relationships with other tables

---

## 🔹 Types of SQL Commands

### 1️⃣ DDL – Data Definition Language
Used to define database structure.
- CREATE
- ALTER
- DROP
- TRUNCATE

---

### 2️⃣ DML – Data Manipulation Language
Used to manipulate data.
- INSERT
- UPDATE
- DELETE

---

### 3️⃣ DQL – Data Query Language
Used to retrieve data.
- SELECT

---

### 4️⃣ DCL – Data Control Language
Used for permissions.
- GRANT
- REVOKE

---

### 5️⃣ TCL – Transaction Control Language
Used to manage transactions.
- COMMIT
- ROLLBACK
- SAVEPOINT

---

## 🔹 Where SQL is Used?

- Web applications
- Banking systems
- E-commerce platforms
- Data analytics
- Machine learning pipelines

---

## 🔹 Common SQL Terminology

| Term | Meaning |
|----|----|
| Table | Collection of rows and columns |
| Row | Single record |
| Column | Attribute |
| Primary Key | Unique identifier |
| Query | SQL command |

---

## 🔹 Summary

- SQL is used to communicate with databases
- DBMS manages data efficiently
- RDBMS stores data in table format
- SQL commands are categorized into 5 types

---

## 🔹 Practice Questions with Answers

### Q1. What is SQL?
**Answer:**  
SQL (Structured Query Language) is a standard language used to store, retrieve, manipulate, and manage data in relational databases.

---

### Q2. Difference between DBMS and RDBMS?

| DBMS | RDBMS |
|----|----|
| Stores data as files | Stores data in tables |
| No relationships | Supports relationships |
| No primary key | Uses primary keys |
| Less secure | More secure |

---

### Q3. List types of SQL commands with examples.

| Type | Purpose | Example |
|----|----|----|
| DDL | Define structure | CREATE TABLE |
| DML | Modify data | INSERT |
| DQL | Retrieve data | SELECT |
| DCL | Access control | GRANT |
| TCL | Transactions | COMMIT |

---

### Q4. Why is SQL called a declarative language?
**Answer:**  
SQL is called a declarative language because the user specifies **what result is required**, not **how the database should execute the query**.

---
