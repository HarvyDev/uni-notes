---
id: Schedule
aliases: []
tags: []
---

# What is a Schedule

## Schedules of Transactions

A **schedule** S of n transactions T1, T2, ..., Tn is an ordering of the operations of the transactions. Operations from different transactions can be interleaved ([[ConcurrencyProblems]]) in the schedule S. However, for each transaction Ti that participates in the schedule S, the operations of Ti in S must appear in the same order in which they occur in Ti.

### Schedule Equivalence

The simplest but least satisfactory way to define schedule equivalence is to compare the effect of the schedules in the database.

Two schedules called **result equivalent** if they produce the same final state of the database. But result equivalence alone cannot be used to define equivalence of schedules. The safest and most general approach to defining schedule equivalence is not to make any assumptions about the types of operations included in the transactions. For two schedules to be equivalent, the operations applied to each data item affected by the schedules should be applied to that item in both schedules in the **same order**.

## Schedule Properties

A schedule has the following properties:


## Types of Schedules

### Recoverable Schedule

A schedule is recoverable if it allows for the recovery of the database to a consistent state after a transaction failure. In a recoverable schedule, a transaction that has updated the database must commit before any other transaction reads or writes the same data.

### Cascadeless Schedule

A schedule is cascadeless if it does not result in a cascading rollback of transactions after a failure. **In a cascadeless schedule, a transaction that has read uncommitted data from another transaction cannot commit before that transaction commits**. If a transaction fails before committing, its updates must be rolled back, but any transactions that have read its uncommitted data must also be rolled back.

### Strict Schedule

In a **strict schedule**, a transaction that has read uncommitted data from another transaction **cannot commit before that transaction commits**, and a transaction that has updates the database must commit before any other transaction reads or writes the same data.
