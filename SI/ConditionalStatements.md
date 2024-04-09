---
id: ConditionalStatements
aliases: []
tags: []
---

# Conditional Statements

Conditional statements are used to execute different statements based on different conditions. In PostgreSQL, the following conditional statements are available:
- `IF` statement
- `CASE` statement

## IF Statement

The `IF` statement is used to execute a block of code if a certain condition is met. The syntax of the `IF` statement is as follows:

```sql
IF condition THEN
    -- statements
ELSIF condition THEN
    -- statements
ELSE
    -- statements
END IF;
```

## CASE Statement

The `CASE` statement provides conditional execution based on equality of operands. The expression is evaluated once and compared to each `WHEN` clause. If a match is found, then the corresponding statements are executed and then the control passes to the next statements after `END CASE`. If no match is found, the `ELSE` statements are executed.

The syntax of the `CASE` statement is as follows:

```SQL
CASE
    WHEN condition1 THEN
        -- statements
    WHEN condition2 THEN
        -- statements
    ELSE
        -- statements
END CASE;
```
