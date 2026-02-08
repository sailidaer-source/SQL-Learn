# Inroduction to Relational Database in SQL
## What is the Information Schema?
The Information Schema is a SQL standard system database/view built into most relational database management systems (RDBMS) like MySQL,  SQL Server, PostgreSQL, and SQLite. It stores metadata—data about the database itself, such as:
- Names of databases, tables, and columns
- Data types of columns
- Table/column permissions
- Constraints
- Indexes and table relationshipss 

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
- Create a table universities with three text columns: university_shortname, university, and university_city.

```
-- Create a table for the universities entity type


Create Table universities(
    university_shortname text,
    universities text,
    university_city text
);



-- Print the contents of this table
SELECT * 
FROM universities
```

### ADD a COLUMN with ALTER TABLE
- Alter professors to add the text column university_shortname
```


-- Add the university_shortname column
ALTER TABLE professors
ADD COLUMN university_shortname text;

-- Print the contents of this table
SELECT * 
FROM professors
```
### RENAME and DROP COLUMNs 
- Rename the organisation column to organization in affiliations.

```
-- Rename the organisation column
ALTER TABLE affiliations
RENAME column organisation TO organization;
```

- Delete the university_shortname column in affiliations.

```
-- Delete the university_shortname column
Alter TABLE affiliations
DROP COLUMN university_shortname;
```

### Migrate data with INSERT INTO SELECT DISTINCT

- Insert all DISTINCT professors from university_professors into professors. Print all the rows in professors.

```
-- Insert unique professors into the new table
INSERT INTO professors 
SELECT DISTINCT firstname, lastname, university_shortname 
FROM university_professors;

-- Doublecheck the contents of professors
SELECT * 
FROM professors;
```

- Insert all DISTINCT affiliations into affiliations from university_professors.

```
-- Insert unique affiliations into the new table
INSERT INTO affiliations 
Select distinct firstname, lastname, function, organization 
FROM university_professors;

-- Doublecheck the contents of affiliations
SELECT * 
FROM affiliations;
```

### Delete tables with DROP TABLE

- Delete the university_professors table.

```
-- Delete the university_professors table
DROP Table university_professors;
```


































