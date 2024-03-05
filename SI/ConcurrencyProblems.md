---
id: ConcurrencyProblems
aliases: []
tags: []
---

# Concurrency Problems

Several problems can occur when when concurrent transactions execute in an uncontrolled manner, including:

## The Lost Update Problem

This problem occurs when two transactions that access the same database items have their operations interleaved in way that makes the value of some database items incorrect. For example, if a transaction reads a value, then another transaction reads the same value, and then the first transaction updates the value, the second transaction will update the value based on the old value, not the new value. This can lead to incorrect results. 

## The Temporary Update (Dirty Read) Problem

This problem occurs when one transaction updates a database item and then the transaction fails for some reason. Meanwhile, the updated item is accessed (read) by another transaction before it is changed to its original value (rollback).

## The Incorrect Summary Problem 

If one transaction is calculating an aggregate summary function on a number of database items while other transactions are updating some of these items, the aggregate function may calculate some values before they are updated and other after they are updated. This can cause incorrect and unexpected results.

## The Unrepeatable Read Problem 

Another problem that may occur is called unrepeatable read, where a transaction T reads the same item twice and the item is changed by another transaction T' between the two reads. Hence, T receives different values for its two reads of the same item.


