---
id: TransactionStates
aliases: []
tags: []
---

# Transaction States


A transaction goes into an **active state** immediately after it starts execution, where it can execute its READ and WRITE operations. When the transaction ends, it moves to the **partially committed state**. At this point, some recovery protocols need to ensure that a system failure will not result in an inability to record the changes of the transaction permanently (usually be recording changes in the system log). Once this check is successful, the transaction is said to have reached its commit point and enters the **committed state**. 

However, a transaction can go to the **failed state** if one of the checks fails or if the transaction is aborted during its active state. The transaction may then have to be rolled back to undo the effect of its WRITE operations on the database. The **terminated state** corresponds to the transaction leaving the system. The transaction information that is maintained in system tables while the transaction has been running is removed when the transaction terminates. Failed or aborted transactions may be restarted later as brand new transactions.

[[Recoverability#Characterizing Schedules Based on Recoverability]]

The following figure shows a state transition diagram that illustrates how a transaction moves through its execution states.

![Transaction States](TransactionStates.png)
**Figure 1**: Transaction States Diagram
