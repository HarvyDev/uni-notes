---
id: WoundWait
aliases: []
tags: []
---

# Wound-Wait Scheme

The Wound-Wait algorithm is a deadlock prevention scheme. It is based on the idea that the process requesting a resource with the lowest timestamp (oldest) will be granted access to the resource first.

In the Wound-Wait algorithm, each transaction is assigned a timestamp when it starts. When a transaction requests a resource, it compares its timestamp with the timestamp of the transaction currently holding the resource. If the requesting transaction has a lower transaction, it **wounds** the transaction holding the resource, which must then either release the resource or **wait** for the requesting transaction to release it first.

This algorithm helps to prevent deadlocks by ensuring that the transaction with the lowest priority does not have to wait for a resource.

``` 
If TS(Ti) < TS(Tj), then transaction Ti is older than transaction Tj, so we abort transaction Tj (Ti wounds Tj).

Otherwise, if TS(i) > TS(j), transaction Ti is younger than transaction Tj, so it is allowed to wait. 
```

The aborted transaction is restarted later with the **same** [[Timestamp]].
