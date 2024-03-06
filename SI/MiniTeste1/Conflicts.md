---
id: Conflicts
aliases: []
tags: []
---


# Transaction Conflicts

Two operations of a schedule are in **conflict** if they satisfy all three of the following conditions:
    1. They belong to **different transactions**.
    2. They access the **same item X**.
    3. At least one of the operations is a **write_item** operation.

Intuitively, two operations are conflicting if changing their order can result in a different outcome.

There are **two types of conflicts**:
    1. **Read-write** conflict: A read operation reads the value of an item before a write operation writes a new value to the item, resulting in a incorrect read value of the first operation.
    2. **Write-write** conflict: Two write operations write different values to the same item, resulting in the first value being lost.

These problems are called [[ConcurrencyProblems]].
