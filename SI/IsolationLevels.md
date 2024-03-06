---
id: IsolationLevels
aliases: []
tags: []
---

# Transaction Support in SQL 


With SQL, there is no explicit Begin_Transaction statement. Transaction initiation is done implicitly when particular SQL statements are encountered. However, every transaction must have an explicit end statement, which is either a COMMIT or a ROLLBACK. Every transaction has certain characteristics attributed to it. These characteristics are specified by a SET TRANSACTION statement in SQL. The characteristics are the **access mode**, the **diagnostic area size** and the **isolation level**.

The **access mode** can be specified as READ_ONLY or READ_WRITE. The default is READ_WRITE, unless the isolation level of READ_UNCOMMITTED is specified, in which case READ_ONLY is assumed. A mode of READ WRITE allows select, update, insert, delete, and create commands to be executed. A mode of READ ONLY, as the name implies, is simply for data retrieval.

The **diagnostic area size** option, DIAGNOSTIC SIZE n, specifies an integer value n, which indicates the number of conditions that can be held simultaneously in the diagnostic area. These conditions supply feedback information (errors or exceptions) to the user or program on the n most recently executed SQL statements.

The **isolation level** option in specified using the statement ISOLATION LEVEL <isolation>, where the value for <isolation> can be READ UNCOMMITTED, READ COMMITTED, REPEATABLE READ, or SERIALIZABLE. The default isolation level is SERIALIZABLE, although some systems use READ COMMITTED as their default. The use of the term SERIALIZABLE here is based on not allowing violations that cause dirty read, unrepeatable read, and phantoms. If a transaction executes at a lower isolation level than SERIALIZABLE, then one or more of the following three violations may occur:
    1. Dirty read.
    2. Nonrepeatable read.
    3. Phantoms.

[[ConcurrencyProblems#Concurrency Problems]]

| Isolation Level | Dirty Read | Nonrepeatable Read | Phantom | 
|-----------------|------------|--------------------|---------|
| READ UNCOMMITTED| Yes        | Yes                | Yes     |
| READ COMMITTED  | No         | Yes                | Yes     |
| REPEATABLE READ | No         | No                 | Yes     |
| SERIALIZABLE    | No         | No                 | No      |
