# 📘 Lecture 8: NULL Values in SQL

> This lecture explains what NULL means in SQL and how to correctly handle missing or unknown data.

---

## 🔹 What is a NULL Value?

* `NULL` means **no value / unknown value**
* It indicates **missing information**
* A NULL field is **not the same as**:

  * `0`
  * Empty string `''`
  * Space `' '`

📌 NULL represents **absence of data**, not a value.

---

## 🔹 When Do NULL Values Occur?

* Optional fields are left blank
* Data is not available at the time of insertion
* Partial data is inserted using `INSERT INTO`

Example:

```sql
INSERT INTO Students (Name, Age)
VALUES ('Rohit', NULL);
```

---

## 🔹 Why NULL is Important in SQL

* Affects filtering (`WHERE`)
* Affects calculations
* Needs special handling
* Common source of logical errors

---

## 🔹 Checking for NULL Values (Very Important ⭐)

### ❌ Incorrect Way

```sql
WHERE Address = NULL;
```

🚫 This **never works**

---

### ✅ Correct Way: IS NULL

```sql
SELECT *
FROM Customers
WHERE Address IS NULL;
```

➡ Returns rows where **Address has no value**

---

### ✅ Checking for Non-NULL Values

```sql
SELECT *
FROM Customers
WHERE Address IS NOT NULL;
```

➡ Returns rows where **Address contains a value**

---

## 🔹 Why `=` Does Not Work with NULL

* NULL means **unknown**
* Comparing unknown with anything is undefined
* SQL uses **IS NULL / IS NOT NULL** for this reason

---

## 🔹 NULL in Conditions (Important Concept ⭐)

* Any comparison with NULL results in **UNKNOWN**
* UNKNOWN conditions are treated as **false** in WHERE clause

---

## 🔹 NULL vs 0 vs Empty String

| Value | Meaning       |
| ----- | ------------- |
| NULL  | No value      |
| 0     | Numeric value |
| ''    | Empty text    |

📌 These are **not equal**

---

## 🔹 Common Mistakes (Exam Favorites ⭐)

* Using `=` to check NULL
* Assuming NULL = 0
* Forgetting NULL while filtering data
* Ignoring NULL in calculations

---

## 🔹 Summary

* NULL represents missing or unknown data
* NULL is different from zero or empty string
* NULL cannot be compared using `=`
* Use `IS NULL` and `IS NOT NULL`
* NULL values require special handling

---

## 🔹 Practice Questions (Exam-Oriented)

### Q1. What is a NULL value in SQL?

**Answer:**
A field with no value or unknown value.

---

### Q2. How do you find records where `Email` is NULL?

```sql
SELECT *
FROM Users
WHERE Email IS NULL;
```

---

### Q3. Can NULL be compared using `=`?

**Answer:**
No. NULL must be checked using `IS NULL`.

---

### Q4. Is NULL the same as zero?

**Answer:**
No. NULL represents absence of data, not a value.

---

### Q5. What operator is used to check non-NULL values?

**Answer:**
`IS NOT NULL`

---
