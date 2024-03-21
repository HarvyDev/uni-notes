---
id: MultipleModeLock
aliases: []
tags: []
---

# Multiple Mode Lock

A multiple mode lock allows multiple processes to access a shared resource simultaneously. It is a more flexible lock compared to a binary lock.

This type of lock has three locking operations:
    - **read_lock(X)**: Acquire a read lock on resource `X`.
    - **write_lock(X)**: Acquire a write lock on resource `X`.
    - **unlock(X)**: Release the lock on resource `X`.

When the lock is in read mode, **multiple processes** can acquire the lock. However, when the lock is in write mode, **only one** process can acquire the lock.    

