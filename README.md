# SQL-Basics
### Mastering SQL Basics

##### Introduction to SQL
  SQL is a standard language for accessing and manipulating databases.

- What is SQL?
•	SQL stands for Structured Query Language
•	SQL lets you access and manipulate databases
•	SQL became a standard of the American National Standards Institute (ANSI) in 1986, and of the International Organization for Standardization (ISO) in 1987
What Can SQL do?
•	SQL can execute queries against a database
•	SQL can retrieve data from a database
•	SQL can insert records in a database
•	SQL can update records in a database
•	SQL can delete records from a database
•	SQL can create new databases
•	SQL can create new tables in a database
•	SQL can create stored procedures in a database
•	SQL can create views in a database
•	SQL can set permissions on tables, procedures, and views


Example Table:
Customer Id	Name	Salary
01	Shahin Alam	20000
02	Rudra Roy	15000
03	Mithun	30000

NOTE: Every table is broken up into smaller entities called fields. The fields in the Customers table consist of CustomerID, CustomerName, ContactName, Address, City, PostalCode and Country. A field is a column in a table that is designed to maintain specific information about every record in the table.
A record, also called a row, is each individual entry that exists in a table. For example, there are 91 records in the above Customers table. A record is a horizontal entity in a table.
A column is a vertical entity in a table that contains all information associated with a specific field in a table.

Some of The Most Important SQL Commands
•	SELECT - extracts data from a database
•	UPDATE - updates data in a database
•	DELETE - deletes data from a database
•	INSERT INTO - inserts new data into a database
•	CREATE DATABASE - creates a new database
•	ALTER DATABASE - modifies a database
•	CREATE TABLE - creates a new table
•	ALTER TABLE - modifies a table
•	DROP TABLE - deletes a table
•	CREATE INDEX - creates an index (search key)
•	DROP INDEX - deletes an index

Select:
For spacific column:
     SELECT column1, column2, ...
    FROM table_name;
For all column:

  SELECT * FROM Customers;

#####The SQL SELECT DISTINCT Statement

The SELECT DISTINCT statement is used to return only distinct (different) values.
SELECT DISTINCT column1, column2, ...
FROM table_name;
Count Distinct
By using the DISTINCT keyword in a function called COUNT, we can return the number of different countries.

Example:

SELECT COUNT(DISTINCT Country) FROM Customers;

The SQL WHERE Clause
The WHERE clause is used to filter records.
It is used to extract only those records that fulfill a specified condition.
SELECT column1, column2, ...
FROM table_name
WHERE condition;
Example:

SELECT * FROM Customers
WHERE Country='Mexico';

CustomerID	CustomerName	ContactName	Address	City	PostalCode	Country
2 	Ana Trujillo Emparedados y helados 	Ana Trujillo 	Avda. de la Constitución 2222 	México D.F. 	05021 	Mexico 
3 	Antonio Moreno Taquería 	Antonio Moreno 	Mataderos 2312 	México D.F. 	05023 	Mexico 
13 	Centro comercial Moctezuma 	Francisco Chang 	Sierras de Granada 9993 	México D.F. 	05022 	Mexico 
58 	Pericles Comidas clásicas 	Guillermo Fernández 	Calle Dr. Jorge Cash 321 	México D.F. 	05033 	Mexico 
80 	Tortuga Restaurante 	Miguel Angel Paolino 	Avda. Azteca 123 	México D.F. 	05033 	Mexico 

The SQL ORDER BY
The ORDER BY keyword is used to sort the result-set in ascending or descending order.

SELECT column1, column2, ...
FROM table_name
ORDER BY column1, column2, ... ASC|DESC;

To sort the table reverse alphabetically, use the DESC keyword:
Example;
Sort the products by ProductName in reverse order:

SELECT * FROM Products
ORDER BY ProductName DESC;

##### The SQL AND Operator
The WHERE clause can contain one or many AND operators.
The AND operator is used to filter records based on more than one condition, like if you want to return all customers from Spain that starts with the letter 'G':

