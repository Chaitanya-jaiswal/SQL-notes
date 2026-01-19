# 📘 Lecture 28: SQL Operators

## 🔹 What are SQL Operators?

- SQL operators are **symbols or keywords** used to:
  - Perform calculations
  - Compare values
  - Combine conditions
- Mostly used in:
  - SELECT
  - WHERE
  - HAVING
  - JOIN conditions

---

## 🔹 Arithmetic Operators

Used to perform **mathematical calculations**.

| Operator | Meaning |
|--------|---------|
| + | Addition |
| - | Subtraction |
| * | Multiplication |
| / | Division |
| % | Modulus (remainder) |

### Example

```sql
SELECT Salary + Bonus AS TotalPay
FROM Employees;
````

---

## 🔹 Comparison Operators ⭐

Used to **compare values** and return TRUE/FALSE.

| Operator | Meaning               |
| -------- | --------------------- |
| =        | Equal to              |
| >        | Greater than          |
| <        | Less than             |
| >=       | Greater than or equal |
| <=       | Less than or equal    |
| <>       | Not equal             |

### Example

```sql
SELECT *
FROM Employees
WHERE Salary >= 50000;
```

---

## 🔹 Logical Operators ⭐⭐⭐

Used to **combine multiple conditions**.

| Operator   | Meaning                            |
| ---------- | ---------------------------------- |
| AND        | TRUE if all conditions are TRUE    |
| OR         | TRUE if any condition is TRUE      |
| NOT        | Reverses condition                 |
| IN         | Matches any value in list          |
| BETWEEN    | Checks range                       |
| LIKE       | Pattern matching                   |
| EXISTS     | TRUE if subquery returns rows      |
| ANY / SOME | TRUE if any subquery value matches |
| ALL        | TRUE if all subquery values match  |

---

## 🔹 Logical Operator Example

```sql
SELECT *
FROM Customers
WHERE Country = 'India' AND City = 'Mumbai';
```

---

## 🔹 Bitwise Operators (Low Exam Priority)

Operate on **binary values**.

| Operator | Meaning     |            |
| -------- | ----------- | ---------- |
| &        | Bitwise AND |            |
|          |             | Bitwise OR |
| ^        | Bitwise XOR |            |

📌 Mostly used in **SQL Server**, rarely asked in exams.

---

## 🔹 Compound Operators

Used to **modify a value and assign it back**.

| Operator | Meaning             |
| -------- | ------------------- |
| +=       | Add and assign      |
| -=       | Subtract and assign |
| *=       | Multiply and assign |
| /=       | Divide and assign   |
| %=       | Modulus and assign  |

📌 Limited SQL support → **low exam weight**.

---

## 🔹 Operators vs Functions (Exam Tip ⭐)

| Operators          | Functions                |
| ------------------ | ------------------------ |
| Symbols / keywords | Built-in methods         |
| Faster             | More flexible            |
| Used in conditions | Used for transformations |

---

## 🔹 Common Mistakes (High Probability ⭐)

* Using `=` instead of `LIKE`
* Forgetting operator precedence
* Using `<>` incorrectly
* Confusing AND vs OR
* Ignoring NULL in comparisons

---

## 🔹 Operator Precedence (Important ⭐)

1. Arithmetic
2. Comparison
3. NOT
4. AND
5. OR

📌 Use **parentheses** to control evaluation.

---

## 🔹 Summary

* Operators perform calculations and comparisons
* Arithmetic operators handle math
* Comparison operators filter data
* Logical operators combine conditions
* AND has higher priority than OR
* Parentheses avoid logical errors

---

## 🔹 Practice Questions (Exam-Oriented)

### Q1. Which operator is used to add two numbers?

**Answer:**
`+`

---

### Q2. Which operator checks a range of values?

**Answer:**
`BETWEEN`

---

### Q3. Which operator returns TRUE if all conditions are met?

**Answer:**
`AND`

---

### Q4. Write a query using comparison operator.

```sql
SELECT *
FROM Students
WHERE Marks > 60;
```

---

### Q5. Which operator is used for pattern matching?

**Answer:**
`LIKE`

---

```

---