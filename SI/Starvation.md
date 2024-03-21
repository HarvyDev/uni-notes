---
id: Starvation
aliases: []
tags: []
---

# Starvation

**Starvation** is a problem that may occur when we use locking. It occurs when a transaction cannot process for an indefinite period of time while other transactions in the system continue normally. This may occur if the waiting scheme for locked items is unfair, giving priority to some transactions over others. One solution for starvation is to have a fair waiting scheme, such as using a **first-come-first-served** queue. In this case, transactions are allowed to lock an item in the order in which they requested the lock.
