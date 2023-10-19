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
<br/><hr/><br/>

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
<br/><hr/><br/>

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
<br/><hr/><br/>

### SQL Data Insertion

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
<br/><hr/><br/>

### SQL Where clause:
WHERE clause specifies criteria that field values must meet for the records that contain the values to be included in the query results.

**I'll recreate the SQL queries you provided along with the corresponding results:**

```sql
-- **Original Data in "labour" Table**
SELECT * FROM labour;
```

**Result:**
```
+-----------+----------+------+------------+
| firstname | lastname | age  | phone      |
+-----------+----------+------+------------+
| Alex      | Joyel    | 22   | 6383470145 |
| Arun      | Britto   | 18   | 6383470154 |
| Alex      | Raj      | 25   | 56456856   |
| Maria     | Anders   | 27   | 147        |
| Ana       | Trujillo | 26   | 258        |
| Antonio   | Moreno   | 28   | 369        |
| Thomas    | Hardy    | 29   | 1047       |
| Christina | Berglund | 20   | 1258       |
+-----------+----------+------+------------+
```
<br/>

**Now, let's recreate the queries:**

```sql
-- **Selecting records where age is 25**
SELECT * FROM labour WHERE age = 25;
```

**Result:**
```
+-----------+----------+------+----------+
| firstname | lastname | age  | phone    |
+-----------+----------+------+----------+
| Alex      | Raj      | 25   | 56456856 |
+-----------+----------+------+----------+
```
<br/>

```sql
-- **Selecting records where age is greater than 18**
SELECT * FROM labour WHERE age > 18;
```

**Result:**
```
+-----------+----------+------+------------+
| firstname | lastname | age  | phone      |
+-----------+----------+------+------------+
| Alex      | Joyel    | 22   | 6383470145 |
| Alex      | Raj      | 25   | 56456856   |
| Maria     | Anders   | 27   | 147        |
| Ana       | Trujillo | 26   | 258        |
| Antonio   | Moreno   | 28   | 369        |
| Thomas    | Hardy    | 29   | 1047       |
| Christina | Berglund | 20   | 1258       |
+-----------+----------+------+------------+
```
<br/>

```sql
-- **Selecting records where age is less than 25**
SELECT * FROM labour WHERE age < 25;
```

**Result:**
```
+-----------+----------+------+------------+
| firstname | lastname | age  | phone      |
+-----------+----------+------+------------+
| Alex      | Joyel    | 22   | 6383470145 |
| Arun      | Britto   | 18   | 6383470154 |
| Christina | Berglund | 20   | 1258       |
+-----------+----------+------+------------+
```
<br/>

```sql
-- **Selecting records where age is greater than or equal to 18**
SELECT * FROM labour WHERE age >= 18;
```

**Result:**
```
+-----------+----------+------+------------+
| firstname | lastname | age  | phone      |
+-----------+----------+------+------------+
| Alex      | Joyel    | 22   | 6383470145 |
| Arun      | Britto   | 18   | 6383470154 |
| Alex      | Raj      | 25   | 56456856   |
| Maria     | Anders   | 27   | 147        |
| Ana       | Trujillo | 26   | 258        |
| Antonio   | Moreno   | 28   | 369        |
| Thomas    | Hardy    | 29   | 1047       |
| Christina | Berglund | 20   | 1258       |
+-----------+----------+------+------------+
```
<br/>

```sql
-- **Selecting records where age is not equal to 26**
SELECT * FROM labour WHERE age <> 26;
```

**Result:**
```
+-----------+----------+------+------------+
| firstname | lastname | age  | phone      |
+-----------+----------+------+------------+
| Alex      | Joyel    | 22   | 6383470145 |
| Arun      | Britto   | 18   | 6383470154 |
| Alex      | Raj      | 25   | 56456856   |
| Maria     | Anders   | 27   | 147        |
| Antonio   | Moreno   | 28   | 369        |
| Thomas    | Hardy    | 29   | 1047       |
| Christina | Berglund | 20   | 1258       |
+-----------+----------+------+------------+
```
<br/>

```sql
-- **Selecting records where age is between 18 and 25**
SELECT * FROM labour WHERE age BETWEEN 18 AND 25;
```

