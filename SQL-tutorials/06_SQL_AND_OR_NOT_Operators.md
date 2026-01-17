# 📘 Lecture 6: AND, OR, NOT Operators

> This lecture explains how to apply multiple conditions in SQL using logical operators.

---

## 🔹 Why Logical Operators Are Needed

* Real-world queries often require **more than one condition**
* Logical operators allow combining conditions inside `WHERE`
* They control **how conditions are evaluated**

---

## 🔹 AND Operator

### Concept

* `AND` returns a row **only if all conditions are TRUE**
* Used when **multiple restrictions must be satisfied**

### Syntax

```sql
WHERE condition1 AND condition2;
```

### Example

```sql
SELECT *
FROM Customers
WHERE Country = 'Spain' AND City = 'Madrid';
```

➡ Customer must be **from Spain AND Madrid**

📌 If even one condition is false → row is excluded

---

## 🔹 OR Operator

### Concept

* `OR` returns a row if **any one condition is TRUE**
* Used when **alternatives are allowed**

### Syntax

```sql
WHERE condition1 OR condition2;
```

### Example

```sql
SELECT *
FROM Customers
WHERE Country = 'Germany' OR Country = 'Spain';
```

➡ Customers from **Germany OR Spain**

📌 Only one condition needs to be true

---

## 🔹 AND vs OR (Core Difference ⭐)

| AND                         | OR                                  |
| --------------------------- | ----------------------------------- |
| All conditions must be true | At least one condition must be true |
| Narrows results             | Expands results                     |
| More restrictive            | Less restrictive                    |

---

## 🔹 NOT Operator

### Concept

* `NOT` **reverses a condition**
* Used to exclude specific values

### Syntax

```sql
WHERE NOT condition;
```

### Example

```sql
SELECT *
FROM Customers
WHERE NOT Country = 'Spain';
```

➡ Customers **not from Spain**

---

## 🔹 NOT with Other Operators

`NOT` can be combined with many operators:

```sql
NOT LIKE
NOT BETWEEN
NOT IN
```

### Examples

```sql
WHERE CustomerName NOT LIKE 'A%';
```

```sql
WHERE City NOT IN ('Paris', 'London');
```

---

## 🔹 Combining AND, OR, NOT (Very Important ⭐⭐⭐)

* SQL follows **operator precedence**
* `AND` is evaluated **before** `OR`
* Use **parentheses** to control logic

### Correct Usage

```sql
SELECT *
FROM Customers
WHERE Country = 'Spain'
AND (CustomerName LIKE 'G%' OR CustomerName LIKE 'R%');
```

➡ Spanish customers whose names start with **G or R**

---

## 🔹 Without Parentheses (Common Mistake ❌)

```sql
WHERE Country = 'Spain'
AND CustomerName LIKE 'G%'
OR CustomerName LIKE 'R%';
```

➡ Returns:

* Spanish customers starting with G
* **All customers starting with R (any country)** ❌

📌 **Parentheses are critical in exams**

---

## 🔹 Logical Evaluation Order (Exam Favorite ⭐)

1. `NOT`
2. `AND`
3. `OR`

---

## 🔹 Common Mistakes (High Probability ⭐)

* Forgetting parentheses
* Misunderstanding AND vs OR
* Overusing OR (returns too many rows)
* Writing complex conditions without clarity

---

## 🔹 Summary

* AND → all conditions must be true
* OR → at least one condition must be true
* NOT → negates a condition
* Parentheses control evaluation
* AND is evaluated before OR
* Logical operators are used inside WHERE

---

## 🔹 Practice Questions (Exam-Oriented)

### Q1. What does the AND operator do?

**Answer:**
It returns records only when all conditions are true.

---

### Q2. Write a query to select customers from India or Italy.

```sql
SELECT *
FROM Customers
WHERE Country = 'India' OR Country = 'Italy';
```

---

### Q3. Write a query to select customers not from Germany.

```sql
SELECT *
FROM Customers
WHERE NOT Country = 'Germany';
```

---

### Q4. Which operator has higher priority: AND or OR?

**Answer:**
AND has higher priority than OR.

---

### Q5. Why are parentheses used with AND and OR?

**Answer:**
To control the order of condition evaluation and avoid incorrect results.

---