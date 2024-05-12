---
id: Triggers
aliases: []
tags: []
---

# Trigger

## What is a trigger in DBMS?

A **trigger** is procedural code that is automatically executed in response to certain events on a particular table or view in a database. These events can be `INSERT`, `UPDATE`, or `DELETE`.

Triggers are typically used to enforce data integrity constraints, implement business rules, or automate certain tasks. They are defined to execute either **before**, **after** or **instead of** (in the case of views) the event that triggers them.

Triggers allow the user to access the `NEW` and `OLD` records, which contain the **new** and **old** values of the row that triggered the event. For example, in an update, the `OLD` record contains the values before the update, and the `NEW` record contains the values changed by the update.

The function that is executed by the trigger has to return the type `TRIGGER` and has to return the `NEW` record.

## Syntax

```sql 
CREATE TRIGGER trigger_name
{BEFORE | AFTER} {INSERT | UPDATE | DELETE}
ON table_name
FOR EACH ROW
EXECUTE FUNCTION function_name();
```
