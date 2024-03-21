---
id: Deadlock
aliases: []
tags: []
---


# Deadlock

**Deadlock** occurs when each transaction T in a set of two or more transactions is waiting for some item that is locked by some other transaction T' in the set. Hence, each transaction in the set is in a waiting queue, waiting for one of the other transactions in the set to release the lock on an item. But because the other transaction is also waiting, it will never release the lock. And that is called a **deadlock**.

There are several methods to prevent deadlocks, such as:
    - [[DeadlockPrevention]]
    - [[DeadlockDetection]]
    
