---
id: SchedulesAndConflicts
aliases: []
tags: []
---
# Characterizing Schedules Based on Recoverability

## Schedules (Histories) of Transactions

A schedule (or history) S of n transaction T1, T2, ..., Tn is an ordering of the operations of the transactions. Operations from different transactions can be interleaved in the schedule S. However, for each transaction Ti, that participates in the schedule S, the operations of Ti in S must appear in the same order in which they occur in Ti.

For the purpose of recovery and concurrency control, we are mainly interested in the **read_item** and **write_item** operations of the transactions, as well as the **commit** and **abort** operations.

Two operations of a schedule are in **conflict** if they satisfy all three of the following conditions:
    1. They belong to **different transactions**.
    2. They access the **same item X**.
    3. At least one of the operations is a **write_item** operation.

Intuitively, two operations are conflicting if changing their order can result in a different outcome.

There are **two types of conflicts**:
    1. **Read-write** conflict: A read operation reads the value of an item before a write operation writes a new value to the item, resulting in a incorrect read value of the first operations.
    2. **Write-write** conflict: Two write operations write different values to the same item, resulting in the first value being lost.


## Characterizing Schedules Based on Recoverability

For some schedules it is easy to recover from transaction failures, whereas for other schedules the recovery process can be quite involved. In some cases, it is even not possible to recover correctly after a failure. Hence, it is important to characterize the types of schedules for which recovery is possible, as well as those for which recovery is relatively simple.

First, we would like to ensure that, once a transaction T is committed, it should never be necessary to roll back T. This ensures that durability property of transactions is not violated. The schedules that theoretically meet this criterion are called **recoverable schedules**. Those that do not are called **nonrecoverable** and hence should not be permitted by the DBMS.

**The definition of recoverable schedule is as follows: A schedules S is recoverable if no transaction T in S commits until all transactions T' that have written some item X that T reads have committed.**

A transaction T **reads** from transaction T' in a schedule S if some item X is first written by T' and later read by T. In addition, T' should not have been aborted before T reads item X, and there should be no transaction that write X after T' writes it and before T reads it (unless those transactions, if any, have aborted before T reads X).

In a recoverable schedule, no committed transaction ever needs to be rolled back, and so the definition of committed transaction as durable is not violated. However it is possible for a phenomenon known as **cascading rollback** (or **cascading abort**) to occur in some recoverable schedules, where an uncommited transaction has to be rolled back because it **read an item from a transaction that failed**.

A schedule S is said to be **cascadeless**, or **avoid cascading rollback**, if every transaction in the schedule reads only items that were written by committed transactions. In this case, all items read will not be discarded, so no cascading rollback will occur.
