# Lecture 18 – SQL GROUP BY

---

## What is GROUP BY?

`GROUP BY` is used to **group rows that have the same values** in one or more columns and apply **aggregate functions** on each group.

👉 It converts **row-level data → summary-level data**

---

## Why GROUP BY is Needed

Without `GROUP BY`:
- Aggregate functions return **one result for the whole table**

With `GROUP BY`:
- Aggregate functions return **one result per group**

---

## Common Aggregate Functions Used

- `COUNT()` → number of rows
- `SUM()` → total
- `AVG()` → average
- `MIN()` → minimum value
- `MAX()` → maximum value

---

## Basic GROUP BY Syntax

```sql
SELECT column_name, AGG_FUNCTION(column_name)
FROM table_name
GROUP BY column_name;
````

---

## Example 1: Count records per group

**Count number of customers in each country**

```sql
SELECT Country, COUNT(CustomerID) AS total_customers
FROM Customers
GROUP BY Country;
```

✔ Groups rows by `Country`
✔ COUNT runs **inside each group**

---

## Example 2: GROUP BY with ORDER BY

```sql
SELECT Country, COUNT(CustomerID) AS total_customers
FROM Customers
GROUP BY Country
ORDER BY total_customers DESC;
```

✔ Sorting happens **after grouping**

---

## Important Rule ⚠️

👉 **Every column in SELECT must be either:**

* present in `GROUP BY`, OR
* wrapped inside an aggregate function

❌ This is INVALID:

```sql
SELECT Country, City, COUNT(*) FROM Customers GROUP BY Country;
```

---

## GROUP BY with WHERE

```sql
SELECT Country, COUNT(*) 
FROM Customers
WHERE Country <> 'USA'
GROUP BY Country;
```

✔ `WHERE` filters rows **before grouping**

---

## GROUP BY with JOIN

**Count number of orders per shipper**

```sql
SELECT Shippers.ShipperName, COUNT(Orders.OrderID) AS total_orders
FROM Orders
LEFT JOIN Shippers
ON Orders.ShipperID = Shippers.ShipperID
GROUP BY Shippers.ShipperName;
```

✔ JOIN happens first
✔ GROUP BY summarizes joined data

---

## GROUP BY vs WHERE vs HAVING

| Clause   | Purpose        | When it runs    |
| -------- | -------------- | --------------- |
| WHERE    | Filters rows   | Before GROUP BY |
| GROUP BY | Groups rows    | After WHERE     |
| HAVING   | Filters groups | After GROUP BY  |

---

## Example: HAVING (preview)

```sql
SELECT Country, COUNT(*) AS total_customers
FROM Customers
GROUP BY Country
HAVING COUNT(*) > 5;
```

✔ Filters **groups**, not rows

---

## Common Mistakes ❌

* Using aggregate functions in `WHERE`
* Selecting columns not in `GROUP BY`
* Confusing `WHERE` with `HAVING`
* Forgetting aliases for aggregate columns

---

## Exam / Interview Tips 📝

* GROUP BY is **mandatory** when mixing aggregates + normal columns
* GROUP BY always works **column-wise**
* GROUP BY ≠ ORDER BY
* GROUP BY ≠ DISTINCT (though results may look similar)

---

## Summary

* `GROUP BY` creates summary data
* Used with aggregate functions
* Works before `ORDER BY` and after `WHERE`
* Essential for analytics and reports

---

```

---
