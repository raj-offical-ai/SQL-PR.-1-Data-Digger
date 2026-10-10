**🔎 DATA DIGGER**

**SQL-Powered Database Management & Sales Analysis**
Turning raw data into meaningful insights with MySQL.

**📌 About the Project**

**Data Digger** is a database management project built using MySQL to organize customer information, manage orders, maintain product records, and analyze sales data.

The project demonstrates how SQL can be used to store, update, retrieve, and analyze structured data through practical database operations.

From customer management to product sales analysis, Data Digger brings essential database concepts together in one project.

**🎯 Project Goals**
Build a structured relational database.
Manage customer profiles and addresses.
Track customer orders and order amounts.
Maintain product prices and stock information.
Analyze revenue and product sales.
Apply SQL queries to solve practical data management problems.

**🛠️ Tech Stack**

Component    	:       Technology

Database	    :       MySQL

Query Language	:      SQL

Database Tools  :       MySQL Workbench / phpMyAdmin

Data Analysis	       SQL Aggregate Functions


**🗂️ Database Architecture**

The project consists of four interconnected tables.

**1. Customers 👥**

Stores customer identity and contact information.

CustomerID — Primary Key

Name — Customer name

Email — Unique email address

Address — Customer location


**2. Orders 🧾**

Maintains order information associated with customers.

OrderID — Primary Key

CustomerID — Foreign Key

OrderDate — Order date

TotalAmount — Order amount


**3. Products 📦**

Contains product information and inventory details.

ProductID — Primary Key

ProductName — Product name

Price — Product price

Stock — Available stock


**4. OrderDetails 🛒**

Connects orders with their individual products.

OrderDetailID — Primary Key

OrderID — Foreign Key

ProductID — Foreign Key

Quantity — Units ordered

SubTotal — Line-item subtotal


**🔗 Relationship Design**


The database uses primary keys and foreign keys to maintain relationships between tables.

One customer can place multiple orders.
One order can contain multiple order-detail records.
One product can appear in multiple order details.

This structure helps organize data and maintain referential integrity.

**💻 SQL Highlights**

**Database Initialization**

CREATE DATABASE Data_Digger;
USE Data_Digger;

**Customer Management**

UPDATE Customers
SET Address = 'Vadodara'
WHERE CustomerID = 2;


Updates a customer's address using their unique ID.

**Product Price Analysis**

SELECT
    MAX(Price) AS Highest_Price,
    MIN(Price) AS Lowest_Price
FROM Products;


Finds the highest and lowest product prices.

**Revenue Calculation**

SELECT SUM(SubTotal) AS Total_Revenue
FROM OrderDetails;


Calculates total revenue from the recorded order-detail subtotals.

**Top-Selling Product**s

SELECT
    ProductID,
    SUM(Quantity) AS Total_Quantity_Sold
FROM OrderDetails
GROUP BY ProductID
ORDER BY Total_Quantity_Sold DESC
LIMIT 3;


Ranks products according to their total recorded quantities sold.

**📊 Project Operations**

Data Digger covers the following SQL concepts:

**DDL**: CREATE DATABASE, CREATE TABLE

**DML**: INSERT, UPDATE, DELETE

**DQL**: SELECT

**Filtering**: WHERE, BETWEEN

**Sorting**: ORDER BY

**Aggregation**: SUM(), AVG(), MAX(), MIN(), COUNT()

**Grouping**: GROUP BY

**Constraints**: PRIMARY KEY, FOREIGN KEY, UNIQUE

**Table inspection**: DESC


**📈 Sample Data Insights**

Based on the provided sample data and the executed operations:

Analysis	                                           Result

Initial customers inserted                             	5

Initial orders inserted	                                5

Initial products inserted	                            5

Order-detail records inserted	                        5

Highest remaining order amount                      	2200.00

Lowest remaining order amount                       	800.00

Average remaining order amount                      	1450.00

Highest product price	                                55000.00

Lowest product price	                                800.00


**Note:**

These figures reflect the script's operations and sample data. Revenue calculated from OrderDetails may differ from the sum of Orders.TotalAmount because the supplied sample amounts are not fully consistent.

**🚀 How to Run**

Install MySQL Server and MySQL Workbench, or use phpMyAdmin.
Connect to your MySQL server.
Open a new SQL editor tab.
Paste the Data Digger SQL script.
Execute the script.
Run the SELECT queries to inspect the resulting data.

Important: The script drops and recreates Data_Digger. Existing data in that database will be deleted when you execute it.

**🧠 Key Learning Outcomes**


Through this project, I practiced:

Designing relational database tables.
Implementing CRUD operations.
Establishing table relationships using foreign keys.
Retrieving and filtering records.
Performing calculations using aggregate functions.
Analyzing product quantities and revenue.
Writing structured SQL queries for real-world scenarios.

**🔮 Future Improvements**

Potential enhancements for future versions include:

Automatically calculating order totals from order details.
Adding stock validation before accepting an order.
Creating views for sales reports.
Adding stored procedures and triggers.
Building a dashboard for customer and sales analytics.

**🏁 Conclusion**

Data Digger demonstrates how MySQL can transform organized records into useful information. By combining customer management, order tracking, inventory records, and sales analysis, the project provides practical experience with core SQL and relational database concepts.

This project represents a foundation for building more advanced database applications and data analytics solutions.

**👨‍💻 Project Information**

**Project Name**: Data Digger

**Category:** Database Management & Data Analysis

**Technology**: MySQL and SQL

**Purpose**: Learning and practical implementation of SQL concepts


**Athor :- Raj Dabhade**
