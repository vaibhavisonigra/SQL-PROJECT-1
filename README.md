# 🛒 E-Commerce Database Management System

> **SQL Project --- Data Digger \| MySQL + phpMyAdmin**

![Database](https://img.shields.io/badge/Database-MySQL-blue)
![Tool](https://img.shields.io/badge/Tool-phpMyAdmin-orange)
![Project](https://img.shields.io/badge/Project-E--Commerce-green)
![Status](https://img.shields.io/badge/Status-Completed-success)

------------------------------------------------------------------------

## ✨ Project Overview

This project is a **relational E-Commerce Database** designed to manage
customers, products, orders, and individual order details.

The database demonstrates practical SQL concepts such as:

-   Database and table creation
-   Primary Keys
-   Foreign Keys
-   Relationships between tables
-   `INSERT`, `SELECT`, `UPDATE`, and `DELETE`
-   Filtering with `WHERE` and `BETWEEN`
-   Sorting with `ORDER BY`
-   Aggregate functions such as `SUM()`, `MAX()`, `MIN()`, and `AVG()`
-   `GROUP BY`
-   `COUNT()`
-   `LIMIT`
-   Date-based filtering
-   Referential integrity using foreign keys

------------------------------------------------------------------------

## 🎯 Project Objective

The main objective is to build a small but realistic database for an
online shopping system.

The database answers questions such as:

> Who are our customers?\
> What products are available?\
> Which customer placed an order?\
> What products were ordered?\
> How much revenue was generated?\
> Which products are sold the most?

------------------------------------------------------------------------

## 🗂️ Database Information

**Database Name**

``` text
ecommerce_db
```

**Technology**

``` text
MySQL
```

**Interface**

``` text
phpMyAdmin
```

------------------------------------------------------------------------

## 🧩 Database Structure

``` text
                    ┌──────────────────┐
                    │    CUSTOMERS     │
                    ├──────────────────┤
                    │ PK CustomerID    │
                    │ Name             │
                    │ Email            │
                    │ Address          │
                    └────────┬─────────┘
                             │
                             │ CustomerID
                             ▼
                    ┌──────────────────┐
                    │      ORDERS      │
                    ├──────────────────┤
                    │ PK OrderID       │
                    │ FK CustomerID    │
                    │ OrderDate        │
                    │ TotalAmount      │
                    └────────┬─────────┘
                             │
                             │ OrderID
                             ▼
                 ┌────────────────────────┐
                 │     ORDERDETAILS       │
                 ├────────────────────────┤
                 │ PK OrderDetailID      │
                 │ FK OrderID            │
                 │ FK ProductID          │
                 │ Quantity              │
                 │ SubTotal              │
                 └───────────┬────────────┘
                             │
                             │ ProductID
                             ▼
                    ┌──────────────────┐
                    │     PRODUCTS     │
                    ├──────────────────┤
                    │ PK ProductID     │
                    │ ProductName      │
                    │ Price            │
                    │ Stock            │
                    └──────────────────┘
```

------------------------------------------------------------------------

# 📋 Tables

## 1. 👤 Customers

Stores customer information.

  Field        Type           Key
  ------------ -------------- -------------
  CustomerID   INT            Primary Key
  Name         VARCHAR(100)   ---
  Email        VARCHAR(100)   ---
  Address      VARCHAR(255)   ---

### Tasks Covered

-   Insert at least 5 customers
-   Retrieve all customer details
-   Update a customer's address
-   Delete a customer using `CustomerID`
-   Retrieve customers whose name is `Alice`

------------------------------------------------------------------------

## 2. 🧾 Orders

Stores basic order information.

  Field         Type            Key
  ------------- --------------- -------------
  OrderID       INT             Primary Key
  CustomerID    INT             Foreign Key
  OrderDate     DATE            ---
  TotalAmount   DECIMAL(10,2)   ---

### Tasks Covered

-   Insert at least 5 orders
-   Retrieve all orders
-   Retrieve orders for a specific customer
-   Update an order's total amount
-   Delete an order using `OrderID`
-   Retrieve orders placed in the last 30 days
-   Find highest, lowest, and average order amount

------------------------------------------------------------------------

## 3. 📦 Products

Stores product and inventory information.

  Field         Type            Key
  ------------- --------------- -------------
  ProductID     INT             Primary Key
  ProductName   VARCHAR(100)    ---
  Price         DECIMAL(10,2)   ---
  Stock         INT             ---

### Tasks Covered

-   Insert at least 5 products
-   Retrieve all products sorted by price in descending order
-   Update the price of a specific product
-   Delete a product if it is out of stock
-   Retrieve products priced between ₹500 and ₹2000
-   Find the most expensive and cheapest product using `MAX()` and
    `MIN()`

------------------------------------------------------------------------

## 4. 🧮 OrderDetails

Stores the products included in each order.

  Field           Type            Key
  --------------- --------------- -------------
  OrderDetailID   INT             Primary Key
  OrderID         INT             Foreign Key
  ProductID       INT             Foreign Key
  Quantity        INT             ---
  SubTotal        DECIMAL(10,2)   ---

### Tasks Covered

-   Insert at least 5 order details
-   Retrieve all order details for a specific order
-   Calculate total revenue using `SUM()`
-   Retrieve the top 3 most ordered products
-   Count how many times a specific product has been sold using
    `COUNT()`

------------------------------------------------------------------------

# 🔗 Relationships

The database uses foreign-key relationships to connect the tables.

``` text
Customers.CustomerID
        ↓
Orders.CustomerID

Orders.OrderID
        ↓
OrderDetails.OrderID

Products.ProductID
        ↓
OrderDetails.ProductID
```

This structure avoids unnecessary duplication and keeps related data
connected.

------------------------------------------------------------------------

# 🧠 SQL Concepts Demonstrated

  SQL Concept         Used For
  ------------------- -------------------------------
  `CREATE DATABASE`   Creating the database
  `CREATE TABLE`      Creating tables
  `PRIMARY KEY`       Uniquely identifying records
  `FOREIGN KEY`       Connecting related tables
  `INSERT`            Adding records
  `SELECT`            Reading records
  `UPDATE`            Modifying records
  `DELETE`            Removing records
  `WHERE`             Filtering records
  `BETWEEN`           Filtering a value range
  `ORDER BY`          Sorting results
  `GROUP BY`          Grouping records
  `SUM()`             Calculating total revenue
  `MAX()`             Finding maximum value
  `MIN()`             Finding minimum value
  `AVG()`             Finding average value
  `COUNT()`           Counting records
  `LIMIT`             Restricting result count
  `CURDATE()`         Working with the current date
  `DATE_SUB()`        Date-range filtering

------------------------------------------------------------------------

# 🛡️ Data Integrity

Foreign keys are used to maintain relationships between records.

For example:

``` sql
FOREIGN KEY (CustomerID)
REFERENCES Customers(CustomerID)
```

This means an order is connected to an existing customer.

The project also uses:

``` sql
ON DELETE CASCADE
ON UPDATE CASCADE
```

where appropriate so related records remain consistent when a parent
record changes.

------------------------------------------------------------------------

# 📸 Project Screenshots

Add your screenshots to a `screenshots` folder and keep them organized
like this:

``` text
screenshots/
├── 01_Customers_Data.png
├── 02_Orders_Data.png
├── 03_Products_Data.png
├── 04_OrderDetails_Data.png
├── 05_Customers_Structure.png
├── 06_Orders_Structure.png
├── 07_Products_Structure.png
└── 08_OrderDetails_Structure.png
```

You can add them to this README using:

``` markdown
![Customers Data](screenshots/01_Customers_Data.png)
```

------------------------------------------------------------------------

# 🚀 How to Run the Project

### Step 1 --- Start XAMPP

Start:

``` text
Apache
MySQL
```

### Step 2 --- Open phpMyAdmin

``` text
http://localhost/phpmyadmin
```

### Step 3 --- Create/Import the Database

Import:

``` text
ecommerce_db.sql
```

### Step 4 --- Verify Tables

After importing, confirm that these tables exist:

``` text
customers
orders
products
orderdetails
```

### Step 5 --- Run SQL Queries

Open the **SQL** tab in phpMyAdmin and execute the required queries.

------------------------------------------------------------------------

# 📁 Repository Structure

``` text
ecommerce-database-project/
│
├── ecommerce_db.sql
├── README.md
│
└── screenshots/
    ├── 01_Customers_Data.png
    ├── 02_Orders_Data.png
    ├── 03_Products_Data.png
    ├── 04_OrderDetails_Data.png
    ├── 05_Customers_Structure.png
    ├── 06_Orders_Structure.png
    ├── 07_Products_Structure.png
    └── 08_OrderDetails_Structure.png
```

------------------------------------------------------------------------

# 💡 Key Learning

This project helped demonstrate how a real-world shopping database can
be divided into related tables instead of keeping everything in one
large table.

The design follows a simple flow:

``` text
Customer
   ↓
Order
   ↓
Order Details
   ↓
Product
```

This makes the database easier to manage, search, update, and expand.

------------------------------------------------------------------------

# 👩‍💻 Author

**Student:** *Vaibhavi Sonigra*\
**Project:** E-Commerce Database Management System\
**Technology:** MySQL + phpMyAdmin

------------------------------------------------------------------------

## ⭐ Project Status

**Database:** ✅ Completed\
**Tables:** ✅ Completed\
**Relationships:** ✅ Completed\
**SQL Operations:** ✅ Completed\
**Documentation:** ✅ Completed

> *Built as an academic SQL project to practice relational database
> design and SQL operations.*
