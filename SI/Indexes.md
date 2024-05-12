---
id: Indexes
aliases: []
tags: []
---

# Indexes

## What are indexes?

Indexes a powerful tool used in the background of a database to **speed up querying**. Indexes power queries by providing a method to **quickly lookup the requested data**.

Simply put, an index is a **pointer to data in a table**.

## Why are indexes important?

Indexes are important because they allow for faster querying of data. Without indexes, a query, in a big table, would have to scan the entire table to find the requested data, but instead, with indexes, the database can quickly find the data by following the pointers in the index, which is much faster.

## Downsides of indexes

While indexes are great for speeding up queries, they also have some downsides.

Indexes take up extra space in the database, which can be a problem if you have a large table with many indexes.

Also, indexes can slow down write operations, such as inserting, updating, or deleting data, because the **database has to update the indexes as well**.

## How to create an index?

To create an index, you can use the `CREATE INDEX` statement. 

```sql
CREATE INDEX index_name ON table_name (column_name);
```

