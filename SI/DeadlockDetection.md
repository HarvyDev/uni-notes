---
id: DeadlockDetection
aliases: []
tags: []
---

# Deadlock Detection

A second, more practical approach to dealing with deadlock is **deadlock detection**, where the system checks if a state of deadlock actually exists.

A simple way to detect a state of deadlock is for the system to construct and maintain a **wait-for-graph**. One node is created in the wait-for-graph for each transaction that is concurrently executing. Whenever a transaction Ti is waiting to lock an item X that is currently locked by a transaction Tj, a directed edge (Ti -> Tj) is created in the wait-for-graph. When Tj releases the lock(s) on the items that Ti was waiting for, the directed edge is dropped from the wait-for-graph. We have a state of deadlock if and only if the wait-for-graph has a cycle.

If the system is in a state of **deadlock**, some of the transaction causing the deadlock must be aborted. Choosing which transactions to abort is known as **victim selection**. The algorithm for victim selection should generally avoid selecting transactions that have been running that have performed many updates, and it should try instead try instead to select transaction that have not made many changes (younger transactions).


## Timeouts 

Another simple scheme to deal with deadlock is the use of **timeouts**. This method is practical because of its low overhead and simplicity. In this method, if a transaction wait for a period longer than a system-defined timeout period, the system assumes that the transaction may be deadlocked and aborts it, regardless of whether a lock actually exists or not.

## Starvation

Another problem that may occur when we use locking is **starvation**, which occurs when a transaction cannot proceed for an indefinite period of time while other transactions in the system continue normally. This may occur if the waiting scheme for locked items is unfair, giving priority to some transaction over others. One solution for starvation is to have a fair waiting scheme, such as using a **first-come-first-served** queue. Starvation can also occur because of victim selection if the algorithm selects the same transaction as victim repeatedly, thus causing it to abort and never finish execution. The **wait-die** and **wound-wait** schemes avoid starvation because they restart a transaction that has been aborted with its original timestamp.
