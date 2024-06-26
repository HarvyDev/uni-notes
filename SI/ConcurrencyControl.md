---
id: ConcurrencyControl
aliases: []
tags: []
---

# Concurrency Control 

Most of the control techniques that are used to ensure the noninterference or isolation property of concurrently executing transactions ensure serializability of schedules ([[Serializability]]) using **concurrency protocols** (sets of rules) that guaranteee serializability. One important set of protocols, known as two-phase locking protocols, employ the technique of **locking** data items to prevent multiple  transactions from accessing the same items concurrently. 

Another set of concurrency control protocols are **timestamps**. A timestamp is a unique identifier for each transaction, generated by the system. Timestamps values are generated in the same order as the transaction start times. There's also **multiversion** concurrency protocols and many others.

