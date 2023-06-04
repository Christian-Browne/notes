# PostgreSQL

## Commands

`\l`

- view all databases

`\c [name]`

- Connect to database

`\d`

- Find relations and tables in database

`\d [name]`

- Go inside the table

`Ctrl + c`

- Escape query

---

You can update ‘on conflict’. If you insert a dup. value just say update on insert (upset)

### If you want to see edits

- Return row you edited at the end of query to see what you’ve done/updated
- `RETURN title, image, id, type`
- Or do `RETURN *`

You can add DEFAULT values as well

## Pagination

- When selecting rows from table using LIMIT it is best to use `WHERE id > #` instead of using `OFFSET` because it might skip a certain value using offset because data is being added and deleted
- TIP: id will always increment even if you delete a row

EVERY TABLE WILL HAVE A PRIMARY KEY
IS HOW YOU WILL INDEX THE TABLE
EX. ID WILL BE A PRIMARY KEY
