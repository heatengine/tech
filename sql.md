# SQL
## Queries
```
SELECT column1, column2, ... FROM table_name;
SELECT DISTINCT column1 FROM table_name;
SELECT * FROM table_name;
SELECT column1, column2, ... FROM table_name WHERE condition;
SELECT column1, column2, ... FROM table_name ORDER BY column1, column2, ... ASC|DESC;
SELECT TOP number|percent column_name(s) FROM table_name WHERE condition;
(=, <, >, <=, >=, <>, BETWEEN, LIKE, IN)
(AND, OR, NOT)
(ASC, DESC)
(IS NULL, IS NOT NULL)
(IS NULL, IS NOT NULL)
(MIN(), MAX())

INSERT INTO table_name (column1, column2, column3, ...) VALUES (value1, value2, value3, ...);
INSERT INTO table_name VALUES (value1, value2, value3, ...);

UPDATE table_name SET column1 = value1, column2 = value2, ... WHERE condition;

DELETE FROM table_name WHERE condition;
DELETE FROM table_name; //delete all


```