Example 
Select all customers from Spain that starts with the letter 'G':

SELECT *
FROM Customers
WHERE Country = 'Spain' AND CustomerName LIKE 'G%';
SELECT column1, column2, ...
FROM table_name
WHERE condition1 AND condition2 AND condition3 ...;

The SQL OR Operator
The WHERE clause can contain one or more OR operators.
The OR operator is used to filter records based on more than one condition, like if you want to return all customers from Germany but also those from Spain:
Example 
Select all customers from Germany or Spain:
SELECT *
FROM Customers
WHERE Country = 'Germany' OR Country = 'Spain';
The NOT Operator
The NOT operator is used in combination with other operators to give the opposite result, also called the negative result.
In the select statement below we want to return all customers that are NOT from Spain:
Example 
Select only the customers that are NOT from Spain:
SELECT * FROM Customers
WHERE NOT Country = 'Spain';




AND vs OR
The AND operator displays a record if all the conditions are TRUE.
The OR operator displays a record if any of the conditions are TRUE.

And -OR combination
SELECT * FROM Customers
WHERE Country = 'Spain' AND (CustomerName LIKE 'G%' OR CustomerName LIKE 'R%');  

The SQL INSERT INTO Statement
The INSERT INTO statement is used to insert new records in a table
INSERT INTO table_name (column1, column2, column3, ...)
VALUES (value1, value2, value3, ...); 
Example:
INSERT INTO Customers (CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES ('Cardinal', 'Tom B. Erichsen', 'Skagen 21', 'Stavanger', '4006', 'Norway');
Example2.
INSERT INTO Customers (CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES
('Cardinal', 'Tom B. Erichsen', 'Skagen 21', 'Stavanger', '4006', 'Norway'),
('Greasy Burger', 'Per Olsen', 'Gateveien 15', 'Sandnes', '4306', 'Norway'),
('Tasty Tee', 'Finn Egan', 'Streetroad 19B', 'Liverpool', 'L1 0AA', 'UK');

The IS NULL Operator
The IS NULL operator is used to test for empty values (NULL values).
The following SQL lists all customers with a NULL value in the "Address" field:
Example 
SELECT CustomerName, ContactName, Address
FROM Customers
WHERE Address IS NULL;

Example2 
The IS NOT NULL Operator
The IS NOT NULL operator is used to test for non-empty values (NOT NULL values).
The following SQL lists all customers with a value in the "Address" field:
Example
SELECT CustomerName, ContactName, Address
FROM Customers
WHERE Address IS NOT NULL;

The SQL DELETE Statement
The DELETE statement is used to delete existing records in a table.
DELETE Syntax
DELETE FROM table_name WHERE condition; 
Note: Be careful when deleting records in a table! Notice the WHERE clause in the DELETE statement. The WHERE clause specifies which record(s) should be deleted. If you omit the WHERE clause, all records in the table will be deleted!
•	DELETE FROM patients WHERE first_name = 'Paul';
The SQL UPDATE Statement
The UPDATE statement is used to modify the existing records in a table.
UPDATE Syntax
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition; 
Note: Be careful when updating records in a table! Notice the WHERE clause in the UPDATE statement. The WHERE clause specifies which record(s) that should be updated. If you omit the WHERE clause, all records in the table will be updated!
The UPDATE statement is used to modify the existing records in a table.
Example
 
UPDATE Customers
SET ContactName = 'Alfred Schmidt', City= 'Frankfurt'
WHERE CustomerID = 1;

Operators
The following operators can be used in the WHERE clause:
 Equal, =
        SELECT * FROM customers
             WHERE customerID=2;
Greater Than, >
             SELECT * FROM customers
             WHERE customerID > 2;
Less Than, <
           SELECT * FROM customers
             WHERE customerID < 5;
Greater Than Or Equal To, >=
           SELECT * FROM customers
             WHERE customerID  >= 5;
Less Than Or Equal To, <=
	SELECT * FROM   WHERE customerID <= 5;
Not Equal, <> or != depending on sql version
   SELECT * FROM customers
             WHERE customerID  <> 5;
Between, inclusive range
     SELECT * FROM customers
             WHERE customerID  BETWEEN  2 AND 5;
Like, pattern search
SELECT * FROM customers
             WHERE customerName  LIKE  ‘v%’ ;
In, in a collection
SELECT * FROM customers
             WHERE customerName  IN  ‘victor’ ;

SQL JOIN
A JOIN clause is used to combine rows from two or more tables, based on a related column between them.
Let's look at a selection from the "Orders" table:
  SELECT Orders.OrderID, Customers.CustomerName, Orders.OrderDate
  FROM Orders
 INNER JOIN Customers ON Orders.CustomerID=Customers.CustomerID;
Output:
OrderID	CustomerName	OrderDate
10308	Ana Trujillo Emparedados y helados	9/18/1996
10365	Antonio Moreno Taquería	11/27/1996
10383	Around the Horn	12/16/1996
10355	Around the Horn	11/15/1996
10278	Berglunds snabbköp	8/12/1996
		
Different Types of SQL JOINs
Here are the different types of the JOINs in SQL:
•	(INNER) JOIN: Returns records that have matching values in both tables
•	LEFT (OUTER) JOIN: Returns all records from the left table, and the matched records from the right table
•	RIGHT (OUTER) JOIN: Returns all records from the right table, and the matched records from the left table
•	FULL (OUTER) JOIN: Returns all records when there is a match in either left or right table
                       
                         

SQL Self Join
A self join is a regular join, but the table is joined with itself.
Self Join Syntax
SELECT column_name(s)
FROM table1 T1, table1 T2
WHERE condition;
SQL Self Join Example
The following SQL statement matches customers that are from the same city:
Example 

SELECT A.CustomerName AS CustomerName1, B.CustomerName AS CustomerName2, A.City
FROM Customers A, Customers B
WHERE A.CustomerID <> B.CustomerID
AND A.City = B.City 
ORDER BY A.City;

The SQL UNION Operator
The UNION operator is used to combine the result-set of two or more SELECT statements.
•	Every SELECT statement within UNION must have the same number of columns
•	The columns must also have similar data types
•	The columns in every SELECT statement must also be in the same order
SELECT column_name(s) FROM table1
UNION
SELECT column_name(s) FROM table2

Demo Database
In this tutorial we will use the well-known Northwind sample database.
Below is a selection from the "Customers" table:
CustomerID	CustomerName	ContactName	Address	City	PostalCode	Country
1	Alfreds Futterkiste	Maria Anders	Obere Str. 57	Berlin	12209	Germany
2	Ana Trujillo Emparedados y helados	Ana Trujillo	Avda. de la Constitución 2222	México D.F.	05021	Mexico
3	Antonio Moreno Taquería	Antonio Moreno	Mataderos 2312	México D.F.	05023	Mexico
And a selection from the "Suppliers" table:
SupplierID	SupplierName	ContactName	Address	City	PostalCode	Country
1	Exotic Liquid	Charlotte Cooper	49 Gilbert St.	London	EC1 4SD	UK
2	New Orleans Cajun Delights	Shelley Burke	P.O. Box 78934	New Orleans	70117	USA
3	Grandma Kelly's Homestead	Regina Murphy	707 Oxford Rd.	Ann Arbor	48104	USA
________________________________________
________________________________________
SQL UNION Example
The following SQL statement returns the cities (only distinct values) from both the "Customers" and the "Suppliers" table:
Example; 
SELECT City FROM Customers
UNION
SELECT City FROM Suppliers
ORDER BY City;

SQL UNION ALL Example
The following SQL statement returns the cities (duplicate values also) from both the "Customers" and the "Suppliers" table:
Example

SELECT City FROM Customers
UNION ALL
SELECT City FROM Suppliers
ORDER BY City;

SQL UNION ALL With WHERE
The following SQL statement returns the German cities (duplicate values also) from both the "Customers" and the "Suppliers" table:
Example
SELECT City, Country FROM Customers
WHERE Country='Germany'
UNION ALL
SELECT City, Country FROM Suppliers
WHERE Country='Germany'
ORDER BY City;
The SQL GROUP BY Statement
The GROUP BY statement groups rows that have the same values into summary rows, like "find the number of customers in each country".
The GROUP BY statement is often used with aggregate functions (COUNT(), MAX(), MIN(), SUM(), AVG()) to group the result-set by one or more columns.
GROUP BY Syntax
SELECT column_name(s)
FROM table_name
WHERE condition
GROUP BY column_name(s)
ORDER BY column_name(s); 
Example
SELECT COUNT(CustomerID), Country
FROM Customers
GROUP BY Country;
Demo Database
Below is a selection from the "Orders" table in the Northwind sample database:
OrderID	CustomerID	EmployeeID	OrderDate	ShipperID
10248	90	5	1996-07-04	3
10249	81	6	1996-07-05	1
10250	34	4	1996-07-08	2
And a selection from the "Shippers" table:
ShipperID	ShipperName
1	Speedy Express
2	United Package
3	Federal Shipping
________________________________________
GROUP BY With JOIN Example
The following SQL statement lists the number of orders sent by each shipper:
Example
SELECT Shippers.ShipperName, COUNT(Orders.OrderID) AS NumberOfOrders FROM Orders
LEFT JOIN Shippers ON Orders.ShipperID = Shippers.ShipperID
GROUP BY ShipperName
The SQL HAVING Clause
The HAVING clause was added to SQL because the WHERE keyword cannot be used with aggregate functions.
HAVING Syntax
SELECT column_name(s)
FROM table_name
WHERE condition
GROUP BY column_name(s)
HAVING condition
ORDER BY column_name(s); 
The following SQL statement lists the number of customers in each country, sorted high to low (Only include countries with more than 5 customers):
Example
SELECT COUNT(CustomerID), Country
FROM Customers
GROUP BY Country
HAVING COUNT(CustomerID) > 5
ORDER BY COUNT(CustomerID) DESC;

The following SQL statement lists if the employees "Davolio" or "Fuller" have registered more than 25 orders:
Example
SELECT Employees.LastName, COUNT(Orders.OrderID) AS NumberOfOrders
FROM Orders
INNER JOIN Employees ON Orders.EmployeeID = Employees.EmployeeID
WHERE LastName = 'Davolio' OR LastName = 'Fuller'
GROUP BY LastName
HAVING COUNT(Orders.OrderID) > 25;
The SQL EXISTS Operator
The EXISTS operator is used to test for the existence of any record in a subquery.
The EXISTS operator returns TRUE if the subquery returns one or more records.
EXISTS Syntax;
SELECT column_name(s)
FROM table_name
WHERE EXISTS
(SELECT column_name FROM table_name WHERE condition); 

SQL EXISTS Examples
The following SQL statement returns TRUE and lists the suppliers with a product price less than 20:
Example 
SELECT SupplierName
FROM Suppliers
WHERE EXISTS (SELECT ProductName FROM Products WHERE Products.SupplierID = Suppliers.supplierID AND Price < 20); 

The SQL ANY Operator
The ANY operator:
•	returns a boolean value as a result
•	returns TRUE if ANY of the subquery values meet the condition
ANY means that the condition will be true if the operation is true for any of the values in the range. Similar like or operator.
ANY Syntax ;
SELECT column_name(s)
FROM table_name
WHERE column_name operator ANY
  (SELECT column_name
  FROM table_name
  WHERE condition); 
Note: The operator must be a standard comparison operator (=, <>, !=, >, >=, <, or <=).

The SQL ALL Operator
The ALL operator:
•	returns a boolean value as a result
•	returns TRUE if ALL of the subquery values meet the condition
•	is used with SELECT, WHERE and HAVING statements
ALL means that the condition will be true only if the operation is true for all values in the range. Similar like and operator.
Example
SELECT ProductName
FROM Products
WHERE ProductID = ALL
  (SELECT ProductID
  FROM OrderDetails
  WHERE Quantity = 10); 




     






