---
id: Deadlock
aliases: []
tags: []
---


# Deadlock

**Deadlock** occurs when each transaction T in a set of two or more transactions is waiting for some item that is locked by some other transaction T' in the set. Hence, each transaction in the set is in a waiting queue, waiting for one of the other transactions in the set to release the lock on an item. But because the other transaction is also waiting, it will never release the lock. And that is called a **deadlock**.

## Deadlock Prevention Protocols

One way to prevent deadlock is to use a **deadlock prevention protocol**.

A number of deadlock prevention schemes have been proposed that make a decision about what to do with a transaction involved in a possible deadlock situation. Some of these techniques use the concept of **transaction timestamp TS(T)**, which is a unique identifier assigned to each transaction. The timestamps are typically based on the order in which transaction are started.

Two schemes that prevent deadlock are called **wait-die** and **wound-wait**.

Suppose that transaction Ti tries to lock an item X but is not able to because X is locked by some other transaction Tj with a conflicting lock. The rules followed by this scheme are:
    - **Wait-die**: If TS(Ti) < TS(Tj), then (Ti older than Tj) Ti is allowed to wait. Otherwise (Ti younger than Tj) abort Ti (Ti dies) and restart it later with the same timestamp.
    - **Wound-wait**: If TS(Ti) < TS(Tj), then (Ti older than Tj) abort Tj (Ti wounds Tj) and restart it lates with the same timestamp. Otherwise (Ti younger than Tj) Ti is allowed to wait.


Another group of protocols that prevent deadlock do not require timestamps. These include the no waiting and cautious waiting. In the **no waiting algorithm**, if a transaction is unable to obtain a lock, it is immediately aborted and then restarted after a certain time delay without checking whether a deadlock will actually occur or not. In this case, no transaction ever waits, so no deadlock will occur. However this scheme can cause transactions to abort and restart needlessly. The **cautious waiting algorithm** was proposed to try to reduce the number of needless aborts/restarts. Suppose that transaction Ti tries to lock an item X but is not able to do so because X is locked by some other transaction Tj with a conflicting lock, The cautious waiting rules are as follows:
    - **Cautious-waiting**: If Tj is not blocked (not waiting for some other locked item), then Ti is blocked and allowed to wait, otherwise abort Ti.

In summary, in **wait-die**, an older transaction is allowed to wait for a younger transaction, whereas a younger transaction requesting an item held by an older transaction is aborted and restarted. The **wound-wait** approach does the opposite: A younger transaction is allowed to wait for an older one, whereas an older transaction requesting an item held by a younger transaction peempts the younger transaction by aborting it. The **no waiting** approach aborts a transaction immediately if it cannot obtain a lock, and the **cautious waiting** approach allows a transaction to wait only if the transaction holding the lock is not waiting for some other lock.


