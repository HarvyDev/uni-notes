---
id: LoopingStatements
aliases: []
tags: []
---

# Looping Statements

In PostgreSQL, looping statements are used to execute a block of code multiple times. Some of the looping statements available in PostgreSQL are:
- `LOOP` statement
- `FOR` loop
- `WHILE` loop
- `REPEAT` loop

## LOOP Statement

The `LOOP` statement is used to execute a block of code repeatedly. The loop will continue until an `EXIT` or `RETURN` statement is encountered. The syntax of the `LOOP` statement is as follows:

```sql
LOOP
    -- statements
END LOOP;
```

## FOR Loop

Just like in other programming languages, the `FOR` loop is used to iterate over a range of values. The loop will continue until the loop counter reaches the end value or an `EXIT` or `RETURN` statement is encountered. Its syntax is as follows:

```sql
FOR loop_counter IN [REVERSE] start_value..end_value [BY step_value] LOOP
    -- statements
END LOOP;
```

## WHILE Loop

The while loop is used to execute a block of code repeatedly as long as a condition is true. The syntax of the `WHILE` loop is as follows:

```sql
WHILE condition LOOP
    -- statements
END LOOP;
```

## REPEAT Loop

The `LOOP`statement is used to execute a block of code just like the other loops, but the condition is checked at the end of the loop, which means that the loop will always execute at least once. The syntax of the `REPEAT` loop is as follows:

```sql
REPEAT
    -- statements
UNTIL condition
END LOOP;
```
