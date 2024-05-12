---
id: Analyze
aliases: []
tags: []
---

# Analyze

## What is the `ANALYZE` statement?

It is possible to check the accuracy of the planner's estimates by using `EXPLAIN`'s `ANALYZE` option. With this option, `EXPLAIN` actually executes the query, and then displays the true row counts and true run time accumulated within each plan node, along with the same estimates that a plain `EXPLAIN` shows.

To use the `ANALYZE` option, simply add the keyword after the `EXPLAIN` keyword.

```sql
EXPLAIN ANALYZE SELECT * FROM table_name WHERE column_name = 'value';
```
