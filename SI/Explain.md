---
id: Explain
aliases: []
tags: []
---

# Explain 

## What is the `EXPLAIN` statement?

The `EXPLAIN` statement is a powerful tool in SQL that allows the user to see the plan of execution of the supplied query without it actually being executed. However, if you provide the command `ANALYZE` ([[Analyze]]) carries out the command and shows actual run times and other statistics.

## Why is the `EXPLAIN` statement important?

The `EXPLAIN` statement is important because it allows the user to see how the database is executing a query and what steps it is taking to retrieve the data. This can be very useful for **optimizing queries** and understanding how the database engine works.

## What information does the `EXPLAIN` statement provide?

The `EXPLAIN` statement provides information about the query execution plan, such as:
- **Estimated cost of the query** (how long it will take to execute the query)
- The **number of rows that the query is expected to return**
- The order in which tables are accessed
- The type of scan being used:
    - **seq_scan**: Sequential scan (scanning the entire table)
    - **index_scan**: Index scan (utilizing an index)
- The type of join being used in case of joins:
    - **nested loop**
    - **hash join**
    - **merge join**

## How to use the `EXPLAIN` statement?

```sql
EXPLAIN SELECT * FROM table_name WHERE column_name = 'value';
```
