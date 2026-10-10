DATA DIGGER – SQL Database Management Project
1. Project Overview

Data Digger is a SQL-based database management project developed using MySQL. The project demonstrates how to create and manage a database, store customer and product information, maintain order records, and perform various SQL operations.

The project uses four tables: Customers, Orders, Products, and OrderDetails. It covers basic database operations such as INSERT, SELECT, UPDATE, DELETE, aggregate functions, sorting, filtering, grouping, and foreign key relationships.

2. Project Objectives
To create and manage a database using MySQL.
To store customer details, product information, and order records.
To perform CRUD operations (Create, Read, Update, Delete).
To retrieve records using filtering and sorting.
To calculate totals, averages, minimum values, and maximum values.
To analyze product sales and order details using aggregate functions.
To understand primary keys and foreign key relationships.
3. Technologies Used
Database: MySQL
Language: SQL
Tools: MySQL Workbench / phpMyAdmin
4. Database Structure

The project contains four tables.

A. Customers

Stores customer information.

Column	Data Type	Description
CustomerID	INT	Primary key
Name	VARCHAR(100)	Customer name
Email	VARCHAR(100)	Unique email address
Address	VARCHAR(200)	Customer address
B. Orders

Stores customer order information.

Column	Data Type	Description
OrderID	INT	Primary key
CustomerID	INT	Foreign key referencing Customers
OrderDate	DATE	Date of the order
TotalAmount	DECIMAL(10,2)	Total order amount
C. Products

Stores product details.

Column	Data Type	Description
ProductID	INT	Primary key
ProductName	VARCHAR(100)	Product name
Price	DECIMAL(10,2)	Product price
Stock	INT	Available stock
D. OrderDetails

Stores individual product details for each order.

Column	Data Type	Description
OrderDetailID	INT	Primary key
OrderID	INT	Foreign key referencing Orders
ProductID	INT	Foreign key referencing Products
Quantity	INT	Quantity ordered
SubTotal	DECIMAL(10,2)	Subtotal for the order detail
5. Database Relationships
One customer can have multiple orders.
One order can contain multiple order-detail records.
One product can appear in multiple order-detail records.

The Customers, Orders, and Products tables are connected through foreign key relationships with the appropriate tables.

6. SQL Operations Performed
6.1 Database Creation
CREATE DATABASE Data_Digger;
USE Data_Digger;


Creates the database and selects it for use.

6.2 Insert Records

Sample customer, order, product, and order-detail records are inserted using the INSERT INTO statement.

INSERT INTO Customers
(CustomerID, Name, Email, Address)
VALUES
(1, 'raj', 'raj@gmail.com', 'Mumbai');

6.3 Retrieve Records

The SELECT statement retrieves information from database tables.

SELECT * FROM Customers;

6.4 Update Records

The project updates customer addresses, order amounts, and product prices.

UPDATE Customers
SET Address = 'Vadodara'
WHERE CustomerID = 2;

6.5 Delete Records

The project deletes a customer, an order, and an out-of-stock product.

DELETE FROM Products
WHERE ProductID = 203
AND Stock = 0;

6.6 Filter and Sort Records

The project uses WHERE, BETWEEN, ORDER BY, and LIMIT to filter and sort data.

SELECT *
FROM Products
ORDER BY Price DESC;

6.7 Aggregate Functions

Aggregate functions are used to analyze orders and product prices.

SELECT
    MAX(TotalAmount) AS Highest_Order_Amount,
    MIN(TotalAmount) AS Lowest_Order_Amount,
    AVG(TotalAmount) AS Average_Order_Amount
FROM Orders;


Functions used:

MAX() – Finds the highest value.
MIN() – Finds the lowest value.
AVG() – Calculates the average.
SUM() – Calculates the total.
COUNT() – Counts records.
6.8 Grouping and Sales Analysis
SELECT
    ProductID,
    SUM(Quantity) AS Total_Quantity_Sold
FROM OrderDetails
GROUP BY ProductID
ORDER BY Total_Quantity_Sold DESC
LIMIT 3;


This query identifies the top three products by total quantity sold.

7. Project Analysis and Results
Customers
Five sample customers are inserted.
CustomerID 2's address is updated from Surat to Vadodara.
CustomerID 5 is deleted.
Customer information is retrieved using SELECT queries.
The current script searches for the customer named raj.
Orders
Five sample orders are inserted.
CustomerID 1 has orders 101 and 104.
Order 101's amount is updated from 1500.00 to 1600.00.
Order 105 is deleted.
The project retrieves recent orders and calculates the highest, lowest, and average order amounts.
Products
Five sample products are inserted.
Products are displayed in descending order of price.
The Smartphone price is updated from 25000.00 to 27000.00.
The out-of-stock Headphones are deleted.
Products priced between 500 and 2000 are retrieved.
The highest and lowest product prices are calculated.
OrderDetails
Five order-detail records are inserted.
Order 101 contains two order-detail records.
Total revenue is calculated using SUM(SubTotal).
Product quantities are grouped and sorted to identify the top three products.
COUNT(*) is used to count the order-detail records for ProductID 204.
8. How to Run the Project
Install MySQL Server and MySQL Workbench, or use XAMPP with phpMyAdmin.
Open the SQL editor and connect to the MySQL server.
Copy and paste the project SQL script.
Execute the script.
View the output of each SELECT query.
Use DESC Customers;, DESC Orders;, DESC Products;, and DESC OrderDetails; to inspect table structures.

Note: The script starts by dropping and recreating the database. This deletes any existing data in Data_Digger. Use DROP DATABASE IF EXISTS Data_Digger; to avoid an error if the database does not already exist.

9. Learning Outcomes

Through this project, I learned how to:

Create databases and tables in MySQL.
Insert, update, retrieve, and delete records.
Apply primary keys and foreign keys.
Filter records using conditions.
Sort data and retrieve limited results.
Use aggregate functions for data analysis.
Group records to analyze product sales.
Understand relationships between database tables.
10. Conclusion

The Data Digger project demonstrates the practical implementation of SQL for database management and data analysis. It provides experience in handling customer information, managing orders, maintaining product records, and analyzing sales details.

This project builds a foundation for understanding relational databases and writing SQL queries for real-world data management tasks.# SQL-PR.-1-Data-Digger
