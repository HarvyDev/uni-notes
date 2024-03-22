---
id: Conservative2PL
aliases: []
tags: []
---

# Conservative Two-Phase Lock Protocol

This protocol is a variation of the basic two-phase locking protocol.

This variation requires the transaction to acquire all locks it will need at the beginning. This means that a transaction has to declare a read set and a write set before it starts its execution. If the transaction cannot acquire all locks it needs, it will abort and not lock any data.

This protocol is called **conservative** because it is conservative in acquiring locks. It acquires all locks it needs at the beginning and does not release any lock until the end. This is in contrast to the basic two-phase locking protocol where a transaction can release locks before it completes.

Although this protocol **prevents deadlocks**, it is still unpractical because it requires a transaction to know all the data items it will access before it starts execution. This is not always possible in real-world scenarios.

