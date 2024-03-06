---
id: Schedule
aliases: []
tags: []
---

# What is a Schedule

## Schedules of Transactions

A **schedule** S of n transactions T1, T2, ..., Tn is an ordering of the operations of the transactions. Operations from different transactions can be interleaved ([[ConcurrencyProblems]]) in the schedule S. However, for each transaction Ti that participates in the schedule S, the operations of Ti in S must appear in the same order in which they occur in Ti.

## Schedule Equivalence

The simplest but least satisfactory way to define schedule equivalence is to compare the effect of the schedules in the database.

Two schedules called **result equivalent** if they produce the same final state of the database. But result equivalence alone cannot be used to define equivalence of schedules. The safest and most general approach to defining schedule equivalence is not to make any assumptions about the types of operations included in the transactions. For two schedules to be equivalent, the operations applied to each data item affected by the schedules should be applied to that item in both schedules in the **same order**.
