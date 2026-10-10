DATA DIGGER – SQL Database Management Project
1. Project Overview

Data Digger is a SQL-based database management project developed using MySQL. It is designed to manage customer information, orders, products, and order details. This project demonstrates basic SQL operations such as INSERT, SELECT, UPDATE, DELETE, filtering, sorting, grouping, and aggregate functions.

2. Project Objectives
To create and manage a database using MySQL.
To store customer and product information.
To manage customer orders and order details.
To perform CRUD operations.
To calculate totals, averages, minimum values, and maximum values.
To analyze product sales using SQL queries.
To understand primary keys and foreign keys.
3. Technologies Used
Database: MySQL
Language: SQL
Tools: MySQL Workbench / phpMyAdmin
4. Database Name

Data_Digger

5. Tables Used
Customers

Stores customer details.

CustomerID (Primary Key)
Name
Email (Unique)
Address
Orders

Stores customer order information.

OrderID (Primary Key)
CustomerID (Foreign Key)
OrderDate
TotalAmount
Products

Stores product information.

ProductID (Primary Key)
ProductName
Price
Stock
OrderDetails

Stores product details associated with each order.

OrderDetailID (Primary Key)
OrderID (Foreign Key)
ProductID (Foreign Key)
Quantity
SubTotal
6. SQL Operations Performed
Database Creation
CREATE DATABASE Data_Digger;
USE Data_Digger;

Insert Records

Sample records are inserted into all four tables using the INSERT INTO statement.

Retrieve Records
SELECT * FROM Customers;
SELECT * FROM Orders;
SELECT * FROM Products;
SELECT * FROM OrderDetails;

Update Records

Customer addresses, order amounts, and product prices are updated using UPDATE statements.

Example:

UPDATE Customers
SET Address = 'Vadodara'
WHERE CustomerID = 2;

Delete Records

Customer, order, and product records are deleted using DELETE statements.

Example:

DELETE FROM Products
WHERE ProductID = 203
AND Stock = 0;

Sorting and Filtering

The project uses WHERE, BETWEEN, ORDER BY, and LIMIT clauses to retrieve specific records and sort results.

Example:

SELECT *
FROM Products
ORDER BY Price DESC;

Aggregate Functions

The project uses MAX(), MIN(), AVG(), SUM(), and COUNT() to analyze data.

Example:

SELECT
    MAX(TotalAmount) AS Highest_Order_Amount,
    MIN(TotalAmount) AS Lowest_Order_Amount,
    AVG(TotalAmount) AS Average_Order_Amount
FROM Orders;

Grouping and Sales Analysis
SELECT
    ProductID,
    SUM(Quantity) AS Total_Quantity_Sold
FROM OrderDetails
GROUP BY ProductID
ORDER BY Total_Quantity_Sold DESC
LIMIT 3;


This query displays the top three products based on total quantity sold.

7. Project Analysis and Results
Customers
Five sample customers were inserted.
CustomerID 2's address was updated from Surat to Vadodara.
CustomerID 5 was deleted.
Customer details were retrieved using SELECT queries.
The customer search query searches for the name 'raj'.
Orders
Five sample orders were inserted.
CustomerID 1 has orders 101 and 104.
Order 101's amount was updated from 1500.00 to 1600.00.
Order 105 was deleted.
Recent orders were retrieved using a date condition.
Highest order amount: 2200.00
Lowest order amount: 800.00
Average order amount: 1450.00
Products
Five sample products were inserted.
Products were displayed in descending order of price.
Smartphone price was updated from 25000.00 to 27000.00.
Out-of-stock Headphones were deleted.
Keyboard and Mouse fall within the price range of 500 to 2000.
Highest product price: 55000.00
Lowest product price: 800.00
OrderDetails
Five order-detail records were inserted.
Order 101 has two order-detail records.
Total revenue is calculated using SUM(SubTotal).
Product quantities are grouped and sorted to identify the top three products.
ProductID 204 appears in two order-detail records.
8. How to Run the Project
Install MySQL Server and MySQL Workbench.
Open MySQL Workbench and connect to the server.
Open a new SQL query tab.
Copy and paste the SQL script.
Execute the script.
View the results of the SELECT queries.

Note: The script drops and recreates the database. Existing data in Data_Digger will be deleted when the script is executed.

9. Learning Outcomes
Learned database creation and table management.
Understood CRUD operations in SQL.
Learned primary key and foreign key relationships.
Practiced filtering and sorting records.
Used aggregate functions for data analysis.
Learned GROUP BY and LIMIT for sales analysis.
Understood relational database concepts.
10. Conclusion

The Data Digger project demonstrates the practical use of SQL for database management and data analysis. It covers customer management, order processing, product management, and sales analysis using SQL queries. This project provides a strong foundation in relational database concepts and SQL programming.
