---
id: Rigorous2PL
aliases: []
tags: []
---

# Rigorous Two-Phase Lock Protocol

The Rigorous Two-Phase Lock Protocol is a variation of the basic [[TwoPhaseLock]] protocol. It is a stricter version of the basic 2PL protocol which also guarantees strict schedules.

In this variation, a transaction T does not release any of its locks until after it commits or aborts.

