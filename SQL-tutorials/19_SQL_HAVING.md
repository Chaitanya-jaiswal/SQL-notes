# Lecture 19 – SQL HAVING

---

## Why HAVING Exists

`HAVING` is used to **filter groups**, not individual rows.

👉 `WHERE` **cannot** be used with aggregate functions  
👉 `HAVING` **is specifically designed** to work with aggregates like `COUNT()`, `SUM()`, `AVG()`, etc.

---

## WHERE vs HAVING (Core Concept)

| Clause | Filters | When it runs |
|------|--------|--------------|
| WHERE | Rows | Before GROUP BY |
| HAVING | Groups | After GROUP BY |

---

## Basic HAVING Syntax

```sql
SELECT column_name, AGG_FUNCTION(column_name)
FROM table_name
WHERE condition
GROUP BY column_name
HAVING aggregate_condition
ORDER BY column_name;
````

---

## Example 1: Filter groups using HAVING

**Countries with more than 5 customers**

```sql
SELECT Country, COUNT(CustomerID) AS total_customers
FROM Customers
GROUP BY Country
HAVING COUNT(CustomerID) > 5;
```

✔ GROUP BY creates country groups
✔ HAVING filters those groups

---

## Example 2: HAVING with ORDER BY

```sql
SELECT Country, COUNT(CustomerID) AS total_customers
FROM Customers
GROUP BY Country
HAVING COUNT(CustomerID) > 5
ORDER BY total_customers DESC;
```

✔ ORDER BY runs **after HAVING**

---

## Important Rule ⚠️

❌ This is INVALID:

```sql
SELECT Country FROM Customers
WHERE COUNT(CustomerID) > 5;
```

✔ Aggregate conditions **must go in HAVING**, not WHERE.

---

## HAVING with JOIN

**Employees who handled more than 10 orders**

```sql
SELECT Employees.LastName, COUNT(Orders.OrderID) AS total_orders
FROM Orders
INNER JOIN Employees
ON Orders.EmployeeID = Employees.EmployeeID
GROUP BY Employees.LastName
HAVING COUNT(Orders.OrderID) > 10;
```

✔ JOIN → GROUP BY → HAVING

---

## WHERE + HAVING Together

**Check only specific employees, then filter by aggregate**

```sql
SELECT Employees.LastName, COUNT(Orders.OrderID) AS total_orders
FROM Orders
INNER JOIN Employees
ON Orders.EmployeeID = Employees.EmployeeID
WHERE Employees.LastName IN ('Davolio', 'Fuller')
GROUP BY Employees.LastName
HAVING COUNT(Orders.OrderID) > 25;
```

✔ WHERE filters rows first
✔ HAVING filters grouped results

---

## Common Mistakes ❌

* Using aggregate functions inside `WHERE`
* Forgetting `GROUP BY` before `HAVING`
* Thinking HAVING replaces WHERE (it doesn’t)
* Filtering non-aggregated columns in HAVING unnecessarily

---

## Execution Order (Very Important for Exams)

1. FROM
2. JOIN
3. WHERE
4. GROUP BY
5. HAVING
6. SELECT
7. ORDER BY

---

## HAVING vs GROUP BY vs WHERE (Quick Recap)

* WHERE → row-level filtering
* GROUP BY → grouping logic
* HAVING → group-level filtering

---

## Exam / Interview Tips 📝

* If the condition contains `COUNT`, `SUM`, `AVG`, etc. → **HAVING**
* HAVING is useless without GROUP BY (almost always)
* HAVING runs **after** grouping
* WHERE + HAVING together is very common in real queries

---

## Summary

* `HAVING` filters aggregated data
* Used only after `GROUP BY`
* Solves the limitation of `WHERE`
* Essential for analytics queries

---

```

---
