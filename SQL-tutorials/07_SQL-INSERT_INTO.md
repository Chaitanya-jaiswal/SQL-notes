# 📘 Lecture 7: INSERT INTO Statement

> This lecture explains how to add new records (rows) into a database table using SQL.

---

## 🔹 Purpose of INSERT INTO

* `INSERT INTO` is used to **add new data** to a table
* It increases the **number of rows**
* It does **not modify existing records**

📌 Used when storing:

* New users
* New orders
* New transactions
* New entries in any table

---

## 🔹 Two Ways to Use INSERT INTO

### 1️⃣ Insert with Column Names (Recommended ✅)

```sql
INSERT INTO table_name (column1, column2, column3)
VALUES (value1, value2, value3);
```

✔ Safer
✔ Clear
✔ Order of columns is controlled by the user

---

### 2️⃣ Insert Without Column Names

```sql
INSERT INTO table_name
VALUES (value1, value2, value3, ...);
```

⚠ Works **only if**:

* Values are provided for **all columns**
* Values follow **exact table column order**

📌 More error-prone → **not recommended** in real projects

---

## 🔹 Inserting Partial Data

* You can insert values into **only selected columns**
* Remaining columns:

  * Become `NULL`, or
  * Take default values

```sql
INSERT INTO Customers (CustomerName, City, Country)
VALUES ('Cardinal', 'Stavanger', 'Norway');
```

📌 Very common exam point

---

## 🔹 Auto-Increment Columns

* Auto-increment columns (like `ID`) are generated automatically
* Do **not** insert values manually unless required

```sql
-- ID is auto-generated
INSERT INTO Students (Name, Age)
VALUES ('Rahul', 21);
```

---

## 🔹 Inserting Multiple Rows

* Multiple records can be inserted in **one query**
* Saves time and improves performance

```sql
INSERT INTO Customers (CustomerName, City, Country)
VALUES
('A', 'Delhi', 'India'),
('B', 'Rome', 'Italy'),
('C', 'Berlin', 'Germany');
```

📌 Each row is separated by a **comma**

---

## 🔹 Data Type Rules (Important ⭐)

* **Text values** → single quotes `' '`
* **Numeric values** → no quotes
* **NULL** → written as `NULL` (without quotes)

```sql
INSERT INTO Users (Name, Age)
VALUES ('Amit', 22);
```

---

## 🔹 INSERT vs UPDATE (Quick Difference)

| INSERT INTO         | UPDATE                |
| ------------------- | --------------------- |
| Adds new row        | Modifies existing row |
| Increases row count | Row count unchanged   |
| Used for new data   | Used for corrections  |

---

## 🔹 Common Mistakes (Exam Favorites ⭐)

* Mismatch between columns and values
* Wrong order of values
* Missing quotes for text data
* Trying to insert into auto-increment column
* Forgetting commas between multiple rows

---

## 🔹 Summary

* INSERT INTO adds new records to a table
* Column names can be specified or omitted
* Partial column insertion is allowed
* Auto-increment values are generated automatically
* Multiple rows can be inserted in a single query

---

## 🔹 Practice Questions (Exam-Oriented)

### Q1. What is the purpose of INSERT INTO?

**Answer:**
To add new records into a database table.

---

### Q2. Write a query to insert a new student into a `Students` table.

```sql
INSERT INTO Students (Name, Age, City)
VALUES ('Riya', 20, 'Mumbai');
```

---

### Q3. Is it compulsory to specify column names in INSERT INTO?

**Answer:**
No, but it is recommended to avoid errors.

---

### Q4. What happens if values are not provided for some columns?

**Answer:**
They are set to `NULL` or default values.

---

### Q5. Can INSERT INTO add multiple rows?

**Answer:**
Yes, multiple rows can be inserted in a single statement.

---

### ✅ Next logical lectures:

* 📘 **Lecture 8: NULL Values**
* 📘 **Lecture 9: UPDATE Statement**
* 📘 **Lecture 10: DELETE Statement**

