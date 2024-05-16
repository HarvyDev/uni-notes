---
id: HashIndex
aliases: []
tags: []
---

# Hash Index

## How does the Hash index work?

The Hash Index is a data structure that works similarly to the way that hash maps work. The Hash Index is a **key-value pair** data structure that is used to store the keys of a table in a hash table.

It is most useful for **equality queries** since it can have O(1) time complexity for lookups.

However, it is not well suited for **range queries** since it does not store the keys in a sorted order. 
