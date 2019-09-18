# SQL NOTES

## DQL

### SELECT
e.g.  SELECT <Column_name> FROM <table_name>
      SELECT * FROM Books;

    Asterisk means all collumns.
    Semi-colon terminates the statement (like a fullstop in a sentence)

-Alisasing Column Names
  SELECT <Column_name> AS <alias> FROM <table_name>

-Finding Data You Want
  SELECT <Column_name> FROM <table_name> WHERE <Condition>;

-Equality Operator
  Find all rows that a given value matches a column's value

  SELECT <Column_name> FROM <table_name> WHERE <Column_name> = <value>

  Find all rows that a given value doesn't match a column's value

  SELECT <Column_name> FROM <table_name> WHERE <Column_name> != <value>

  SELECT <Column_name> FROM <table_name> WHERE <Column_name> <> <value>

-Relational Operator
  '<' less than
  '<=' less than or equal to
  '>' more than
  '>=' more than or equal to

-More than one Condition
You can compare multiple values in a WHERE condition. If you want to test that both conditions are true use the 'AND' keyword, or either conditions are true use the 'OR' keyword

SELECT <columns> FROM <table> WHERE <condition 1> AND <condition 2> ...;

SELECT <columns> FROM <table> WHERE <condition 1> OR <condition 2> ...;

-Searching in a set of values

  SELECT <columns> FROM <table> WHERE <column> IN (<value 1>, <value 2>, ...

-Searching within a range of values

  SELECT <columns> FROM <table> WHERE <column> BETWEEN <lesser value> AND <greater value>;

-Pattern Matching

  Placing the percent symbol (%) any where in a string in conjunction with the LIKE keyword will operate as a wildcard. Meaning it can be substituted by any number of characters, including zero!

  SELECT <columns> FROM <table> WHERE <column> LIKE <pattern>;

-Missing values

  SELECT * FROM <table> WHERE <column> IS NULL

-Ordering columns

  Ordering by a single column criteria:

  SELECT * FROM <table name> ORDER BY <column> [ASC|DESC];

  ASC is used to order results in ascending order.

  DESC is used to order results in descending order.

-Limiting results
  To limit the number of results returned, use the TOP keyword.

  SELECT TOP <# of rows> <columns> FROM <table>
### INSERT

  Insert data into empty table

  INSERT INTO <Column_name>
  VALUES <DATA>

### UPDATE

  UPDATE <table_name>
  SET <column_name> = value1, <Column_name2> = value2
  WHERE <Condition>

### DELETE

DELETE FROM <table_name>
WHERE <condition>

##DDL

###CREATE

  CREATE TABLE <table_name>(column1 [datatype], column2 [datatype], column3 [datatype])

### ALTER

  ALTER <table_name>
  ADD <column_name> [datatype]

  ALTER <table_name>
  DROP COLUMN <column_name>

### DML

Aggregate Functions:

SUM SUM(OrderTotal) – grand total of a column for all rows selected

AVG AVG(UnitPrice) – average of the column for all rows selected

MIN MIN(UnitPrice) – for the smallest value in a column for all rows

Max MAX(UnitPrice) - for the largest value in a column for all rows

COUNT COUNT(*) – for the number of NOT NULL rows selected. If * is used then all rows are counted, regardless of NULL/NOTNULL.

These must be used in conjunction with a GROUP BY clause.

HAVING is essentially a WHERE condition used only for when a GROUP BY clause is in effect. It limits the data in the query based on a given condition.
