# Lecture 14 – SQL Wildcards

## What are SQL Wildcards?
SQL **wildcards** are special characters used with the `LIKE` operator to **match patterns** in text data.

They are mainly used in the `WHERE` clause.

---

## Common Wildcards

| Wildcard | Meaning |
|--------|--------|
| `%` | Matches **zero or more characters** |
| `_` | Matches **exactly one character** |

> Wildcards are **case-sensitive** in some databases (depends on collation).

---

## `%` Wildcard (Multiple Characters)

### Starts with a letter
```sql
SELECT * FROM Customers
WHERE CustomerName LIKE 'A%';
````

✔ Names starting with **A**

---

### Ends with a letter

```sql
SELECT * FROM Customers
WHERE CustomerName LIKE '%a';
```

✔ Names ending with **a**

---

### Contains a word or letter

```sql
SELECT * FROM Customers
WHERE CustomerName LIKE '%or%';
```

✔ Names containing **or**

---

## `_` Wildcard (Single Character)

### Fixed-length pattern

```sql
SELECT * FROM Customers
WHERE City LIKE 'L_nd_n';
```

✔ Matches: **London**

---

### Character at a specific position

```sql
SELECT * FROM Customers
WHERE CustomerName LIKE '_r%';
```

✔ Second letter must be **r**

---

## Combining `%` and `_`

```sql
SELECT * FROM Customers
WHERE CustomerName LIKE 'A__%';
```

✔ Starts with **A**
✔ At least **3 characters long**

---

## Exact Match using LIKE (No Wildcards)

```sql
SELECT * FROM Customers
WHERE Country LIKE 'Germany';
```

✔ Same as `=`
✔ No pattern matching here

---

## Using LIKE with AND / OR

### OR condition

```sql
SELECT * FROM Customers
WHERE CustomerName LIKE 'A%' OR CustomerName LIKE 'B%';
```

---

### AND condition

```sql
SELECT * FROM Customers
WHERE CustomerName LIKE 'B%' AND CustomerName LIKE '%s';
```

✔ Starts with **B** and ends with **s**

---

## NOT LIKE

```sql
SELECT * FROM Customers
WHERE CustomerName NOT LIKE 'A%';
```

✔ Excludes names starting with **A**

---

## Important Notes (Exam / Interview)

* `%` → **any number of characters**
* `_` → **exactly one character**
* `LIKE` is mainly for **text columns**
* `LIKE` with no wildcard behaves like `=`
* Performance may drop if `%` is used at the **start** (`'%abc'`)

---

## Quick Summary

| Pattern    | Meaning                    |
| ---------- | -------------------------- |
| `'A%'`     | Starts with A              |
| `'%a'`     | Ends with a                |
| `'%or%'`   | Contains or                |
| `'L_nd_n'` | Fixed pattern              |
| `'A__%'`   | Starts with A, min 3 chars |

---

## End of Lecture 14

```

---
