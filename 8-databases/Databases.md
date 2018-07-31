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
			ON tab


 