**Result:**
```
+-----------+----------+------+------------+
| firstname | lastname | age  | phone      |
+-----------+----------+------+------------+
| Alex      | Joyel    | 22   | 6383470145 |
| Arun      | Britto   | 18   | 6383470154 |
| Alex      | Raj      | 25   | 56456856   |
| Christina | Berglund | 20   | 1258       |
+-----------+----------+------+------------+
```
<br/>

```sql
-- **Selecting records where firstname starts with 'A'**
SELECT * FROM labour WHERE firstname LIKE 'A%';
```

**Result:**
```
+-----------+----------+------+------------+
| firstname | lastname | age  | phone      |
+-----------+----------+------+------------+
| Alex      | Joyel    | 22   | 6383470145 |
| Arun      | Britto   | 18   | 6383470154 |
| Alex      | Raj      | 25   | 56456856   |
| Ana       | Trujillo | 26   | 258        |
| Antonio   | Moreno   | 28   | 369        |
+-----------+----------+------+------------+
```
<br/>

```sql
-- **Selecting records where lastname is 'Joyel' or 'Trujillo'**
SELECT * FROM labour WHERE lastname IN ('Joyel', 'Trujillo');
```

**Result:**
```
+-----------+----------+------+------------+
| firstname | lastname | age  | phone      |
+-----------+----------+------+------------+
| Alex      | Joyel    | 22   | 6383470145 |
| Ana       | Trujillo | 26   | 258        |
+-----------+----------+------+------------+
```
<br/><hr/><br/>

### SQL Order By
The ORDER BY keyword is used to sort the result-set in ascending or descending order.<br/>

**Now, let's recreate the SQL queries for ordering records:
**<br/>

```sql
-- **Ordering by "firstname" in ascending order**
SELECT * FROM labour ORDER BY firstname;
```

**Result** (Ordered by "firstname" in ascending order):
```
+-----------+----------+------+------------+
| firstname | lastname | age  | phone      |
+-----------+----------+------+------------+
| Alex      | Joyel    | 22   | 6383470145 |
| Alex      | Raj      | 25   | 56456856   |
| Ana       | Trujillo | 26   | 258        |
| Antonio   | Moreno   | 28   | 369        |
| Arun      | Britto   | 18   | 6383470154 |
| Christina | Berglund | 20   | 1258       |
| Maria     | Anders   | 27   | 147        |
| Thomas    | Hardy    | 29   | 1047       |
+-----------+----------+------+------------+
```
<br/>

```sql
-- **Ordering by "age" in descending order**
SELECT * FROM labour ORDER BY age DESC;
```

**Result** (Ordered by "age" in descending order):
```
+-----------+----------+------+------------+
| firstname | lastname | age  | phone      |
+-----------+----------+------+------------+
| Thomas    | Hardy    | 29   | 1047       |
| Antonio   | Moreno   | 28   | 369        |
| Maria     | Anders   | 27   | 147        |
| Ana       | Trujillo | 26   | 258        |
| Alex      | Raj      | 25   | 56456856   |
| Alex      | Joyel    | 22   | 6383470145 |
| Christina | Berglund | 20   | 1258       |
| Arun      | Britto   | 18   | 6383470154 |
+-----------+----------+------+------------+
```
<br/>

```sql
-- **Ordering by "lastname" in ascending order**
SELECT * FROM labour ORDER BY lastname ASC;
```

**Result** (Ordered by "lastname" in ascending order):
```
+-----------+----------+------+------------+
| firstname | lastname | age  | phone      |
+-----------+----------+------+------------+
| Maria     | Anders   | 27   | 147        |
| Christina | Berglund | 20   | 1258       |
| Arun      | Britto   | 18   | 6383470154 |
| Thomas    | Hardy    | 29   | 1047       |
| Alex      | Joyel    | 22   | 6383470145 |
| Antonio   | Moreno   | 28   | 369        |
| Alex      | Raj      | 25   | 56456856   |
| Ana       | Trujillo | 26   | 258        |
+-----------+----------+------+------------+
```
<br/><hr/><br/>

### SQL AND Operator
The WHERE clause can contain one or many AND operators. The AND operator is used to filter records based on more than one condition.<br/>

```sql
-- **Original Data in "labour" Table**
SELECT * FROM labour;
```

