---
id: B-TreeIndex
aliases: []
tags: []
---

# B-Tree Index

## How does the B-Tree index work?

The B-Tree index is a data structure that is used to **improve the performance of queries** in a database. The B-Tree index is a balanced tree data structure that is used to store the keys of a table in tree form. 

This type of index is best suited for **range queries** like `BETWEEN`, `>`, `<`, `>=`, `<=`, etc.

It is the default type of index in PostgreSQL databases.

## Main differences between B-Tree and a Binary Tree

The **main differences** between B-Tree and a normal Binary Tree are the following:
- B-Tree can have **more than two children per node**.
- B-Tree is always **balanced**.
- B-Tree is self-balancing, by having a minimum and a maximum number of children per node.
- B-Tree's are **optimized for storage systems and databases**, where disk I/O operations are expensive. The balanced structure of B-Tree's ensures that **disk seeks are minimized**, leading to efficient data retrieval.
