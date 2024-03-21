---
id: WaitDie
aliases: []
tags: []
---

# Wait-Die Scheme

The Wait-Die algorithm is a deadlock prevention scheme. The algorithm makes use of timestamps to prevent deadlocks from occurring in a multi-user database environment. The concept is that transactions with older timestamps are given priority to access a resource, and transactions with newer timestamps are forced to wait.

```
If TS(Ti) < TS(Tj), then transaction Ti is older than transaction Tj, so it is allowed to wait.

Otherwise, if TS(Ti) > TS(Tj), transaction Ti is younger than transaction Tj and is forced to die. 
```

The aborted transaction will be restarted later with the **same** [[Timestamp]].