**Result:**
```
+-----------+----------+------+------------+
| firstname | lastname | age  | phone      |
+-----------+----------+------+------------+
| Alex      | Joyel    | 22   | 6383470145 |
| Arun      | Britto   | 18   | 6383470154 |
| Alex      | Raj      | 25   | 56456856   |
| Maria     | Anders   | 27   | 147        |
| Ana       | Trujillo | 26   | 258        |
| Antonio   | Moreno   | 28   | 369        |
| Thomas    | Hardy    | 29   | 1047       |
| Christina | Berglund | 20   | 1258       |
| Arun      | Arun     | 18   | 3698521478 |
| Karthi    | kaki     | 15   | 258963369  |
| Margret   | Chau     | 22   | 564615352  |
+-----------+----------+------+------------+
```
<br/>

**Now, let's recreate the SQL queries:**

```sql
-- **Selecting records where firstname starts with 'A' and age is 18**
SELECT * FROM labour WHERE firstname LIKE 'A%' AND age = 18;
```

**Result:**
```
+-----------+----------+------+------------+
| firstname | lastname | age  | phone      |
+-----------+----------+------+------------+
| Arun      | Britto   | 18   | 6383470154 |
| Arun      | Arun     | 18   | 3698521478 |
+-----------+----------+------+------------+
```
<br/>

```sql
-- **Selecting records where firstname starts with 'A' and age is either 18 or 29**
SELECT * FROM labour WHERE firstname LIKE 'A%' AND (age = 18 OR age = 29);
```

**Result:**
```
+-----------+----------+------+------------+
| firstname | lastname | age  | phone      |
+-----------+----------+------+------------+
| Arun      | Britto   | 18   | 6383470154 |
| Arun      | Arun     | 18   | 3698521478 |
+-----------+----------+------+------------+
```
<br/>

```sql
-- **Selecting records where firstname starts with 'A' and age is either 18 or less than 29**
SELECT * FROM labour WHERE firstname LIKE 'A%' AND (age = 18 OR age < 29);
```

**Result:**
```
+-----------+----------+------+------------+
| firstname | lastname | age  | phone      |
+-----------+----------+------+------------+
| Alex      | Joyel    | 22   | 6383470145 |
| Arun      | Britto   | 18   | 6383470154 |
| Alex      | Raj      | 25   | 56456856   |
| Ana       | Trujillo | 26   | 258        |
| Antonio   | Moreno   | 28   | 369        |
| Arun      | Arun     | 18   | 3698521478 |
+-----------+----------+------+------------+
```
<br/><hr/><br/>

### SQL OR Operator
The WHERE clause can contain one or more OR operators. The OR operator is used to filter records based on more than one condition.<br/>

```sql
-- **Selecting records where firstname starts with 'A', lastname ends with 'o', or age is less than 18**
SELECT * FROM labour WHERE firstname LIKE 'A%' OR lastname LIKE '%o' OR age < 18;
```

**Result:**
```
+-----------+----------+------+------------+
| firstname | lastname | age  | phone      |
+-----------+----------+------+------------+
| Alex      | Joyel    | 22   | 6383470145 |
| Arun      | Britto   | 18   | 6383470154 |
| Alex      | Raj      | 25   | 56456856   |
| Ana       | Trujillo | 26   | 258        |
| Antonio   | Moreno   | 28   | 369        |
| Arun      | Arun     | 18   | 3698521478 |
| Karthi    | kaki     | 15   | 258963369  |
+-----------+----------+------+------------+
```
<br/>

```sql
-- **Selecting records where firstname is 'Alex', lastname is 'Arun', or age is 18**
SELECT * FROM labour WHERE firstname = 'Alex' OR lastname = 'Arun' OR age = 18;
```

**Result:**
```
+-----------+----------+------+------------+
| firstname | lastname | age  | phone      |
+-----------+----------+------+------------+
| Alex      | Joyel    | 22   | 6383470145 |
| Arun      | Britto   | 18   | 6383470154 |
| Alex      | Raj      | 25   | 56456856   |
| Arun      | Arun     | 18   | 3698521478 |
+-----------+----------+------+------------+
```
<br/><hr/><br/>

### SQL NOT Operator
The NOT operator is used in combination with other operators to give the opposite result, also called the negative result.<br/>

```sql
-- **Selecting records where the age is not 18**
SELECT * FROM labour WHERE NOT age = 18;
```

