---
id: TypesOfLocks
aliases: []
tags: []
---

# Types of Locks and Systems

## Binary Locks

**Binary Locks**. A **binary lock** can have two **states** or **values**: locked and unlocked. A distinct lock is associated with each database item X. If the value of the lock on X is 1, item X cannot be accessed by a database operation that requests the item. If the value of the lock on X is 0, the item can be accessed. We refer to the current value (or state) of the lock associated with item X as **lock(X)**.

Two operations, lock_item and unlock_item, are used with binary locking. A transaction requests access to an item X by first issuing a **lock_item(X)** operation. If LOCK(X) = 1, the transaction is forced to wait. If LOCK(X) = 0, it is set to 1 (the transaction **locks** the item) and the transaction is allowed  to access item X. When the transaction is through using the item, it issues an **unlock_item(X)** operation, which sets LOCK(X) back to 0 (**unlocks** the item) so that X may be accessed by other transactions. Hence, a binary lock enforces **mutual exclusion** on the data item. 

## Shared/Exclusive (Read/Write) Locks

The preceding binary locking scheme is too restrictive for database items because at most, one transaction can hold a lock on a given item. We should allow several transactions to access the same item X if they all access X for reading purposes only (because read operations are not conflicting).

However, if a transaction is to write an item X, it must have exclusive access to X. For this purpose, a different type of lock called a **multiple-mode lock** is used. In this scheme called **shared/exclusive** or **read/write** locks, there are three locking operations
    * **read_lock(X)** 
    * **write_lock(X)**
    * **unlock(X)**

A lock associated with an item X, LOCK(X), now has three possible states:
    * **read_locked(X)**: Also caleed **shared-lock** because other transaction are allowed to read the item.
    * **write_locked(X)**: Also called **exclusive-lock** because no other transaction is allowed to read or write the item.
    * **unlocked(X)**: No transaction has a lock on the item.

