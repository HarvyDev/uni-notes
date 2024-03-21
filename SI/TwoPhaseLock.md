---
id: TwoPhaseLock
aliases: []
tags: []
---

# Two-Phase Lock Protocol 

A transaction is said to follow the **two-phase locking protocol** if all locking operations precede the first unlock operation in the transaction.

## Transaction Phases

Transactions following the two-phase locking protocol can be divided into two phases:
    - **Growing Phase**: In this phase, a transaction can obtain locks but cannot release any lock.
    - **Shrinking Phase**: In this phase, a transaction can release locks but cannot obtain any new lock.
    
## Two-Phase Lock Downsides
    
The two-phase locking protocol, while ensuring serializability, still has some downsides:
    - [[Deadlock]]
    - [[Starvation]]
