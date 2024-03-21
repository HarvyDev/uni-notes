---
id: Locks
aliases: []
tags: []
---

# Locks

Locking protocols are used in database management systems as a means of concurrency control.

A lock is a mechanism to control access to a shared resource by multiple processes. Locks are used to prevent conflicts between concurrent transactions.

Each data item in the database is associated with a lock. 


## Types of Locks

Several types of locks are used in concurrency control. Some of these are:
    - [[BinaryLock]]
    - [[MultipleModeLock]]


## Lock Operations

Locks are used to control access to shared resources. The following operations are performed on locks:
    - `lock(X)`: Acquire a lock on resource `X`.
    - `unlock(X)`: Release the lock on resource `X`.