**Result:**
```
+-----------+----------+------+------------+
| firstname | lastname | age  | phone      |
+-----------+----------+------+------------+
| Alex      | Joyel    | 22   | 6383470145 |
| Alex      | Raj      | 25   | 56456856   |
| Maria     | Anders   | 27   | 147        |
| Ana       | Trujillo | 26   | 258        |
| Antonio   | Moreno   | 28   | 369        |
| Thomas    | Hardy    | 29   | 1047       |
| Christina | Berglund | 20   | 1258       |
| Karthi    | kaki     | 15   | 258963369  |
| Margret   | Chau     | 22   | 564615352  |
+-----------+----------+------+------------+
```
<br/>

```sql
-- **Selecting records where the firstname does not start with 'A'**
SELECT * FROM labour WHERE NOT firstname LIKE 'A%';
```

**Result:**
```
+-----------+----------+------+-----------+
| firstname | lastname | age  | phone     |
+-----------+----------+------+-----------+
| Maria     | Anders   | 27   | 147       |
| Thomas    | Hardy    | 29   | 1047      |
| Christina | Berglund | 20   | 1258      |
| Karthi    | kaki     | 15   | 258963369 |
| Margret   | Chau     | 22   | 564615352 |
+-----------+----------+------+-----------+
```
<br/><hr/><br/>

### SQL Insert Statement
The INSERT INTO statement is used to insert new records in a table.<br/>
1. Specify both the column names and the values to be inserted:<br/>
   
```sql
-- **Inserting new records into the "labour" table**
INSERT INTO labour (lastname, age)
VALUES ('kirk', 30),
       ('Doni', 22);

-- **Viewing the updated "labour" table**
SELECT * FROM labour;
```

**Result:**
```
+-----------+----------+------+------------+
| firstname | lastname | age  | phone      |
+-----------+----------+------+------------+
| Alex      | Joyel    | 22   | 6383470145 |
| Arun      | Britto   | 18   | 6383470154 |
| Alex      | Raj      | 25   | 56456856   |
| Maria     | Anders   | 27   | 147        |
| Ana       | Trujillo | 26   | 258        |
| Antonio   | Moreno   | 28   | 369        |
| Thomas    | Hardy    | 29   | 1047       |
| Christina | Berglund | 20   | 1258       |
| Arun      | Arun     | 18   | 3698521478 |
| Karthi    | kaki     | 15   | 258963369  |
| Margret   | Chau     | 22   | 564615352  |
| NULL      | kirk     | 30   | NULL       |
| NULL      | Doni     | 22   | NULL       |
+-----------+----------+------+------------+
```
<br/>

2. If you are adding values for all the columns of the table, you do not need to specify the column names in the SQL query. However, make sure the order of the values is in the same order as the columns in the table.<br/>

```sql
-- **Inserting new records into the "labour" table**
INSERT INTO labour (firstname, lastname, age, phone)
VALUES ('Dell', 'Company', 65, 563256),
       ('HP', 'Company', 75, 7854785);

-- **Viewing the updated "labour" table**
SELECT * FROM labour;
```

**Result:**
```
+-----------+----------+------+----------+
| firstname | lastname | age  | phone    |
+-----------+----------+------+----------+
| Alex      | Joyel    | 22   | 6383470145 |
| Arun      | Britto   | 18   | 6383470154 |
| Alex      | Raj      | 25   | 56456856   |
| Maria     | Anders   | 27   | 147        |
| Ana       | Trujillo | 26   | 258        |
| Antonio   | Moreno   | 28   | 369        |
| Thomas    | Hardy    | 29   | 1047       |
| Christina | Berglund | 20   | 1258       |
| Arun      | Arun     | 18   | 3698521478 |
| Karthi    | kaki     | 15   | 258963369  |
| Margret   | Chau     | 22   | 564615352  |
| NULL      | kirk     | 30   | NULL       |
| NULL      | Doni     | 22   | NULL       |
| Dell      | Company  | 65   | 563256    |
| HP        | Company  | 75   | 7854785   |
+-----------+----------+------+----------+
```
<br/><hr/><br/>

### SQL Null Values
A field with a NULL value is a field with no value. If a field in a table is optional, it is possible to insert a new record or update a record without adding a value to this field.<br/>

1. The IS NULL operator is used to test for empty values (NULL values).<br/>

```sql
-- **Selecting records where firstname is NULL**
SELECT * FROM labour WHERE firstname IS NULL;
```

