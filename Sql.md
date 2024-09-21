<mark style="background: #FFB8EBA6;"># what is pros of views?</mark>
1. **Simplifies Complex Queries**:
    - Views can encapsulate complex queries, making it easier to query data. Instead of writing long, complex SQL each time, you can query the view directly.
    **Example**: Instead of writing a query with multiple joins every time, you can create a view that handles it for you.
    
2. **Security**:
    - Views allow you to control which columns and rows are visible to certain users. You can grant access to a view without giving direct access to the underlying tables.
    **Example**: You can create a view that shows only non-sensitive data from a table, allowing restricted access for certain users.   
4. **Reuse of Queries**:
    
    - Once you define a view, you can reuse it in multiple queries. This helps avoid redundancy and reduces errors by centralizing complex SQL logic in one place.
5. **Improved Readability**:
    
    - Views make it easier to understand and manage complex relationships between tables by creating a simple interface for users.

# what is the cons of view?
1. **Dependency Issues**:
    
    - Views create dependencies on the underlying tables. If those tables are modified (schema changes), it could break the view and potentially cause errors in applications relying on it.
2. **Limited Functionality**:
- Some views are **not updatable**, meaning you can’t perform `INSERT`, `UPDATE`, or `DELETE` operations on them. This happens especially when the view involves complex joins, aggregations, or distinct clauses.
<mark style="background: #FFB8EBA6;">## What is a Stored Procedure?</mark>

A stored procedure is a prepared SQL code that you can save, so the code can be reused over and over again.

So if you have an SQL query that you write over and over again, save it as a stored procedure, and then just call it to execute it.

****PL/SQL (Procedural Language for SQL)***
* is one of the most widely used database programming languages in the world, known for its robust performance, flexibility, and tight integration with Oracle databases. It is a preferred choice for many top companies such as Oracle, IBM, Accenture, Infosys, TCS, Cognizant, and many more due to its powerful features and efficiency in managing database operations.

# SQL Trigger
A trigger is a stored procedure in a database that automatically invokes whenever a special event in the database occurs. For example, a trigger can be invoked when a row is inserted into a specified table or when specific table columns are updated. In simple words, a trigger is a collection of [SQL](https://www.geeksforgeeks.org/sql-tutorial) statements with particular names that are stored in system memory. It belongs to a specific class of stored procedures that are automatically invoked in response to database server events. Every trigger has a table attached to it.

### **Difference Between Entity and View in SQL**:
- **Entity (Table)**: Stores actual data and supports full CRUD operations. It is a core database object representing a real-world entity.
- **View**: A virtual table that doesn’t store data itself but shows data from one or more entities based on a query. Primarily used to simplify access, improve security, and abstract complex logic.

# what is transactions in sql?
In SQL, a **transaction** is a sequence of one or more SQL operations (such as `INSERT`, `UPDATE`, `DELETE`, etc.) that are executed as a single unit.

# Types of index? 
### . **Clustered Index**

- **Definition**: Sorts the actual data rows of the table based on the index. A table can have only one clustered index because the data can only be sorted in one way.
### **Non-Clustered Index**

- **Definition**: Stores a separate structure from the data that points to the actual data rows. A table can have multiple non-clustered indexes.

# What is Normalization?
**Normalization** in SQL refers to the process of organizing data in a database to reduce redundancy and improve data integrity. It involves dividing large tables into smaller, related tables and defining relationships between them. 

Normalization typically involves applying a series of rules, known as **normal forms**. The most common normal forms are:

### 1. **First Normal Form (1NF)**

- **Rule**: Eliminate repeating groups. Each column contains atomic (indivisible) values, and each record has a unique identifier.
- **Example**: A table with a single column for multiple phone numbers should be split so each phone number has its own column or row.

### 2. **Second Normal Form (2NF)**

- **Rule**: Achieve 1NF and ensure that all non-key attributes are fully dependent on the primary key.
- **Example**: In a table where `OrderID` is the primary key, customer details like `CustomerName` shouldn’t be part of the table unless the entire table is dependent on `OrderID`.

### 3. **Third Normal Form (3NF)**

- **Rule**: Achieve 2NF and remove transitive dependencies (i.e., non-key attributes should not depend on other non-key attributes).
- **Example**: In a table where both `CustomerID` and `CustomerAddress` exist, but `CustomerAddress` depends on `CustomerID`, you should move `CustomerAddress` to a separate table.
# What is Demoralization?

**Denormalization** is a database optimization technique where normalization rules are selectively reversed to improve read performance by reducing the number of joins needed in queries. It involves combining tables or duplicating data in a way that might introduce some redundancy, but at the same time, speeds up data retrieval for complex queries.

# What is Rows?
A **cursor** in SQL is a database object that allows you to retrieve, manipulate, and navigate through rows in a result set **one row at a time**. It's like a pointer that points to a specific row within a query result, allowing for row-by-row processing, which is useful in scenarios where bulk operations aren't feasible or when you need to process each row individually.