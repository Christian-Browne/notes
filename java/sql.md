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

---

- COUNT

SELECT `<column_name>` COUNT(\*) FROM `<table_name>`
SELECT `DISTINCT(<column_name>)` COUNT(\*) FROM `<table_name>`

- WHERE

SELECT \* FROM `<table_name>` WHERE `<coulmn_value>` = `<value>`

- LIKE
  - Where value is simillar
- GROUP BY
- ORDER BY
- LIMIT

## JOIN

> 💡 Joins two tables based on a related column (primary/foreign key)

- Will only join if the two keys match

- `JOIN` by the **_shared_** foreign and primary key
- the `JOIN` operation is used to combine rows from two or more tables based on a related column between them. It allows you to retrieve data from multiple tables in a single query, creating a virtual table by merging the selected rows.

```postgreSQL
SELECT recipes.title, recipes.body, recipes_photos.url FROM recipes
INNER JOIN recipes_photos
ON recipes.recipe_id = recipes_photos.recipe_id
WHERE recipes.recipe_id = 1;
```

### How it _JOIN_ Works

The query starts with the `SELECT` statement, which specifies the columns we want to retrieve from the tables. In this case, we want to retrieve the "title" and "body" columns from the "recipes" table and the "url" column from the "recipes_photos" table.

The `FROM` clause indicates the initial table from which we retrieve data, which is the "recipes" table. What you put after `FROM` will be on the left

The `INNER JOIN` clause is used to combine rows from the "recipes" and "recipes_photos" tables based on a specified condition.

The `ON` keyword follows the `INNER JOIN` clause and specifies the condition for the join. In this case, the condition is "recipes.recipe_id = recipes_photos.recipe_id", which means that the "recipe_id" column in the "recipes" table should match the "recipe_id" column in the "recipes_photos" table.

The `WHERE` clause filters the rows based on a specific condition. Here, we want to retrieve the information for a particular recipe with the ID of 1. So, the condition "recipes.recipe_id = 1" ensures that only rows with a recipe ID of 1 are selected.

To explain how the join works:

- The query retrieves data from the "recipes" table and matches it with corresponding data from the "recipes_photos" table.
- The join condition "recipes.recipe_id = recipes_photos.recipe_id" ensures that only rows with matching recipe IDs are combined.
- **_This means that for each row in the "recipes" table with a recipe ID of 1, the query will find the corresponding row in the "recipes_photos" table that has the same recipe ID._**
- The result of the join is a combined result set that includes the "title" and "body" columns from the "recipes" table and the "url" column from the "recipes_photos" table, for the recipe with the ID of 1.

In summary, the query retrieves the title and body columns from the "recipes" table and the url column from the "recipes_photos" table, combining them based on the recipe ID. It then filters the results to only include the data for the recipe with ID 1.

---

## Constraints

- This makes sure that the type column can 0only contain these values

```sql
ALTER TABLE ingredients
ADD CONSTRAINT type_check_enum
CHECK ( type IN ('vegetable', 'meat', 'fruit', 'other') );
```

---

## Distinct

- Returns the distinct value (ff there are many of the same values returns only one of them)

```sql
SELECT DISTINCT <column_name> FROM <table_name>;
```
