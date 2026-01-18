# Lecture 20 – SQL EXISTS

---

## What is EXISTS?

`EXISTS` is used to **check whether a subquery returns at least one row**.

- If the subquery returns **one or more rows** → `EXISTS` = TRUE
- If the subquery returns **no rows** → `EXISTS` = FALSE

⚠️ `EXISTS` does **not return data** from the subquery  
It only checks **existence**

---

## Why EXISTS is Useful

- Efficient for checking **relationships between tables**
- Stops searching as soon as **one matching row is found**
- Commonly used instead of `IN` for better performance

---

## Basic Syntax

```sql
SELECT column_name(s)
FROM table1
WHERE EXISTS (
    SELECT column_name
    FROM table2
    WHERE condition
);
````

---

## How EXISTS Works (Concept)

* Outer query checks rows one by one
* Subquery is executed for each row
* If subquery returns **any row**, outer row is selected

---

## Example Tables (Conceptual)

### Suppliers

* SupplierID
* SupplierName

### Products

* ProductID
* SupplierID
* Price

---

## Example 1: Suppliers who have products cheaper than 20

```sql
SELECT SupplierName
FROM Suppliers
WHERE EXISTS (
    SELECT 1
    FROM Products
    WHERE Products.SupplierID = Suppliers.SupplierID
    AND Price < 20
);
```

✔ Subquery checks if **at least one product** exists
✔ Price condition applied inside subquery

---

## Example 2: Suppliers with a product priced exactly at 22

```sql
SELECT SupplierName
FROM Suppliers
WHERE EXISTS (
    SELECT 1
    FROM Products
    WHERE Products.SupplierID = Suppliers.SupplierID
    AND Price = 22
);
```

✔ Even **one matching product** is enough

---

## Important Rule ⚠️

The values returned inside `SELECT` in the subquery **do not matter**

These are all equivalent:

```sql
SELECT 1
SELECT *
SELECT ProductName
```

Because `EXISTS` only checks **whether a row exists**

---

## EXISTS vs IN (Very Important)

### EXISTS

* Checks existence
* Faster for large datasets
* Stops when first match is found

### IN

* Compares values
* Can be slower for large subqueries
* Issues with NULL values

---

## EXISTS vs IN Example

```sql
-- EXISTS
SELECT SupplierName
FROM Suppliers S
WHERE EXISTS (
    SELECT 1 FROM Products P
    WHERE P.SupplierID = S.SupplierID
);

-- IN
SELECT SupplierName
FROM Suppliers
WHERE SupplierID IN (
    SELECT SupplierID FROM Products
);
```

✔ Output same
✔ `EXISTS` usually more efficient

---

## EXISTS with NOT

**Find suppliers who have NO products**

```sql
SELECT SupplierName
FROM Suppliers
WHERE NOT EXISTS (
    SELECT 1
    FROM Products
    WHERE Products.SupplierID = Suppliers.SupplierID
);
```

✔ Common interview question
✔ Very powerful use case

---

## Common Mistakes ❌

* Expecting EXISTS to return values
* Using EXISTS without a proper correlation condition
* Confusing EXISTS with JOIN
* Forgetting `NOT` when checking absence

---

## Execution Flow (Important for Exams)

1. Outer query row selected
2. Subquery executed
3. EXISTS checks if **any row exists**
4. TRUE → row included
5. FALSE → row excluded

---

## When to Use EXISTS

* Relationship checks
* Presence / absence queries
* Correlated subqueries
* Performance-critical queries

---

## Exam / Interview Tips 📝

* EXISTS returns TRUE/FALSE, not data
* Subquery result content is irrelevant
* EXISTS + NOT EXISTS = very common
* Faster than IN in many cases

---

## Summary

* `EXISTS` checks existence of rows
* Works with subqueries
* Returns TRUE or FALSE
* Best for relational checks
* Often used with NOT EXISTS

---

```

---
