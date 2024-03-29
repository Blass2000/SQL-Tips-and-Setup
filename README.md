# SQL-Tips-and-Setup
General overview of getting started with SQL and a few tools to boot. It is always a dream of a project leader to know that they have a team that understands the basics of SQL and data maipulation. I have worked on the leadership and development teams and here are just a few SQL related processes that should be well known 

# SQL 101: Beginner's Guide to SQL Database Programming

Welcome to the SQL 101 repository, your beginner's guide to SQL database programming. Whether you're new to databases or have some programming experience, this repository provides step-by-step guidance, code examples, exercises, and resources to help you master SQL. Lets Gooooo!

## Table of Contents
1. [Installation Guide](#installation-guide)
2. [Introduction to SQL](#introduction-to-sql)
3. [Querying Data](#querying-data)
4. [Modifying Data](#modifying-data)
5. [Data Types and Constraints](#data-types-and-constraints)
6. [Joins and Relationships](#joins-and-relationships)
7. [Aggregation and Grouping](#aggregation-and-grouping)
8. [Subqueries and Views](#subqueries-and-views)
9. [Indexing and Performance Optimization](#indexing-and-performance-optimization)
10. [Transactions and Concurrency Control](#transactions-and-concurrency-control)
11. [Advanced Topics](#advanced-topics)
12. [Best Practices](#best-practices)
13. [Recommended Learning Resources](#recommended-learning-resources)
14. [Exercises and Solutions](#exercises-and-solutions)

## Installation Guide

To get started with SQL, you need to install a relational database management system (RDBMS) on your computer. Here are the installation instructions for the most popular RDBMS:

### MySQL

1. Visit the official MySQL website at [https://dev.mysql.com/downloads/installer/](https://dev.mysql.com/downloads/installer/).
2. Download the MySQL Installer for your operating system.
3. Run the installer and follow the on-screen instructions.
4. During the installation, select the "MySQL Server" component.
5. Choose the appropriate setup type (e.g., Developer Default or Server Only).
6. Set a root password for the MySQL Server.
7. Complete the installation process.
8. Verify the installation by opening a command prompt and running the following command:
   
```
mysql --version
```
   
You should see the installed MySQL version printed on the console.

### PostgreSQL

1. Go to the official PostgreSQL website at [https://www.postgresql.org/download/](https://www.postgresql.org/download/).
2. Choose your operating system and download the PostgreSQL installer.
3. Run the installer and follow the on-screen instructions.
4. During the installation, select the components you want to install, including the PostgreSQL Server and command-line tools.
5. Choose the installation directory and port number (the default values are usually fine).
6. Set a password for the PostgreSQL superuser (postgres).
7. Complete the installation process.
8. Verify the installation by opening a command prompt and running the following command:
   
```
psql --version
```
   
You should see the installed PostgreSQL version printed on the console.

### SQLite

1. Visit the official SQLite website at [https://www.sqlite.org/download.html](https://www.sqlite.org/download.html).
2. Download the precompiled binaries for your operating system.
3. Extract the downloaded file to a directory of your choice.
4. Add the directory containing the SQLite binary to your system's PATH environment variable.
5. Verify the installation by opening a command prompt and running the following command:
   
```
sqlite3 --version
```
   
You should see the installed SQLite version printed on the console.

Choose the RDBMS that best suits your needs and follow the corresponding installation instructions. Once you have successfully installed an RDBMS, you can proceed with the SQL lessons and exercises provided in this repository.

## Introduction to SQL

Structured Query Language (SQL) is a powerful and widely used language for managing and manipulating relational databases. SQL allows you to interact with databases to store, retrieve, update, and delete data. In this section, we will cover the fundamental concepts and syntax of SQL.

### Database Basics

A database is an organized collection of data stored in a structured format. It consists of tables, which hold the data, and relationships between the tables. Each table consists of rows (also known as records) and columns (also known as fields). Columns define the type of data that can be stored, such as text, numbers, or dates.

### SQL Statements

SQL operates through various statements that allow you to perform different actions on the database. The most common SQL statements are:

- **SELECT**: Retrieves data from one or more tables.
- **INSERT**: Adds new data into a table.
- **UPDATE**: Modifies existing data in a table.
- **DELETE**: Removes data from a table.

### Syntax and Structure

SQL statements follow a specific syntax and structure. Here's a basic structure of a SELECT statement:

```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

- `SELECT` specifies the columns you want to retrieve from the table.
- `FROM` specifies the table you want to retrieve data from.
- `WHERE` (optional) specifies the conditions for filtering the data.

### Querying Data

To retrieve data from a database, you use the SELECT statement. You can specify the columns you want to retrieve and apply various conditions to filter the data. Here's an example of a simple SELECT statement:

```sql
SELECT column1, column2
FROM table_name;
```

This statement retrieves the values from `column1` and `column2` in the `table_name` table.

### Filtering Data

You can filter the retrieved data using the WHERE clause. It allows you to specify conditions to match specific records. For example:

```sql
SELECT column1, column2
FROM table_name
WHERE condition;
```

The `condition` can be a comparison between columns or values using operators like `=`, `<>`, `<`, `>`, `<=`, `>=`. You can also use logical operators like `AND`, `OR`, `NOT` to combine multiple conditions.

### Sorting Data

You can sort the retrieved data using the ORDER BY clause. It allows you to specify the columns to sort the data by. For example:

```sql
SELECT column1, column2
FROM table_name
ORDER BY column1 ASC, column2 DESC;
```

This statement sorts the data in ascending order based on `column1` and descending order based on `column2`.

## Modifying Data

In addition to retrieving data, SQL allows you to modify the data stored in a database. This section covers the basic SQL statements for inserting, updating, and deleting data, and explains their impact on the database.

### Inserting Data

To add new data into a table, you use the INSERT statement. Here's an example:

```sql
INSERT INTO table_name (column1, column2, ...)
VALUES (value1, value2, ...);
```

This statement inserts a new row into `table_name` with the specified values for `column1`, `column2`, and so on.

### Updating Data

The UPDATE statement is used to modify existing data in a table. Here's an example:

```sql
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;
```

This statement updates the values of `column1`, `column2`, and so on in `table_name` that match the specified condition.

### Deleting Data

To remove data from a table, you use the DELETE statement. Here's an example:

```sql
DELETE FROM table_name
WHERE condition;
```

This statement deletes the rows from `table_name` that match the specified condition.

**Note:** Modifying data in a database should be done with caution, as it can permanently alter or remove data. Always double-check your statements and ensure they are targeting the correct data before executing them.

## Data Types and Constraints

SQL supports various data types to store different kinds of data in tables. Additionally, you can apply constraints to enforce rules and maintain data integrity. Here are some commonly used data types and constraints:

### Data Types

- **INTEGER**: Represents whole numbers.
- **FLOAT**: Represents floating-point numbers.
- **VARCHAR**: Represents variable-length character strings.
- **DATE**: Represents a date without a time component.
- **BOOLEAN**: Represents true or false values.

These are just a few examples, and different database systems may support additional data types.

### Constraints

- **Primary Key**: Ensures the uniqueness of a column's value in a table, typically used to uniquely identify each row.
- **Foreign Key**: Establishes a relationship between two tables, enforcing referential integrity.
- **Unique Constraint**: Ensures the uniqueness of values in one or more columns.
- **Check Constraint**: Defines a condition that must be true for a row to be valid.

These constraints help maintain data integrity, enforce data relationships, and prevent invalid data from being inserted or modified.

Understanding data types and constraints is crucial for designing and creating well-structured databases that accurately represent the real-world entities and relationships.

*This section has covered the basics of modifying data in a database using SQL statements. It has also introduced data types and constraints that help define the structure and integrity of the data.*

*As you progress, you'll explore more advanced techniques and features of SQL, including working with multiple tables, aggregating data, and optimizing query performance.*

## Joins and Relationships

In a relational database, data is often spread across multiple tables, and relationships are established between them. Understanding relationships and using JOIN statements allows you to retrieve related data from multiple tables efficiently.

### Relationships in Databases

There are three common types of relationships in databases:

- **One-to-One**: A relationship where each record in one table is associated with at most one record in another table.
- **One-to-Many**: A relationship where each record in one table can be associated with multiple records in another table.
- **Many-to-Many**: A relationship where records in both tables can be associated with multiple records in the other table.

Establishing proper relationships between tables helps organize and structure the data effectively.

### JOIN Statements

JOIN statements are used to combine rows from different tables based on related columns. Here are the main types of JOINs:

- **INNER JOIN**: Retrieves rows that have matching values in both tables being joined.
- **LEFT JOIN**: Retrieves all rows from the left table and matching rows from the right table (if any).
- **RIGHT JOIN**: Retrieves all rows from the right table and matching rows from the left table (if any).
- **FULL JOIN**: Retrieves all rows from both tables, including matching and non-matching rows.

JOIN statements allow you to fetch data from multiple tables, leveraging the relationships established between them.

## Aggregation and Grouping

Aggregation functions in SQL, such as SUM, AVG, COUNT, and others, enable you to summarize and calculate values from a set of rows. The GROUP BY clause is used in conjunction with these functions to group rows based on one or more columns.

### Aggregating Data

Aggregate functions perform calculations on a set of rows and return a single result. For example:

- **SUM**: Calculates the sum of a column's values.
- **AVG**: Calculates the average of a column's values.
- **COUNT**: Returns the number of rows in a group.
- **MIN**: Retrieves the minimum value from a column.
- **MAX**: Retrieves the maximum value from a column.

These functions allow you to derive meaningful insights and statistical calculations from your data.

### Grouping Data

The GROUP BY clause is used to group rows based on one or more columns. It allows you to divide the data into logical subsets and apply aggregate functions to each group individually. For example:

```sql
SELECT column1, aggregate_function(column2)
FROM table_name
GROUP BY column1;
```

This statement groups the rows based on `column1` and applies the aggregate function to each group.

## Subqueries and Views

SQL subqueries provide a way to nest one query inside another. They can be used to create more complex queries and retrieve data from multiple tables simultaneously.

Views, on the other hand, are virtual tables based on the result of a query. They simplify data retrieval by providing a predefined query that can be treated as a table.

### Subqueries

A subquery is a query embedded within another query. It can be used in the WHERE or FROM clause of the outer query to retrieve data based on intermediate results. Subqueries allow you to break down complex problems into smaller, more manageable parts.

### Views

Views are saved queries that act as virtual tables. They can be created using a SELECT statement and provide an abstraction layer over the underlying tables. Views simplify data retrieval by encapsulating complex queries into a single, reusable entity.

*This section has covered the concept of relationships in databases, JOIN statements to retrieve related data, aggregation functions and the GROUP BY clause for summarizing data, and the usage of subqueries and views to handle complex queries.*

*By understanding these concepts, you'll be able to work with more advanced SQL queries, manipulate data effectively, and gain valuable insights from your databases.*

## Indexing and Performance Optimization

Indexes play a crucial role in enhancing the performance of SQL queries by improving data retrieval speed. Understanding how to create and use indexes effectively is essential for optimizing database performance.

### Importance of Indexes

Indexes are data structures that provide quick access to specific data within a table. They enable the database engine to locate data faster by reducing the number of rows that need to be scanned. Indexes are created on one or more columns and significantly enhance query performance, especially for large tables.

### Creating Indexes

To create an index, you need to identify the columns that are frequently used in search conditions or join operations. Using the `CREATE INDEX` statement, you can specify the index name, the table on which the index will be created, and the column(s) to be indexed. For example:

```sql
CREATE INDEX idx_name ON table_name (column1, column2);
```

Creating indexes on appropriate columns can significantly speed up query execution.

### Using Indexes Effectively

While indexes boost performance, they also come with some overhead. It's essential to strike a balance between the number of indexes and their impact on data modification operations (inserts, updates, and deletes). Remember to update indexes when modifying data to ensure their accuracy.

Regularly analyze query performance, monitor index usage, and consider adding or removing indexes based on actual usage patterns. Proper indexing strategy is crucial for optimizing database performance.

## Transactions and Concurrency Control

In a multi-user database environment, transactions ensure data integrity and maintain consistency. Understanding transactions and concurrency control is vital when dealing with concurrent database operations.

### Transactions and ACID Properties

A transaction is a logical unit of work that consists of one or more database operations. Transactions adhere to the ACID properties:

- **Atomicity**: A transaction is treated as a single, indivisible unit of work. Either all operations within a transaction are committed, or none of them are.
- **Consistency**: Transactions bring the database from one consistent state to another consistent state. The integrity of the data is maintained.
- **Isolation**: Concurrently executing transactions are isolated from each other, ensuring that the intermediate states of transactions are not visible to other transactions.
- **Durability**: Once a transaction is committed, its changes are permanently saved and can survive system failures.

Understanding the ACID properties helps ensure data integrity and reliability in database operations.

### Isolation Levels

Isolation levels define the degree of isolation and concurrency control in database transactions. They determine how transactions interact with each other and impact data consistency.

Common isolation levels include:

- **Read Uncommitted**: Allows dirty reads and has the lowest level of isolation.
- **Read Committed**: Prevents dirty reads, but non-repeatable reads and phantom reads are possible.
- **Repeatable Read**: Guarantees consistent reads within a transaction, but phantom reads may occur.
- **Serializable**: Provides the highest level of isolation, ensuring that transactions are executed as if they were processed sequentially.

Understanding isolation levels helps manage concurrent transactions and maintain data consistency.

## Advanced Topics

SQL offers advanced features that extend its capabilities beyond simple queries. Exploring these advanced topics opens up new possibilities for efficient data management and automation.

### Stored Procedures

Stored procedures are precompiled SQL code that can be stored and executed on the database server. They encapsulate a set of SQL statements as a single unit, enabling code reuse, improved performance, and enhanced security. Stored procedures can accept input parameters and return output values.

### Triggers

Triggers are special SQL constructs that automatically execute in response to specific database events, such as INSERT, UPDATE,

 or DELETE operations on tables. Triggers enable you to enforce business rules, maintain data integrity, and automate complex database actions.

### User-Defined Functions

User-defined functions (UDFs) allow you to extend SQL by creating custom functions. UDFs encapsulate specific logic and can be used within SQL statements just like built-in functions. They provide a way to modularize complex calculations or data transformations, improving code readability and reusability.

Exploring these advanced topics will expand your SQL skills and empower you to build more sophisticated database solutions.

*Keep learning, practicing, and experimenting with SQL to become proficient in handling diverse data scenarios.*

## Best Practices

Writing efficient and maintainable SQL code is essential for building robust and scalable database applications. Here are some best practices to follow:

### Naming Conventions

Use descriptive names for tables, columns, and other database objects. Choose names that accurately represent the data they store or the purpose they serve. Consistent and meaningful naming conventions improve code readability and maintainability.

### Code Formatting

Consistent code formatting enhances readability and makes it easier to understand SQL statements. Indentation, proper spacing, and line breaks improve code structure and organization. Consider using a code formatter or adhering to a style guide for consistent formatting.

### Error Handling

Implement error handling mechanisms in your SQL code to gracefully handle unexpected scenarios. Use structured error handling constructs provided by your database system, such as TRY-CATCH blocks, to catch and handle errors effectively. Proper error handling improves code reliability and maintainability.

## Recommended Learning Resources

To further enhance your SQL skills, explore these recommended learning resources:

- **Books**: "SQL Cookbook" by Anthony Molinaro, "SQL Queries for Mere Mortals" by John Viescas and Michael J. Hernandez.
- **Online Tutorials**: SQL tutorials on websites like W3Schools, SQLZoo, and Mode Analytics.
- **Video Courses**: Online platforms like Udemy, Coursera, and Pluralsight offer SQL courses for beginners.
- **Interactive Websites**: SQLFiddle, HackerRank, and LeetCode provide interactive SQL challenges and exercises.

These resources provide comprehensive explanations, hands-on practice, and real-world examples to deepen your SQL knowledge.

Great! Here's an updated version of the "Exercises and Solutions" section that includes the mentioned websites:

## Exercises and Solutions

Practice is key to mastering SQL. This repository includes a set of SQL exercises designed specifically for beginners. Each exercise is accompanied by a solution to help you validate your approach and learn from different perspectives.

These exercises cover a range of SQL topics, including querying, data manipulation, joins, and more. Solve the exercises independently, compare your solutions with the provided ones, and explore alternative approaches to strengthen your SQL skills.

Additionally, you can further enhance your SQL proficiency by practicing on dedicated websites that offer SQL exercises and challenges. Check out the following platforms:

- [SQLZoo](https://sqlzoo.net/): SQLZoo provides interactive SQL exercises and tutorials for beginners. It covers various SQL topics and offers a hands-on learning experience.

- [HackerRank](https://www.hackerrank.com/domains/tutorials/10-days-of-statistics): HackerRank offers a section dedicated to SQL exercises. Solve SQL problems and test your skills on their platform.

- [LeetCode](https://leetcode.com/problemset/database/): LeetCode, known for coding challenges, also offers a database section with SQL exercises. Practice SQL problems and improve your problem-solving abilities.

*Challenge yourself with these exercises and watch your SQL proficiency grow!*

## Conclusion

Congratulations on completing SQL 101: Beginner's Guide to SQL Programming! You've learned essential SQL concepts, from querying data to optimizing performance. Remember best practices, practice with exercises, and explore recommended resources.

**Good luck and Happy coding with SQL!**




# SQL Sales Analysis

For many of us in the tech world, SQL (Structured Query Language) is the backbone of data management and analysis. It's a critical skill, whether you're a data analyst, software developer, business analyst, or a professional in virtually any field that relies on data.

Now, let's understand AtliQ's business model. In the industry, domain understanding is actually more important than technical skills.

---

**1. Gross monthly total sales report for Croma**

**Discription:-**

As a product owner, I need an aggregate monthly gross sales report for Croma India customers so that I can track how much sales this particular customer is generating for AtliQ and manage our relationships accordingly.

The report should have the following fields,

- Month
- Total gross sales amount to Croma India in this month

**SQL Query :-**

```sql
SELECT
    S.date,
    ROUND (SUM(g.gross_price * s.sold_quantity),2) AS gross_total_price
FROM fact_sales_monthly s
JOIN fact_gross_price g
    ON g.product_code = s.product_code
    AND g.fiscal_year = get_fiscal_year(s.date)
WHERE customer_code = 90002002
GROUP BY s.date
ORDER BY s.date DESC

```

**Result :-**

<div align="center">

| date       | gross_total_price |
| :--------- | ----------------: |
| 2021-12-01 |     $ 19537146.56 |
| 2021-10-01 |     $ 13908229.29 |
| 2021-09-01 |     $ 11192823.08 |
| 2021-08-01 |      $ 2349478.82 |
| 2021-06-01 |      $ 2288587.45 |
| 2021-05-01 |      $ 2181587.78 |
| 2021-04-01 |      $ 2253574.91 |
| 2021-02-01 |      $ 2355170.45 |
| 2021-01-01 |      $ 2303086.37 |
| 2020-12-01 |      $ 4078789.92 |

</div>

---

**2. Generate a yearly report for Croma India where there are two columns.**

**Discription:-**

- Fiscal Year

- Total Gross Sales amount in that Year from Croma

**SQL Query :-**

```sql
SELECT
    get_fiscal_year(s.date) AS Fiscal_Year,
    ROUND (SUM(g.gross_price * s.sold_quantity),2) AS gross_total_price
FROM
	fact_sales_monthly s
JOIN
	fact_gross_price g
ON
	g.product_code = s.product_code
AND
	g.fiscal_year = get_fiscal_year(s.date)
WHERE customer_code = 90002002
GROUP BY get_fiscal_year(date)
ORDER BY fiscal_year DESC
```

**Result :-**

<div align="center">

| Fiscal Year | gross_total_price |
| ----------- | ----------------: |
| 2022        |     $ 44638198.92 |
| 2021        |     $ 23216512.22 |
| 2020        |      $ 6502181.91 |
| 2019        |      $ 3555079.02 |
| 2018        |      $ 1324097.44 |

</div>

---

**3. Created stored proc for monthly gross sales report.**

**Discription:-**

<p>

As a data analyst, I want to create a stored proc for monthly gross sales reports so that I don't have to modify the query every time manually. Stored proc can be run by other users (who have limited access to the database) and they can generate this report without having to involve the data analytics team.

</p>

The report should have the following columns,

- Month

- Total gross sales in that month from a given customer

**SQL Query :-**

```sql
CREATE DEFINER=`root`@`localhost` PROCEDURE `get_monthly_gross_sales_for_customer`(
	in_customer_code TEXT
)
BEGIN
	SELECT
		s.date,
		ROUND(SUM(g.gross_price * s.sold_quantity),2) AS gross_monthly_sales
	FROM
		fact_sales_monthly s
	JOIN
		fact_gross_price g
	ON
		g.product_code = s.product_code
	AND
		g.fiscal_year = get_fiscal_year(s.date)
	WHERE
		FIND_IN_SET(s.customer_code, in_costomer_code)>0
	GROUP BY s.date
	ORDER BY s.date DESC;
END

```

**Result :-**

<div align="center">

| date       | gross_monthly_sales |
| ---------- | ------------------: |
| 2021-12-01 |       $ 19537146.56 |
| 2021-10-01 |       $ 13908229.29 |
| 2021-09-01 |       $ 11192823.08 |
| 2021-08-01 |        $ 2349478.82 |
| 2021-06-01 |        $ 2288587.45 |
| 2021-05-01 |        $ 2181587.78 |
| 2021-04-01 |        $ 2253574.91 |
| 2021-02-01 |        $ 2355170.45 |
| 2021-01-01 |        $ 2303086.37 |
| 2020-12-01 |        $ 4078789.92 |
| 2020-10-01 |        $ 3109316.88 |
| 2020-09-01 |        $ 2296919.63 |
| 2020-08-01 |         $ 799327.63 |
| 2020-06-01 |         $ 362545.14 |
| 2020-05-01 |         $ 145049.05 |
| 2020-04-01 |         $ 130520.92 |

</div>

---

**4. Stored proc for the market badge.**

**Discription:-**

Create a stored proc that can determine the market badge based on the following logic, If the total sold quantity > 5 million that market is considered Gold else it is Silver.

My input will be,

- Market
- Fiscal Year

Output

- Market badge

**SQL Query :-**

```sql
CREATE DEFINER=`root`@`localhost` PROCEDURE `get_market_badge`(
	IN in_market VARCHAR(45),
    IN in_fiscal_year YEAR,
    OUT out_badge VARCHAR(45)
)
BEGIN
	DECLARE qty INT DEFAULT 0;
    #If value not given for market assume like default market is India
    IF in_market = "" THEN
		SET in_market = "India";
	END IF;
    #Retrive total qty for given market and fiscal year
	SELECT
		SUM(s.sold_quantity) AS total_qty
	FROM fact_sales_monthly s
	JOIN dim_customer c
	ON s.customer_code = c.customer_code
	WHERE
		get_fiscal_year(s.date) = in_fiscal_year AND
        c.market = in_market
	GROUP BY c.market;

    #Determine market badge
    IF qty > 5000000 THEN
		SET out_badge = "Gold";
	ELSE
		SET out_badge = "Silver";
	END IF;
END
```

```sql
set @out_badge = '0';
call gdb0041.get_market_badge('india', 2021, @out_badge);
select @out_badge;
```

**Result :-**

| @out_badge |
| ---------- |
| Silver     |

---

**5. Create a view for gross sales. It should have the following columns.**

**Discription:-**

date, fiscal_year, customer_code, customer, market, product_code, product, variant, sold_quanity, gross_price_per_item, gross_price_total

**SQL Query :-**

```sql
CREATE
    ALGORITHM = UNDEFINED
    DEFINER = `root`@`localhost`
    SQL SECURITY DEFINER
VIEW `gross_sales` AS
    SELECT
		S.date,
		S.fiscal_year,
		S.customer_code,
		C.customer,
		C.market,
		S.product_code,
		P.product,
		P.variant,
		S.sold_quantity,
		g.gross_price AS gross_price_per_item,
		ROUND((s.sold_quantity * g.gross_price),2) AS gross_price_total
	FROM fact_sales_monthly s
	JOIN dim_customer c
		ON s.customer_code = c.customer_code
	JOIN dim_product p
		ON s.product_code = p.product_code
	JOIN fact_gross_price g
		ON s.fiscal_year = g.fiscal_year
		AND s.product_code = g.product_code

```

```sql
SELECT * FROM gdb0041.gross_sales;
```

**Result :-**

<div align="center">

![gross-sales](/images/gross-sales.png)

</div>

---

**6. Top markets, products, and customers for a given financial year.**

**Discription:-**

As a product owner, I want a report for top markets, products, and customers by net sales for a given financial year so that I can have a holistic view of our financial performance and can take appropriate actions to address any potential issues.

We will probably write stored proc for this as we will also need this report going forward.

- **Report for top markets**

**SQL Query :-**

```sql
CREATE DEFINER=`root`@`localhost` PROCEDURE `get_top_n_market_by_net_sales`(
	in_fiscal_year INT,
    in_top_n INT
)
BEGIN
	SELECT
		market,
		ROUND(SUM(net_sales)/1000000,2) AS net_sales_mln
	FROM net_sales
	WHERE fiscal_year = in_fiscal_year
	GROUP BY market
	ORDER BY net_sales_mln DESC
	LIMIT in_top_n;
END
```

```sql
call gdb0041.get_top_n_market_by_net_sales(2021, 5);
```

**Result :-**

<div align="center">

| market         | net sales mln |
| -------------- | ------------: |
| India          |      $ 210.67 |
| USA            |      $ 132.05 |
| South Korea    |       $ 64.01 |
| Canada         |       $ 45.89 |
| United Kingdom |       $ 44.73 |

</div>

---

- **Report for top products**

**SQL Query :-**

```sql
CREATE DEFINER=`root`@`localhost` PROCEDURE `get_top_n_product_by_net_sales`(
	in_market VARCHAR(45),
    in_fiscal_year INT,
    in_top_n INT
)
BEGIN
	SELECT
		product,
		ROUND(SUM(net_sales)/1000000,2) AS net_sales_mln
	FROM net_sales
	WHERE fiscal_year = in_fiscal_year
		AND market = in_market
	GROUP BY product
	ORDER BY net_sales_mln DESC
	LIMIT in_top_n;
END
```

```sql
call gdb0041.get_top_n_product_by_net_sales('India', 2021, 5);
```

**Result :-**

<div align="center">

| product       | net sales mln |
| ------------- | ------------: |
| AQ BZ Allinl  |        $ 8.54 |
| AQ Qwerty     |        $ 7.22 |
| AQ Trigger    |        $ 6.78 |
| AQ Gen Y      |        $ 6.02 |
| AQ Trigger Ms |        $ 5.74 |

</div>

---

- **Report for top customers**

**SQL Query :-**

```sql
CREATE DEFINER=`root`@`localhost` PROCEDURE `get_top_n_customer_by_net_sales`(
	in_market VARCHAR(45),
    in_fiscal_year INT,
    in_top_n INT
)
BEGIN
	SELECT
		c.customer,
		ROUND(SUM(net_sales)/1000000,2) AS net_sales_mln
	FROM net_sales n
	JOIN dim_customer c
		ON n.customer_code = c.customer_code
	WHERE fiscal_year = in_fiscal_year
		AND n.market = in_market
	GROUP BY c.customer
	ORDER BY net_sales_mln DESC
	LIMIT in_top_n;
END
```

```sql
call gdb0041.get_top_n_customer_by_net_sales('India', 2021, 5);
```

**Result :-**

<div align="center">

| customer         | net sales mln |
| ---------------- | ------------: |
| Amazon           |        $30.00 |
| Atliq Exclusive  |        $23.98 |
| Flipkart         |        $12.96 |
| Electricalsocity |        $12.31 |
| Propel           |        $11.86 |

</div>

---

**7. Net sales % share Global.**

**Discription:-**

AS product owner, I want to see a bar Chart report for FY—2021 for top IO markets by % net sales.

**SQL Query :-**

```sql
WITH cte AS (
	SELECT
		C.customer,
		ROUND(SUM(net_sales)/1000000,2) AS net_sales_mln
	FROM net_sales n
	JOIN dim_customer c
		ON n.customer_code = c.customer_code
	WHERE fiscal_year = 2021
	GROUP BY c.customer
)
SELECT
	*,
	net_sales_mln*100/SUM(net_sales_mln) over() AS pct
FROM cte
ORDER BY net_sales_mln DESC
```

**Result :-**

<div align="center">

| customer         | net sales mln |    pct |
| ---------------- | ------------: | -----: |
| Amazon           |       $109.03 | 13.23% |
| Atliq Exclusive  |        $79.92 |   9.7% |
| Atliq e Store    |        $70.31 |  8.53% |
| Sage             |        $27.07 |  3.29% |
| Flipkart         |        $25.25 |  3.06% |
| Leader           |        $24.52 |  2.98% |
| Neptune          |        $21.01 |  2.55% |
| Ebay             |        $19.88 |  2.41% |
| Electricalsocity |        $16.25 |  1.97% |
| Synthetic        |        $16.10 |  1.95% |

</div>

**Bar Chart :-**

<div align="center">

![net-sales-bar-chart](/images/net-sales-bar-chart.png)

</div>

---

**8. Net sales % share by region**

**Discription:-**

As a product owner, I want to see region-wise (APAC, EU, L TAM, etc) % net sales breakdown by customers in a respective region so that I can perform my regional analysis on the financial performance of the company.

The end result should be bar charts in the following format for FY = 2021. Build a reusable asset that we can use to conduct this analysis for any financial year.

**SQL Query :-**

```sql
WITH cte AS (
	SELECT
		c.customer,
		c.region,
		ROUND(SUM(net_sales)/1000000,2) AS net_sales_mln
	FROM net_sales n
	JOIN dim_customer c
		ON n.customer_code = c.customer_code
	WHERE fiscal_year = 2021
	GROUP BY c.customer, c.region
)
SELECT
	*,
	net_sales_mln*100/SUM(net_sales_mln) over(partition by region) AS pct
FROM cte
ORDER BY region, net_sales_mln DESC
```

**Result :-**

- **APAC Region**

<div align="center">

| customer         | region | net_sales_mln |    pct |
| ---------------- | ------ | ------------: | -----: |
| Amazon           | APAC   |        $57.41 | 12.99% |
| Atliq Exclusive  | APAC   |        $51.58 | 11.67% |
| Atliq e Store    | APAC   |        $36.97 |  8.36% |
| Leader           | APAC   |        $24.52 |  5.55% |
| Sage             | APAC   |        $22.85 |  5.17% |
| Neptune          | APAC   |        $21.01 |  4.75% |
| Electricalsocity | APAC   |        $16.25 |  3.68% |
| Propel           | APAC   |        $14.14 |   3.2% |
| Synthetic        | APAC   |        $14.14 |   3.2% |
| Flipkart         | APAC   |        $12.96 |  2.93% |

</div>

**Pie Chart :-**

<div align="center">

![net-sales-pie-chart-apac](/images/net-sales-apac.png)

</div>

---

- **EU Region**

<div align="center">

| customer        | region | net_sales_mln |   pct |
| --------------- | ------ | ------------: | ----: |
| Atliq e Store   | EU     |        $19.83 | 9.87% |
| Amazon          | EU     |        $19.77 | 9.84% |
| Atliq Exclusive | EU     |        $13.39 | 6.67% |
| UniEuro         | EU     |         $9.63 |  4.8% |
| Expert          | EU     |         $8.38 | 4.17% |
| Chip 7          | EU     |         $7.23 |  3.6% |
| Radio Popular   | EU     |         $6.95 | 3.46% |
| Media Markt     | EU     |         $6.88 | 3.43% |
| ElkjÃ¸p         | EU     |         $6.76 | 3.37% |
| Sorefoz         | EU     |         $6.13 | 3.05% |

</div>

**Pie Chart :-**

<div align="center">

![net-sales-pie-chart-eu](/images/net-sales-eu.png)

</div>

---

- **NA Region**

<div align="center">

| customer         | region | net_sales_mln |    pct |
| ---------------- | ------ | ------------: | -----: |
| Amazon           | NA     |        $30.31 | 17.03% |
| Atliq Exclusive  | NA     |        $14.95 |   8.4% |
| walmart          | NA     |        $12.63 |   7.1% |
| Atliq e Store    | NA     |        $12.42 |  6.98% |
| Costco           | NA     |        $12.19 |  6.85% |
| Staples          | NA     |        $11.49 |  6.46% |
| Flipkart         | NA     |        $10.35 |  5.82% |
| Path             | NA     |         $9.10 |  5.11% |
| Ebay             | NA     |         $8.74 |  4.91% |
| Acclaimed Stores | NA     |         $8.53 |  4.79% |

</div>

**Pie Chart :-**

<div align="center">

![net-sales-pie-chart-na](/images/net-sales-na.png)

</div>

---

**9. Get top n products in each division by their quantity sold.**

**Discription:-**

Write a stored proc for getting TOP n products in each division by their quantity sold in a given financial year. For example below would be the result for FY=2021.

**SQL Query :-**

```sql
CREATE DEFINER=`root`@`localhost` PROCEDURE `get_top_n_product_by_net_sales`(
	in_market VARCHAR(45),
	in_fiscal_year INT,
	in_top_n INT
)
BEGIN
	SELECT
		product,
		ROUND(SUM(net_sales)/1000000,2) AS net_sales_mln
	FROM net_sales
	WHERE fiscal_year = in_fiscal_year
		AND market = in_market
	GROUP BY product
	ORDER BY net_sales_mln DESC
	LIMIT in_top_n;
END
```

```sql
call gdb0041.get_top_n_product_by_net_sales('india', 2021, 5);
```

**Result :-**

<div align="center">

| product       | net_sales_mln |
| ------------- | ------------: |
| AQ BZ Allinl  |         $8.54 |
| AQ Qwerty     |         $7.22 |
| AQ Trigger    |         $6.78 |
| AQ Gen Y      |         $6.02 |
| AQ Trigger Ms |         $5.74 |

</div>

---

**10. Creating a fact_act_est.**

**Discription:-**

using the fact_sales_mothly and fact_forecast_monthly create a fact_act_est.

**SQL Query :-**

```sql
create table fact_act_est(
	select
		s.date as date,
		s.fiscal_year as fiscal_year,
		s.product_code as product_code,
		s.customer_code as customer_code,
		s.sold_quantity as sold_quantity,
		f.forecast_quantity as forecast_quantity
	from fact_sales_monthly s
	left join fact_forecast_monthly f
	using (date, customer_code, product_code)
)
union
(
	select
		f.date as date,
		f.fiscal_year as fiscal_year,
		f.product_code as product_code,
		f.customer_code as customer_code,
		s.sold_quantity as sold_quantity,
		f.forecast_quantity as forecast_quantity
	from fact_forecast_monthly  f
	left join fact_sales_monthly s
	using (date, customer_code, product_code)
);

update fact_act_est
set sold_quantity = 0
where sold_quantity is null;

update fact_act_est
set forecast_quantity = 0
where forecast_quantity is null;

```

```sql
SELECT * FROM gdb0041.fact_act_est;
```

**Result :-**

<div align="center">

| date     | fiscal_year | product_code | customer_code | sold_quantity | forecast_quantity |
| -------- | ----------- | ------------ | ------------- | ------------: | ----------------: |
| 9/1/2017 | 2018        | A0118150101  | 70002017      |            51 |                18 |
| 9/1/2017 | 2018        | A0118150101  | 70002018      |            77 |                11 |
| 9/1/2017 | 2018        | A0118150101  | 70003181      |            17 |                 9 |
| 9/1/2017 | 2018        | A0118150101  | 70003182      |             6 |                 6 |
| 9/1/2017 | 2018        | A0118150101  | 70006157      |             5 |                 5 |
| 9/1/2017 | 2018        | A0118150101  | 70006158      |             7 |                 6 |
| 9/1/2017 | 2018        | A0118150101  | 70007198      |            29 |                 4 |
| 9/1/2017 | 2018        | A0118150101  | 70007199      |            34 |                 7 |
| 9/1/2017 | 2018        | A0118150101  | 70008169      |            22 |                 7 |
| 9/1/2017 | 2018        | A0118150101  | 70008170      |             5 |                 8 |

</div>

---

**11. Write a query for the below scenario.**

**Discription:-**

The supply chain business manager wants to see which customers’ forecast accuracy has dropped from 2020 to 2021. Provide a complete report with these columns: customer_code, customer_name, market, forecast_accuracy_2020, forecast_accuracy_2021

**SQL Query :-**

- forecast_accuracy_2021

```sql
create temporary table forecast_accuracy_2021
with forecast_err_table as (
	select
		s.customer_code as customer_code,
		c.customer as customer_name,
		c.market as market,
		sum(s.sold_quantity) as total_sold_qty,
		sum(s.forecast_quantity) as total_forecast_qty,
		sum(s.forecast_quantity-s.sold_quantity) as net_error,
		round( sum( s.forecast_quantity - s.sold_quantity ) * 100 / sum( s.forecast_quantity ) , 1 ) as net_error_pct,
		sum(abs(s.forecast_quantity-s.sold_quantity)) as abs_error,
		round ( sum( abs( s.forecast_quantity - sold_quantity ) ) * 100 / sum( s.forecast_quantity ) , 2 ) as abs_error_pct
	from fact_act_est s
	join dim_customer c
	on s.customer_code = c.customer_code
	where s.fiscal_year=2021
	group by customer_code
)
Select
	*,
	if (abs_error_pct > 100, 0, 100.0 - abs_error_pct) as forecast_accuracy
from forecast_err_table
order by forecast_accuracy desc;
```

- forecast_accuracy_2020

```sql
create temporary table forecast_accuracy_2020
with forecast_err_table as (
	select
		s.customer_code as customer_code,
		c.customer as customer_name,
		c.market as market,
		sum(s.sold_quantity) as total_sold_qty,
		sum(s.forecast_quantity) as total_forecast_qty,
		sum(s.forecast_quantity-s.sold_quantity) as net_error,
		round( sum( s.forecast_quantity - s.sold_quantity ) * 100 / sum( s.forecast_quantity ) , 1 ) as net_error_pct,
		sum(abs(s.forecast_quantity-s.sold_quantity)) as abs_error,
		round ( sum( abs( s.forecast_quantity - sold_quantity ) ) * 100 / sum( s.forecast_quantity ) , 2 ) as abs_error_pct
	from fact_act_est s
	join dim_customer c
	on s.customer_code = c.customer_code
	where s.fiscal_year=2020
	group by customer_code
)
Select
	*,
	if (abs_error_pct > 100, 0, 100.0 - abs_error_pct) as forecast_accuracy
from forecast_err_table
order by forecast_accuracy desc;
```

```sql
select
	f_2020.customer_code,
	f_2020.customer_name,
	f_2020.market,
	f_2020.forecast_accuracy as forecast_acc_2020,
	f_2021.forecast_accuracy as forecast_acc_2021
from forecast_accuracy_2020 f_2020
join forecast_accuracy_2021 f_2021
on f_2020.customer_code = f_2021.customer_code
where f_2021.forecast_accuracy < f_2020.forecast_accuracy
order by forecast_acc_2020 desc;
```

**Result :-**

<div align="center">

| customer_code | customer_name   | market      | forecast_acc_2020 | forecast_acc_2021 |
| ------------- | --------------- | ----------- | ----------------: | ----------------: |
| 70006158      | Atliq e Store   | Philiphines |             42.65 |             24.49 |
| 70008170      | Atliq e Store   | Australia   |             40.96 |             38.74 |
| 90005161      | Zone            | Pakistan    |             40.08 |              37.1 |
| 90014140      | Radio Popular   | Netherlands |             38.53 |                 0 |
| 90008166      | Sound           | Australia   |             38.51 |             36.79 |
| 70014143      | Atliq e Store   | Netherlands |             38.32 |                 0 |
| 90004062      | Flawless Stores | Japan       |             38.22 |             32.56 |
| 90014137      | Media Markt     | Netherlands |             37.85 |                 0 |
| 90014138      | Mbit            | Netherlands |             37.83 |                 0 |
| 70004069      | Atliq Exclusive | Japan       |             37.62 |             32.09 |

</div>

---

