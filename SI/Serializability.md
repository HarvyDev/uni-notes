---
id: Serializability
aliases: []
tags: []
---

# Serializability

The concept of serializability of schedules is used to identify which schedules are correct when transaction executions have interleaving of their operations in the schedules.

Formally a schedule S is **serial** if, for every transaction T participating in the schedule. Otherwise the schedule is called **nonserial**.

Therefore, in a serial schedule, only one transaction at a time is active (the commit or abort of the active transaction initiates execution of the next transaction).

**No interleaving occurs in a serial schedule.**

It does not matter which transaction is executed first. As long as every transaction is executed from the beginning to end in isolation from the operations of other transactions ([[ACID]]), we get a correct end result on the database.

The definition of serializable schedule is as follows:
    - A schedule S of n transactions is **serializable** if it is equivalent to some serial schedule of the same n transactions.

