# Inroduction to Relational Database in SQL
## What is the Information Schema?
The Information Schema is a SQL standard system database/view built into most relational database management systems (RDBMS) like MySQL,  SQL Server, PostgreSQL, and SQLite. It stores metadata—data about the database itself, such as:
- Names of databases, tables, and columns
- Data types of columns
- Table/column permissions
- Constraints
- Indexes and table relationships

### Use Information Schema to Count Columns in table
```
SELECT COUNT(*) AS column_count
FROM information_schema.COLUMNS
WHERE table_schema = 'your_database_name'  -- Name of your database
  AND table_name = 'your_table_name';      -- Name of your table
```
### Create your frist TABLEs

- Create a table professors with two text columns: firstname and lastname.
```
-- Create a table for the professors entity type
CREATE TABLE professors (
firstname text,
 lastname text
);

-- Print the contents of this table
SELECT * 
FROM professors
```




