# SQL

-
-
## Lecture Overview
* Querying data using SQL
* Modifying data using SQL
* Creating Schema's
* Querying Relational Databases

-
-
### Querying Data

-
#### Simple Queries

Documentation
```sql
--Retrieves all the data from the table
SELECT * FROM <table>;

--Retrieves all the data from a specific column in the table
SELECT <column> FROM <table>;

--Retrieves all the data from the specific columns in the table
SELECT <column1>, <column2> FROM <table>;
```

Example
```sql
SELECT full_name, age, username FROM <table>;
```

```text
|full_name  |age|username |
---------------------------
|Kaleb Burd |24 |kburd    |
|Emma Watson|30 |hGranger |
|Tariq Hook |40 |CodeRhino|
```

-
#### Filtering w/ Comparisons
Documentation
```sql
--Retrieves all the data from the table where condition is true
SELECT * FROM <table> WHERE <condition>;

--Retrieves all the data from the table where both conditions are true
SELECT * FROM <table> WHERE <condition1> AND <condition2>;

--Retrieves all the data from the table where either condition is true
SELECT * FROM <table> WHERE <condition1> OR <condition2>;
```

Example
```sql
SELECT * FROM users where age < 40;
```

```text
|full_name  |age|username |
---------------------------
|Kaleb Burd |24 |kburd    |
|Emma Watson|30 |hGranger |
```

-
#### Filtering w/ Ranges
Documentation
```sql
--Retrieves all the data from the table where condition is true
SELECT * FROM <table> WHERE <column> IN (value1, value2);

--Retrieves all the data from the table where both conditions are true
SELECT * FROM <table> WHERE <column> BETWEEN <value1> and <value2>;
```

Example

```sql
SELECT * FROM users where age BETWEEN 25 AND 45;
```

```text
|full_name  |age|username |
---------------------------
|Emma Watson|30 |hGranger |
|Tariq Hook |40 |CodeRhino|
```

-
#### Filtering w/ Pattern Matching
Documentation
```sql
--Retrieves all the data from the table where column data end with pattern
SELECT * FROM <table> WHERE <column> LIKE "%<text>";

--Retrieves all the data from the table where column data starts with pattern
SELECT * FROM <table> WHERE <column> LIKE "<text>%";

--Retrieves all the data from the table where column data contains text
SELECT * FROM <table> WHERE <column> LIKE "%<text>%";
```

Example
```sql
SELECT * FROM users where username LIKE "r%";
```

```text
|full_name  |age|username |
---------------------------
|Tariq Hook |40 |CodeRhino|
```

-
#### Misc

```sql
--Gives column an alias in report
SELECT <column> AS <alias> FROM <table>;

--IS can be used interchangably with "="
SELECT * FROM <table> WHERE <column> IS <value>;

--NOT inverts a condition
SELECT * FROM <table> WHERE <column> IS NOT <value>;
```
