---
id: Procedures
aliases: []
tags: []
---

# Procedures

A procedure is a database object similar to a function. The key **differences** are:
    - **Procedures do not return values.**
    - ** Procedures are called using the `CALL` statement.**
    - ** A procedure can commit and rollback transactions during its execution.**

Procedures are used to perform a set of operations on the database, for example, to insert, update, or delete records.

## Procedure Creation

Procedures are created using the `CREATE PROCEDURE` statement. They can also be created using the `CREATE OR REPLACE PROCEDURE` statement that, in case of a procedure with the same name already existing, replaces its behaviour.

## Parameters

Just like functions, procedures also take parameters. The syntax is the same as functions and is shown in [[Functions#Parameters]].

### Example Procedure 

```SQL
CREATE PROCEDURE insert_student(student_id INTEGER, student_name VARCHAR, student_age INTEGER) AS $$
BEGIN
    INSERT INTO student(id, name, age) VALUES (student_id, student_name, student_age);
END;
$$ LANGUAGE plpgsql;
``` 

### Example Procedure Call

```SQL
CALL insert_student(1, 'John Doe', 20);
```

