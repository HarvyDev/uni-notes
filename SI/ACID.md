---
id: ACID
aliases: []
tags: []
---

# Desirable Properties of Transactions

Transactions should possess several properties, often called ACID properties. They should be enforced by the concurrency control and recovery methods of the DBMS. The following are the ACID properties:
    - **Atomicity**: A transaction is an atomic unit of processing. It should either be performed in its entirety or not performed at all.
    - **Consistency preservation**: A transaction should be consistency preserving, meaning that if it is completely executed from beginning to end without interference from other transactions, it should take the database from on consistent state to another.
    - **Isolation**: A transaction should appear as though it is begin executed in isolation from other transactions, even though many transactions are executing concurrently. That is, the execution of a transaction should not be interfered with by any other transactions executing concurrently.
    - **Durability**: The changes applied to the database by a committed transaction must persist in the database. These changes must not be lost because of any failure.

The preservation of consistency is generally considered to be the responsibility of the programmers who write the database programs or of the DBMS module that enforces integrity constraints. 

The **database state** is a collection of all the stored data items (values) in the database at a given point in time.

A **consistent state** of the database satisfies the constraints specified in the schema as well as any other constraints on the database that should hold.

