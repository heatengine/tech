# SQL
## Queries
```
SELECT column1, column2, ... FROM table_name;
SELECT DISTINCT column1 FROM table_name;
SELECT * FROM table_name;
SELECT column1, column2, ... FROM table_name WHERE condition;
SELECT column1, column2, ... FROM table_name ORDER BY column1, column2, ... ASC|DESC;
SELECT TOP number|percent column_name(s) FROM table_name WHERE condition;
SELECT column_name(s) FROM table_name WHERE column_name IN (value1, value2, ...);
SELECT column_name(s) FROM table_name WHERE column_name BETWEEN value1 AND value2;
SELECT column_name AS alias_name FROM table_name; // (ALIAS)
SELECT column_name(s) FROM table_name WHERE condition GROUP BY column_name(s) ORDER BY column_name(s);
SELECT column_name(s) FROM table_name WHERE condition GROUP BY column_name(s) HAVING condition ORDER BY column_name(s);

(=, <, >, <=, >=, <>, BETWEEN, LIKE, IN)
(AND, OR, NOT)
(ASC, DESC)
(IS NULL, IS NOT NULL)
(IS NULL, IS NOT NULL)
(MIN(), MAX())
(LIKE (%, _))

INSERT INTO table_name (column1, column2, column3, ...) VALUES (value1, value2, value3, ...);
INSERT INTO table_name VALUES (value1, value2, value3, ...);

UPDATE table_name SET column1 = value1, column2 = value2, ... WHERE condition;

DELETE FROM table_name WHERE condition;
DELETE FROM table_name; //delete all


```

## Wildcards
```
*   zero or more character
?   a single character
[]  any single character within the brackets  ab[cd]ef
!   any character not in the brackets         ab[!cd]ef
-   a range of characters                     ab[c-g]ef
#   any single numeric character
```

## Joins
- (INNER) JOIN: Returns records that have matching values in both tables
- LEFT (OUTER) JOIN: Returns all records from the left table, and the matched records from the right table
- RIGHT (OUTER) JOIN: Returns all records from the right table, and the matched records from the left table
- FULL (OUTER) JOIN: Returns all records when there is a match in either left or right table
```
// INNER JOIN
SELECT column_name(s)
FROM table1
INNER JOIN table2
ON table1.column_name = table2.column_name;

     ****   ****
  *      ***      *
*      *******      *
*      *******      *
  *      ***      *
     ****   ****

// LEFT JOIN
SELECT column_name(s)
FROM table1
LEFT JOIN table2
ON table1.column_name = table2.column_name;

     ****   ****
  **********      *
**************      *
**************      *
  **********      *
     ****   ****

// RIGHT JOIN
SELECT column_name(s)
FROM table1
RIGHT JOIN table2
ON table1.column_name = table2.column_name;

     ****   ****
  *      **********
*      **************
*      **************
  *      **********
     ****   ****

// FULL JOIN
SELECT column_name(s)
FROM table1
FULL OUTER JOIN table2
ON table1.column_name = table2.column_name

     ****   ****
  *****************
*********************
*********************
  *****************
     ****   ****
```

## Self Join
```
SELECT column_name(s)
FROM table1 T1, table1 T2
WHERE condition; // condition between 2 tables
```

## UNION
```
// Distinct
SELECT column_name(s) FROM table1
UNION
SELECT column_name(s) FROM table2;

// Union ALL
SELECT column_name(s) FROM table1
UNION ALL
SELECT column_name(s) FROM table2;

```

## Exist
```
SELECT column_name(s)
FROM table_name
WHERE EXISTS
(SELECT column_name FROM table_name WHERE condition);
```

## ANY ALL
- The ANY and ALL operators are used with a WHERE or HAVING clause.
- The ANY operator returns true if any of the subquery values meet the condition.
- The ALL operator returns true if all of the subquery values meet the condition.
```
SELECT column_name(s)
FROM table_name
WHERE column_name operator ANY/ALL
(SELECT column_name FROM table_name WHERE condition);
```

## INTO
- Copied into new table
```
SELECT *
INTO newtable [IN externaldb]
FROM oldtable
WHERE condition;
```

## INSERT INTO SELECT
```
INSERT INTO table2
SELECT * FROM table1
WHERE condition;
```

## CASE
```
CASE
    WHEN condition1 THEN result1
    WHEN condition2 THEN result2
    WHEN conditionN THEN resultN
    ELSE result
END;
```

## Stored Procedure
```
CREATE PROCEDURE procedure_name
AS
sql_statement
GO;

EXEC procedure_name;

// Stored Procedure With One Parameter
CREATE PROCEDURE SelectAllCustomers @City nvarchar(30)
AS
SELECT * FROM Customers WHERE City = @City
GO;

// Stored Procedure With Multiple Parameters
CREATE PROCEDURE SelectAllCustomers @City nvarchar(30), @PostalCode nvarchar(10)
AS
SELECT * FROM Customers WHERE City = @City AND PostalCode = @PostalCode
GO;

EXEC SelectAllCustomers @City = 'London', @PostalCode = 'WA1 1DP';
```

## OTHER SYNTAX
```
CREATE DATABASE databasename;
DROP DATABASE databasename;
BACKUP DATABASE databasename TO DISK = 'filepath';

CREATE TABLE table_name (
    column1 datatype,
    column2 datatype,
    column3 datatype,
   ....
);

DROP TABLE table_name;
ALTER TABLE table_name ADD column_name datatype;

CREATE TABLE table_name (
    column1 datatype constraint,
    column2 datatype constraint,
    column3 datatype constraint,
    ....
);
/*
NOT NULL - Ensures that a column cannot have a NULL value
UNIQUE - Ensures that all values in a column are different
PRIMARY KEY - A combination of a NOT NULL and UNIQUE. Uniquely identifies each row in a table
FOREIGN KEY - Uniquely identifies a row/record in another table
CHECK - Ensures that all values in a column satisfies a specific condition
DEFAULT - Sets a default value for a column when no value is specified
INDEX - Used to create and retrieve data from the database very quickly
*/


```





<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>

- specialization
- generalization
- transactions problems (concurrency)
- normalization
- aggregation
- 