**Result:**
```
+-----------+----------+------+-------+
| firstname | lastname | age  | phone |
+-----------+----------+------+-------+
| NULL      | kirk     | 30   | NULL  |
| NULL      | Doni     | 22   | NULL  |
+-----------+----------+------+-------+
```
<br/>

2. The IS NOT NULL operator is used to test for non-empty values (NOT NULL values).<br/>

```sql
-- **Selecting records where firstname is not NULL**
SELECT * FROM labour WHERE firstname IS NOT NULL;
```

**Result:**
```
+-----------+----------+------+------------+
| firstname | lastname | age  | phone      |
+-----------+----------+------+------------+
| Alex      | Joyel    | 22   | 6383470145 |
| Arun      | Britto   | 18   | 6383470154 |
| Alex      | Raj      | 25   | 56456856   |
| Maria     | Anders   | 27   | 147        |
| Ana       | Trujillo | 26   | 258        |
| Antonio   | Moreno   | 28   | 369        |
| Thomas    | Hardy    | 29   | 1047       |
| Christina | Berglund | 20   | 1258       |
| Arun      | Arun     | 18   | 3698521478 |
| Karthi    | kaki     | 15   | 258963369  |
| Margret   | Chau     | 22   | 564615352  |
| Dell      | Company  | 65   | 563256     |
| HP        | Company  | 75   | 7854785    |
+-----------+----------+------+------------+
```
<br/><hr/><br/>


### SQL Update Statement
The UPDATE statement is used to modify the existing records in a table.<br/>

```sql
-- **Updating records in the "labour" table where age is 20**
UPDATE labour
SET firstname = 'Joyel', lastname = 'Raj'
WHERE age = 20;

-- **Viewing the updated "labour" table**
SELECT * FROM labour;
```

**Result:**
```
+-----------+----------+------+------------+
| firstname | lastname | age  | phone      |
+-----------+----------+------+------------+
| Alex      | Joyel    | 22   | 6383470145 |
| Arun      | Britto   | 18   | 6383470154 |
| Alex      | Raj      | 25   | 56456856   |
| Maria     | Anders   | 27   | 147        |
| Ana       | Trujillo | 26   | 258        |
| Antonio   | Moreno   | 28   | 369        |
| Thomas    | Hardy    | 29   | 1047       |
| Joyel     | Raj      | 20   | 1258       |  <-- Updated record
| Arun      | Arun     | 18   | 3698521478 |
| Karthi    | kaki     | 15   | 258963369  |
| Margret   | Chau     | 22   | 564615352  |
| NULL      | kirk     | 30   | NULL       |
| NULL      | Doni     | 22   | NULL       |
| Dell      | Company  | 65   | 563256     |
| HP        | Company  | 75   | 7854785    |
+-----------+----------+------+------------+
```
The records where the age was 20 have been successfully updated with the first name "Joyel" and last name "Raj."<br/>

```sql
-- **Updating the "firstname" from 'HP' to 'Sony' in the "labour" table**
UPDATE labour
SET firstname = 'Sony'
WHERE firstname = 'HP';

-- **Viewing the updated "labour" table**
SELECT * FROM labour;
```

**Result:**
```
+-----------+----------+------+------------+
| firstname | lastname | age  | phone      |
+-----------+----------+------+------------+
| Alex      | Joyel    | 22   | 6383470145 |
| Arun      | Britto   | 18   | 6383470154 |
| Alex      | Raj      | 25   | 56456856   |
| Maria     | Anders   | 27   | 147        |
| Ana       | Trujillo | 26   | 258        |
| Antonio   | Moreno   | 28   | 369        |
| Thomas    | Hardy    | 29   | 1047       |
| Joyel     | Raj      | 20   | 1258       |
| Arun      | Arun     | 18   | 3698521478 |
| Karthi    | kaki     | 15   | 258963369  |
| Margret   | Chau     | 22   | 564615352  |
| NULL      | kirk     | 30   | NULL       |
| NULL      | Doni     | 22   | NULL       |
| Dell      | Company  | 65   | 563256     |
| Sony      | Company  | 75   | 7854785    |  <-- Updated record
+-----------+----------+------+------------+
```
The record with "firstname" as 'HP' has been successfully updated to 'Sony.'
<br/><hr/><br/>

### SQL Delete Statement







   
