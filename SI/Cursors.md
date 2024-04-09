---
id: Cursors
aliases: []
tags: []
---

# Cursors

Rather than executing a whole query at once, it is possible to set up a **cursor** that encapsulates the query, and then read the query result a few rows at a time. 

## What is a Cursor?

A cursor is a database object that allows you to retrieve rows from a result set one at a time. For example, when you issue a `SELECT` statement, the result set is returned all at once. That is where cursors come in. You can use a cursor to read the rows one by one so you can perform complex logic based on the values of the rows.

## Declare a Cursor

```sql 
cursor_name CURSOR FOR query
``` 

## Open a Cursor

Once you have declared a cursor, you can open it to read rows from the result set.

```sql
OPEN cursor_name
```

## Using Cursors

### Fetching Rows

The `FETCH` statement is used to retrieve rows from a cursor. We can set the direction of the cursor to `NEXT` or `PRIOR` to fetch the next or previous row respectively. By omission, the cursor will fetch the next row.

```sql 
FETCH cursor_name INTO variable_list
```

### Looping through a Cursor

We can use a for loop to iterate through the rows of a cursor. The loop will continue until there are no more rows to fetch. The for loop **automatically opens and closes the cursor**. To iterate through a cursor, we need to declare a variable to hold the row fetched from the cursor. That variable is of type `RECORD`.

```sql
DECLARE
    cursor_name CURSOR FOR query;
    record_name RECORD;
BEGIN 
    FOR record_name IN cursor_name LOOP
        -- do something
    END LOOP;
END;
```

### Closing a Cursor

`CLOSE` closes the portal underlying an open cursor. This can be used to release resources earlier than end of transaction, or to free up the cursor variable to be opened again.

```sql
CLOSE cursor_name
```

