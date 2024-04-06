---
id: Functions
aliases: []
tags: []
---

# Functions

PostgreSQL provides four kinds of functions:
    - **Query Language Functions** (Functions written in SQL)
    - **Procedural Language Functions** (Functions written in PL/pgSQL, PL/Python, PL/Perl, etc.)
    - **C Language Functions** (Functions written in C)

**We are going to be focusing on Procedural Language Functions, written in PL/pgSQL.**

## Function Creation

Functions are created using the `CREATE FUNCTION` that simply creates a function, or `CREATE OR REPLACE FUNCTION` that redefines a function, in case there is already with that name.

## Parameters

Functions take parameters composed of a name, which is optional, and a type. In case the name is not provided, the parameters are accessed by their position in the argument list of the function declaration, like `$1`, for example.

## Returning 

Functions in PostgreSQL must have a return type. This is specified by the `RETURNS` keyword followed by the type of the return value. We return values using the `RETURN` keyword.

### Returning Primitve Types

The return type can be any primitive type, such as `INTEGER`, `VARCHAR`, `BOOLEAN`, etc. We can also specify the return type as `VOID` if we don't want the function to return anything.

### Returning Multiple Values

Functions can also return multiple values. In that case, we can use the `SETOF <type>` syntax. For example, if we wanted to return all student table entries with the name "Francisco" we would do:

#### Example Function 

If we have a table `student` with the following schema:

```SQL 
CREATE TABLE student (
    id SERIAL PRIMARY KEY,
    name VARCHAR(20),
    age INTEGER
);
```

We can create a function that returns the name of the student with the given `id`:

```SQL
CREATE FUNCTION get_student_name(student_id INTEGER) RETURNS VARCHAR(20) AS $$
BEGIN 
    RETURN (SELECT name FROM student WHERE id = student_id);
END;
$$ LANGUAGE plpgsql;
```

In this case, we are returning a single value, so we use the `RETURN` keyword to return the result of the query.

```SQL
CREATE FUNCTION get_students_by_name(student_name VARCHAR(10)) RETURNS SETOF student as $$
BEGIN
	RETURN QUERY
	SELECT * FROM student WHERE name = student_name;
END;
$$ LANGUAGE plpgsql;
```

In this case, because we returning a set of rows, we use the `RETURN QUERY` keyword to return the result of the query.


