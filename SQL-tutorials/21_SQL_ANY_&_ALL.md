# Lecture 21 – SQL ANY and ALL

---

## What are ANY and ALL?

`ANY` and `ALL` are SQL operators used to **compare a single value with a set of values returned by a subquery**.

They always return a **boolean result (TRUE / FALSE)**.

---

## SQL ANY Operator

### Meaning of ANY

- Returns **TRUE if at least ONE value** in the subquery satisfies the condition
- Works like a logical **OR**

---

### ANY Syntax

```sql
SELECT column_name(s)
FROM table_name
WHERE column_name operator ANY (
    SELECT column_name
    FROM table_name
    WHERE condition
);
````

⚠️ The operator must be:
`=, <>, !=, >, >=, <, <=`

---

### Example Tables (Concept)

**Products**

* ProductID
* ProductName

**OrderDetails**

* ProductID
* Quantity

---

### Example 1: Products ordered with quantity = 10

```sql
SELECT ProductName
FROM Products
WHERE ProductID = ANY (
    SELECT ProductID
    FROM OrderDetails
    WHERE Quantity = 10
);
```

✔ TRUE if **any row** in subquery has Quantity = 10
✔ Even one match is enough

---

### Example 2: Quantity greater than 99

```sql
SELECT ProductName
FROM Products
WHERE ProductID = ANY (
    SELECT ProductID
    FROM OrderDetails
    WHERE Quantity > 99
);
```

✔ Returns rows **only if at least one match exists**

---

### Example 3: No matching rows (FALSE case)

```sql
SELECT ProductName
FROM Products
WHERE ProductID = ANY (
    SELECT ProductID
    FROM OrderDetails
    WHERE Quantity > 1000
);
```

❌ Subquery returns no rows
❌ ANY → FALSE

---

## SQL ALL Operator

### Meaning of ALL

* Returns **TRUE only if ALL values** in the subquery satisfy the condition
* Works like a logical **AND**

---

### ALL Syntax (with WHERE / HAVING)

```sql
SELECT column_name(s)
FROM table_name
WHERE column_name operator ALL (
    SELECT column_name
    FROM table_name
    WHERE condition
);
```

---

### Example 4: ALL keyword with SELECT

```sql
SELECT ALL ProductName
FROM Products;
```

✔ `ALL` here simply means **do not remove duplicates**
✔ Default behavior of SELECT

---

### Example 5: ALL with condition (mostly FALSE)

```sql
SELECT ProductName
FROM Products
WHERE ProductID = ALL (
    SELECT ProductID
    FROM OrderDetails
    WHERE Quantity = 10
);
```

❌ FALSE unless **every row** in subquery matches
❌ Very strict condition

---

## ANY vs ALL (Very Important)

| Feature    | ANY                       | ALL                          |
| ---------- | ------------------------- | ---------------------------- |
| Logic      | OR                        | AND                          |
| TRUE when  | Any one condition is true | All conditions are true      |
| Strictness | Less strict               | Very strict                  |
| Common use | Checking existence        | Checking universal condition |

---

## ANY vs IN (Important Concept)

```sql
-- ANY
WHERE ProductID = ANY (subquery)

-- IN
WHERE ProductID IN (subquery)
```

✔ For `=` operator, `ANY` behaves similar to `IN`
✔ Difference appears with `<`, `>`, `>=`, etc.

---

## Common Mistakes ❌

* Forgetting comparison operator
* Expecting ANY / ALL to return data
* Using ALL when ANY is needed
* Confusing EXISTS with ANY

---

## When to Use ANY

* When **at least one value** should satisfy condition
* Flexible comparisons (`>`, `<`, `>=`)

---

## When to Use ALL

* When **every value** must satisfy condition
* Rare but important for logic-based queries

---

## Exam / Interview Tips 📝

* ANY = OR logic
* ALL = AND logic
* Works only with subqueries
* Requires comparison operator
* EXISTS ≠ ANY ≠ ALL

---

## Summary

* ANY → TRUE if **one or more** matches
* ALL → TRUE only if **all** match
* Used with subqueries
* Powerful but must be used carefully

---

```

---
