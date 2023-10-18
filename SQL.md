# Database

A **database** is an organized collection of structured information, or data, typically stored electronically in a computer system. It is usually managed by a **Database Management System (DBMS)**.<br/>

## SQL - Structured Query Language

**SQL (Structured Query Language)** is a programming language used to store, manipulate, and retrieve data in databases. It is the standard language for **Relational Database Management Systems (RDBMS)**.<br/>
<br/>

### SQL Usage

**SQL is used to:**<br/>
- Communicate with a database.<br/>
- Execute queries against a database.<br/>
- Retrieve data from a database.<br/>
- Insert records into a database.<br/>
- Update records in a database.<br/>
- Delete records from a database.<br/>
- Create new tables in a database.<br/>
- Create stored procedures in a database.<br/>
- Create new databases.<br/>
<br/>

### Types of SQL Commands

1. **DDL (Data Definition Language)**:<br/>
   - Create: Create new database objects (e.g., tables, indexes).<br/>
   - Alter: Modify existing database objects.<br/>
   - Drop: Delete database objects.<br/>
   - Truncate: Remove all records from a table.<br/>
<br/>

2. **DML (Data Manipulation Language)**:<br/>
   - Insert: Add new records to a table.<br/>
   - Update: Modify existing records.<br/>
   - Delete: Remove records from a table.<br/>
<br/>

3. **DCL (Data Control Language)**:<br/>
   - Grant: Provide privileges to users.<br/>
   - Revoke: Remove privileges from users.<br/>
<br/>

4. **TCL (Transaction Control Language)**:<br/>
   - Commit: Save changes made during a transaction.<br/>
   - Rollback: Undo changes made during a transaction.<br/>
   - Savepoint: Set a point in a transaction to which you can later roll back.<br/>
<br/>

5. **DQL (Data Query Language)**:<br/>
   - Select: Retrieve data from a database.<br/>
<br/>

### Common SQL Commands

**Some of the most important SQL commands include:**<br/>

- SELECT: Extracts data from a database.<br/>
- UPDATE: Modifies data in a database.<br/>
- DELETE: Removes data from a database.<br/>
- INSERT INTO: Adds new data into a database.<br/>
- CREATE DATABASE: Creates a new database.<br/>
- ALTER DATABASE: Modifies a database.<br/>
- CREATE TABLE: Creates a new table.<br/>
- ALTER TABLE: Modifies a table.<br/>
- DROP TABLE: Deletes a table.<br/>
- CREATE INDEX: Creates an index for efficient data retrieval.<br/>
- DROP INDEX: Deletes an index.<br/>
<br/>

## MySQL Commands

To interact with a MySQL database, you can use various commands:<br/>

### Change Command Prompt to MySQL Monitor

**To access the MySQL monitor, use the following command:**

```sql
mysql -u root -p
```

You will be prompted to enter the password.
<br/><br/>

### Database Management

1. **Show Databases**: Lists all databases in MySQL.

```sql
SHOW DATABASES;
```
<br/>

2. **Create Database**: Creates a new database.

```sql
CREATE DATABASE Joyel;
```
<br/>

3. **Use Database**: Switch to a specific database to work with its tables.

```sql
USE Joyel;
```
<br/>

4. **Drop Database**: Deletes a database.

```sql
DROP DATABASE Joyel;
```
<br/>

### Table Creation

**Tables are the heart of a database and hold the data. You can create a table using the following syntax:**

```sql
CREATE TABLE tablename (
   column_name data_type,
   column_name data_type
);
```

**For example:**

```sql
CREATE TABLE Morris (
   name VARCHAR(100),
   age INT
);
```
<br/>

**To see the tables created in the database, you can use:
**
```sql
SHOW TABLES;
```

**To view the structure of a table, use:**

```sql
DESC tablename; -- For example, DESC Morris;
```

**To delete a table, you can use:**

```sql
DROP TABLE tablename; -- For example, DROP TABLE Morris;
```
<br/><br/>

### Data Insertion

**To insert data into a table, you can use the following syntax:**

```sql
INSERT INTO table_name (column_names) VALUES (data);
```

**For example:**

```sql
INSERT INTO Morris (name, age) VALUES
("Joyel", 21),
("Arun", 18);
```

**To view the data in a table, use:**

```sql
SELECT * FROM table_name; -- For example, SELECT * FROM Morris;
```

**To retrieve distinct values, use:**

```sql
SELECT DISTINCT column_name FROM table_name; -- For example, SELECT DISTINCT name FROM Morris;
```

