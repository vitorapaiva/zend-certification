# Definition

* Way of storing and retrieving data efficiently

# Keys

* Primary key: column of unique values that describe an entry in the data table

* Foreign key: primary key from another table; enables relational databases

# SQL

* Create table:
	CREATE TABLE tb1 (
		id INT NOT NULL PRIMARY KEY,
		field1 VARCHAR(100)
		field2 CHAR(32) NOT NULL
	)

	* Note: null is not the same as the number "0", "false", or an empty string...it represents "no value" or "missing value"

* Read data:
	SELECT field1, field2 from tb1
		where field3 = 'value'

* Insert data:
	INSERT INTO tb1
		(field1, field2, field3) VALUES
		('value1', 2, 'value3')

* Update data:
	UPDATE tb1
		SET field1 = 'value1', field2='value2'
		WHERE field3='value3'

* Delete data:
	DELETE FROM tb1 WHERE field1='value1'
	DROP TABLE tb1
	DROP DATABASE dbName

* Sorting (order by)
	* Order by ascending (ASC) or descending (DESC)
		SELECT * FROM tb1 ORDER BY col DESC

* Grouping (group by)
	* In general, the columns used to group by must be included in the select list
		SELECT col1, col2 FROM tb1
			GROUP BY col1

* Aggregation
	
	AVG() Average value
	COUNT() Number of elements
	DISTINCT COUNT() Number of distinct elements
	MIN() Minimal value
	MAX() Maximum value
	SUM() Sum of values

# Joins

* Inner join
	
	Ex: returns all entries in tb1 and tab2 linked using the primary/foreign key, and that fulfill the where clause in tab1

		SELECT * FROM tab1
			INNER JOIN tab2
			ON tab1.primkey = tab2.forkey
			WHERE tab1.col1 = 'value1'

* Left Join

	Ex: All data from the "left" table is used, even if there is no match in the "right" table
		SELECT * FROM tab1
			LEFT JOIN tab2
			ON tab1.primkey=tab2.forkey
			WHERE tab1.col1='value'

* Right Join
	Ex: All data from the "right" table is used, even if there is no match in the "left" table
		SELECT * FROM tab1
			RIGHT JOIN tab2
			ON tab1.primkey = tab2.forkey
			WHERE tab2.col1='value1'

# Prepared statements

* Similar in concept to templates - contain compiled code used to run common sql operations
	* Advantages:
		* Query only parsed once, but allows for multiple executions, with same or different parameters (perfomance consideration)

		* Related parameters do not need to be quoted (security consideration)

	* Only feature PDO will emulate for adapters that do not support prepared statements

# Transacations

* Combines individual SQL operations into one

* Usually start with begin or begin transaction

* Execute the transaction using commit

* Cancel the transaction using rollback 

# PDO (PHP Data Objects Extension)

* Provides interface for accessing databases - a data-access abstraction layer
	* Can use the same functions to manipulate databases, regardless of DB type
		* Not for data type or SQL abstraction

* Must use database-specific PDO adapters to access a DB server

	* Database adapters implementing PDO interfaces expose database-specific features as regular extensions functions

* Runtime configuration options
	* pdo.dsn.* in php.ini
	* PDO::setAttribute()

* Set of predefined class constants available

* Error settings available: Silent, Warning and Exception

* Connections

	* Connections are made by creating and instance of the PDO class, *not* by creating instances of PDOStatement or PDOException
	* Ex: CONNECTING TO MYSQL
		<?php
			$dbh=new PDO('mysql:host=localhost;dname=t$user,$pass)
		?>

# Queries

	PDO::query()

		Executes a SQL statement, in a single function call, and returns the resulting values as a PDOStatement object

		Need to retrieve all data in the result set before calling query function again

	Fetch

		PDOStatement->setFetchMode
			Sets the default fetch mode(Ex: Fetch_Column)

			* Common fetch modes: PDO::FETCH*:_ASSOC,_OBJ,CLASS
			* Default fetch mode: PDO::FETCH_BOTH

	Transacations

		PDO::beginTransacation()
			Turns off autocommit mode for changes made to the database

		PDO::commit()
			Call to end transacation and commit changes

		PDO::rollBack()
			Call to reserve all changes made to the database and reactivate autocommit mode