Just say **“Next lec”** 👍
Great 👍
Here are **📘 Lecture 7: INSERT INTO Statement** notes — **conceptual, exam-oriented**, and **only the important ideas**, not copied from W3Schools.

---

# 📘 Lecture 7: INSERT INTO Statement

> This lecture explains how to add new records (rows) into a database table using SQL.

---

## 🔹 Purpose of INSERT INTO

* `INSERT INTO` is used to **add new data** to a table
* It increases the **number of rows**
* It does **not modify existing records**

📌 Used when storing:

* New users
* New orders
* New transactions
* New entries in any table

---

## 🔹 Two Ways to Use INSERT INTO

### 1️⃣ Insert with Column Names (Recommended ✅)

```sql
INSERT INTO table_name (column1, column2, column3)
VALUES (value1, value2, value3);
```

✔ Safer
✔ Clear
✔ Order of columns is controlled by the user

---

### 2️⃣ Insert Without Column Names

```sql
INSERT INTO table_name
VALUES (value1, value2, value3, ...);
```

⚠ Works **only if**:

* Values are provided for **all columns**
* Values follow **exact table column order**

📌 More error-prone → **not recommended** in real projects

---

## 🔹 Inserting Partial Data

* You can insert values into **only selected columns**
* Remaining columns:

  * Become `NULL`, or
  * Take default values

```sql
INSERT INTO Customers (CustomerName, City, Country)
VALUES ('Cardinal', 'Stavanger', 'Norway');
```

📌 Very common exam point

---

## 🔹 Auto-Increment Columns

* Auto-increment columns (like `ID`) are generated automatically
* Do **not** insert values manually unless required

```sql
-- ID is auto-generated
INSERT INTO Students (Name, Age)
VALUES ('Rahul', 21);
```

---

## 🔹 Inserting Multiple Rows

* Multiple records can be inserted in **one query**
* Saves time and improves performance

```sql
INSERT INTO Customers (CustomerName, City, Country)
VALUES
('A', 'Delhi', 'India'),
('B', 'Rome', 'Italy'),
('C', 'Berlin', 'Germany');
```

📌 Each row is separated by a **comma**

---

## 🔹 Data Type Rules (Important ⭐)

* **Text values** → single quotes `' '`
* **Numeric values** → no quotes
* **NULL** → written as `NULL` (without quotes)

```sql
INSERT INTO Users (Name, Age)
VALUES ('Amit', 22);
```

---

## 🔹 INSERT vs UPDATE (Quick Difference)

| INSERT INTO         | UPDATE                |
| ------------------- | --------------------- |
| Adds new row        | Modifies existing row |
| Increases row count | Row count unchanged   |
| Used for new data   | Used for corrections  |

---

## 🔹 Common Mistakes (Exam Favorites ⭐)

* Mismatch between columns and values
* Wrong order of values
* Missing quotes for text data
* Trying to insert into auto-increment column
* Forgetting commas between multiple rows

---

## 🔹 Summary

* INSERT INTO adds new records to a table
* Column names can be specified or omitted
* Partial column insertion is allowed
* Auto-increment values are generated automatically
* Multiple rows can be inserted in a single query

---

## 🔹 Practice Questions (Exam-Oriented)

### Q1. What is the purpose of INSERT INTO?

**Answer:**
To add new records into a database table.

---

### Q2. Write a query to insert a new student into a `Students` table.

```sql
INSERT INTO Students (Name, Age, City)
VALUES ('Riya', 20, 'Mumbai');
```

---

### Q3. Is it compulsory to specify column names in INSERT INTO?

**Answer:**
No, but it is recommended to avoid errors.

---

### Q4. What happens if values are not provided for some columns?

**Answer:**
They are set to `NULL` or default values.

---

### Q5. Can INSERT INTO add multiple rows?

**Answer:**
Yes, multiple rows can be inserted in a single statement.

---