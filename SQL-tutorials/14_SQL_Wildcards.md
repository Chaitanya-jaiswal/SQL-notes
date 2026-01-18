# 📘 Lecture 14: SQL Wildcards

> This lecture focuses on **pattern matching symbols** used with the `LIKE` operator to search text data flexibly.

---

## 🔹 What are Wildcards?

* Wildcards are **special characters**
* Used **only with `LIKE`**
* Help match **partial or flexible text patterns**
* Mostly applied on **string columns**

---

## 🔹 Core Wildcards (MOST IMPORTANT ⭐)

| Wildcard | Meaning                             |
| -------- | ----------------------------------- |
| `%`      | Matches **zero or more characters** |
| `_`      | Matches **exactly one character**   |

📌 These two are **universal** (work in MySQL, PostgreSQL, SQL Server, Oracle)

---

## 🔹 `%` Wildcard (Multiple Characters)

### Starts with

```sql
WHERE Name LIKE 'A%';
```

➡ Starts with **A**

---

### Ends with

```sql
WHERE Name LIKE '%a';
```

➡ Ends with **a**

---

### Contains

```sql
WHERE Name LIKE '%or%';
```

➡ Contains **or** anywhere

---

### Matches Everything

```sql
WHERE Name LIKE '%';
```

➡ Matches **all rows**

---

## 🔹 `_` Wildcard (Single Character)

```sql
WHERE City LIKE '_ondon';
```

➡ Matches **London**

---

```sql
WHERE City LIKE 'L___on';
```

➡ L + 3 chars + on

---

📌 Each `_` = **exactly one character**

---

## 🔹 Combining `%` and `_`

```sql
WHERE Name LIKE 'A__%';
```

➡ Starts with **A**, minimum **3 characters**

---

```sql
WHERE Name LIKE '_r%';
```

➡ Second character must be **r**

---

## 🔹 LIKE Without Wildcards

```sql
WHERE Country LIKE 'Spain';
```

📌 Behaves same as `=`
📌 Rarely useful, but valid

---

## 🔹 Database-Specific Wildcards (LOW PRIORITY ❗)

| Symbol   | Meaning            | Support    |
| -------- | ------------------ | ---------- |
| `[abc]`  | Any one of a, b, c | SQL Server |
| `[a-f]`  | Range a–f          | SQL Server |
| `[^abc]` | Not a, b, c        | SQL Server |
| `{}`     | Escaped char       | Oracle     |
| `*`      | Multiple chars     | MS Access  |

📌 **NOT supported in MySQL & PostgreSQL**

👉 Exams usually **ignore these** or ask theory only

---

## 🔹 Wildcards vs Regular Expressions (Concept)

| Wildcards      | Regex            |
| -------------- | ---------------- |
| Simple         | Powerful         |
| Easy           | Complex          |
| Used with LIKE | Used with REGEXP |
| Basic pattern  | Advanced pattern |

---

## 🔹 Performance Note (Exam Tip ⭐)

* `LIKE '%abc%'` → **slow**
* Indexes **not used** when pattern starts with `%`
* Prefer exact matches when possible

---

## 🔹 Common Mistakes (Exam Traps ⚠️)

* Confusing `%` and `_`
* Using LIKE on numeric columns
* Forgetting quotes `' '`
* Assuming LIKE is case-sensitive everywhere
* Expecting indexes to work with `%` at start

---

## 🔹 Summary

* Wildcards help match patterns
* `%` → many characters
* `_` → one character
* Used only with `LIKE`
* Database support varies
* Important for text searching

---

## 🔹 Practice Questions

### Q1. What does `%` represent?

**Answer:** Zero or more characters

---

### Q2. Write query to find names ending with “son”

```sql
SELECT *
FROM Users
WHERE Name LIKE '%son';
```

---

### Q3. Write query to find names with second letter ‘a’

```sql
SELECT *
FROM Users
WHERE Name LIKE '_a%';
```

---

### Q4. Which wildcard matches exactly one character?

**Answer:** `_`

---

### Q5. Is `[a-z]` supported in MySQL?

**Answer:** ❌ No

---
