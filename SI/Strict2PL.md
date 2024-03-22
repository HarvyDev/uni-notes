---
id: Strict2PL
aliases: []
tags: []
---

# Strict Two-Phase Lock Protocol

Strict Two-Phase Lock Protocol is the most used in practice. It is a stricter version of the basic [[TwoPhaseLock]] protocol.

This version of the 2PL protocol guarantees strict schedules.

In this variation, a transaction T does not release any of its exclusive (write) locks until after it commits or aborts. Hence, no other transaction can read or write an item that is written by T unless T has committed, leading to a strict schedule for recoverability.

This variation **is not [[Deadlock]] free**.
