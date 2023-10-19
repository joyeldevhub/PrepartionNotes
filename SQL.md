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
1. The DELETE statement is used to delete existing records in a table.<br/>
Note: Be careful when deleting records in a table! Notice the WHERE clause in the DELETE statement. The WHERE clause specifies which record(s) should be deleted. If you omit the WHERE clause, all records in the table will be deleted!<br/>

```sql
-- **Deleting records where "lastname" is 'kirk'
DELETE FROM labour**
WHERE lastname = 'kirk';

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
| NULL      | Doni     | 22   | NULL       |
| Dell      | Company  | 65   | 563256     |
| Sony      | Company  | 75   | 7854785    |
+-----------+----------+------+------------+
```
The record with "lastname" as 'kirk' has been successfully deleted from the table.<be/>

2. Delete All records in a table.<br/>
-- **Delete all records from the "labour" table**
   DELETE FROM labour;

The "labour" table has been deleted.
<br/><hr/><br/>

### SQL MIN() and MAX() Functions
1. The MIN() function returns the smallest value of the selected column.<br/>

**To get the minimum age:**
```sql
SELECT MIN(age) FROM labour;
```

**Result:**
```
+----------+
| min(age) |
+----------+
|       15 |
+----------+
```
<br/>
2. The MAX() function returns the largest value of the selected column.<br/>

**To get the maximum age:**

```sql
SELECT MAX(age) FROM labour;
```

**Result:**
```
+----------+
| max(age) |
+----------+
|       75 |
+----------+
```
You've found the minimum age to be 15 and the maximum age to be 75 in the "labour" table.
<br/><hr/><br/>

### The SQL COUNT() Function
The COUNT() function returns the number of rows that match a specified criterion.<br/>

1. Count of all records in the "labour" table:
```sql
SELECT COUNT(*) FROM labour;
```
**Result:**
```
+----------+
| count(*) |
+----------+
|       14 |
+----------+
```
< br/>

2. Count of records with an age greater than 22 in the "labour" table:
```sql
SELECT COUNT(age) FROM labour WHERE age > 22;
```
**Result:**
```
+------------+
| count(age) |
+------------+
|          7 |
+------------+
```
< br/>

3. Count of records with a non-null "firstname" in the "labour" table: Null values can't count.
```sql
SELECT COUNT(firstname) FROM labour;
```
**Result:**
```
+------------------+
| count(firstname) |
+------------------+
|               13 |
+------------------+
```
<br/><hr/><br/>

### SQL SUM() Function
The SUM() function returns the total sum of a numeric column.< br/>

1. Sum of all ages in the "labour" table:
```sql
SELECT SUM(age) FROM labour;
```

**Result:**
```
+----------+
| sum(age) |
+----------+
|      412 |
+----------+
```
< br/>

2. Sum of ages for records where age is less than 20 in the "labour" table:
```sql
SELECT SUM(age) FROM labour WHERE age < 20;
```

**Result:**
```
+----------+
| sum(age) |
+----------+
|       51 |
+----------+
```
< br/><hr/><br/>

### SQL AVG() Function
The AVG() function returns the average value of a numeric column. Note: null values are ignored.< br/>

1. Average age of all records in the "labour" table:
```sql
SELECT AVG(age) FROM labour;
```

**Result:**
```
+----------+
| avg(age) |
+----------+
|  29.4286 |
+----------+
```
< br/>

2. Average age of records where age is greater than 25 in the "labour" table:
```sql
SELECT AVG(age) FROM labour WHERE age > 25;
```

**Result:**
```
+----------+
| avg(age) |
+----------+
|  41.6667 |
+----------+
```
< br/><hr/><br/>

### SQL LIKE Operator
The LIKE operator is used in a WHERE clause to search for a specified pattern in a column.<br/>

There are two wildcards often used in conjunction with the LIKE operator:<br/>
* The percent sign % represents zero, one, or multiple characters<br/>
* The underscore sign _ represents one, single character<br/>

1. Select records where the "firstname" starts with 'A':
```sql
SELECT * FROM labour WHERE firstname LIKE 'a%';
```

**Result:**
```
+-----------+----------+------+------------+
| firstname | lastname | age  | phone      |
+-----------+----------+------+------------+
| Alex      | Joyel    |   22 | 6383470145 |
| Arun      | Britto   |   18 | 6383470154 |
| Alex      | Raj      |   25 | 56456856   |
| Ana       | Trujillo |   26 | 258        |
| Antonio   | Moreno   |   28 | 369        |
| Arun      | Arun     |   18 | 3698521478 |
+-----------+----------+------+------------+
```
<br/>

2. Select records where the "firstname" ends with 'a':
```sql
SELECT * FROM labour WHERE firstname LIKE '%a';
```

**Result:**
```
+-----------+----------+------+-------+
| firstname | lastname | age  | phone |
+-----------+----------+------+-------+
| Maria     | Anders   |   27 | 147   |
| Ana       | Trujillo |   26 | 258   |
+-----------+----------+------+-------+
```
<br/>

3. Select records where the "age" starts with '2':
```sql
SELECT * FROM labour WHERE age LIKE '2%';
```

**Result:**
```
+-----------+----------+------+------------+
| firstname | lastname | age  | phone      |
+-----------+----------+------+------------+
| Alex      | Joyel    |   22 | 6383470145 |
| Alex      | Raj      |   25 | 56456856   |
| Maria     | Anders   |   27 | 147        |
| Ana       | Trujillo |   26 | 258        |
| Antonio   | Moreno   |   28 | 369        |
| Thomas    | Hardy    |   29 | 1047       |
| Joyel     | Raj      |   20 | 1258       |
| Margret   | Chau     |   22 | 564615352  |
| NULL      | Doni     |   22 | NULL       |
+-----------+----------+------+------------+
```
<br/>

4. Select records where the "firstname" starts with 'A' or the "age" starts with '1':
```sql
SELECT * FROM labour WHERE firstname LIKE 'A%' OR age LIKE '1%';
```

**Result:**
```
+-----------+----------+------+------------+
| firstname | lastname | age  | phone      |
+-----------+----------+------+------------+
| Alex      | Joyel    |   22 | 6383470145 |
| Arun      | Britto   |   18 | 6383470154 |
| Alex      | Raj      |   25 | 56456856   |
| Ana       | Trujillo |   26 | 258        |
| Antonio   | Moreno   |   28 | 369        |
| Arun      | Arun     |   18 | 3698521478 |
| Karthi    | kaki     |   15 | 258963369  |
+-----------+----------+------+------------+
```
<br/>
You've used the `LIKE` operator with a pattern to retrieve records where the "lastname" matches the pattern 'Bri__o' (where '_' represents any single character).<br/>

```sql
SELECT * FROM labour WHERE lastname LIKE 'Bri__o';
```

**Result:**
```
+-----------+----------+------+------------+
| firstname | lastname | age  | phone      |
+-----------+----------+------+------------+
| Arun      | Britto   |   18 | 6383470154 |
+-----------+----------+------+------------+
```
<br/><hr/><br/>

### SQL Wildcards
A wildcard character is used to substitute one or more characters in a string. Wildcard characters are used with the LIKE operator. The LIKE operator is used in a WHERE clause to search for a specified pattern in a column.< br/>

**%** 	- Represents zero or more characters.<br/>
**_**	   - Represents a single character.<br/>
**[]**	- Represents any single character within the brackets.<br/>
**^** 	- Represents any character not in the brackets.<br/>
**-** 	- Represents any single character within the specified range.<br/>
**{}**	- Represents any escaped character.<br/>
<br/>

1. Using the % Wildcard:<br/>
**Records where "firstname" starts with 'M':**
```sql
SELECT * FROM labour WHERE firstname LIKE 'M%';
```

**Result:**
```
+-----------+----------+------+-----------+
| firstname | lastname | age  | phone     |
+-----------+----------+------+-----------+
| Maria     | Anders   |   27 | 147       |
| Margret   | Chau     |   22 | 564615352 |
+-----------+----------+------+-----------+
```
<br/>

**Records where "lastname" contains 'ruj':**
```sql
SELECT * FROM labour WHERE lastname LIKE '%ruj%';
```

**Result:**
```
+-----------+----------+------+-------+
| firstname | lastname | age  | phone |
+-----------+----------+------+-------+
| Ana       | Trujillo |   26 | 258   |
+-----------+----------+------+-------+
```
<br/><br/>

2. Using the _ Wildcard:<br/>
**Records where "firstname" matches the pattern 'Ar_n' (where '_' represents any single character):**
```sql
SELECT * FROM labour WHERE firstname LIKE 'Ar_n';
```

**Result:**
```
+-----------+----------+------+------------+
| firstname | lastname | age  | phone      |
+-----------+----------+------+------------+
| Arun      | Britto   |   18 | 6383470154 |
| Arun      | Arun     |   18 | 3698521478 |
+-----------+----------+------+------------+
```
<br/>

**Records where "lastname" matches the pattern 'ch__' (where '_' represents any single character):**
```sql
SELECT * FROM labour WHERE lastname LIKE 'ch__';
```

**Result:**
```
+-----------+----------+------+-----------+
| firstname | lastname | age  | phone     |
+-----------+----------+------+-----------+
| Margret   | Chau     |   22 | 564615352 |
+-----------+----------+------+-----------+
```
<br/><hr/><br/>

### MySQL IN Operator
The IN operator allows you to specify multiple values in a WHERE clause. The IN operator is a shorthand for multiple OR conditions.<br/>
1. Records where "firstname" is 'Alex', 'Arun', or 'Joyel':
```sql
SELECT * FROM labour WHERE firstname IN ('Alex', 'Arun', 'Joyel');
```

**Result:**
```
+-----------+----------+------+------------+
| firstname | lastname | age  | phone      |
+-----------+----------+------+------------+
| Alex      | Joyel    |   22 | 6383470145 |
| Arun      | Britto   |   18 | 6383470154 |
| Alex      | Raj      |   25 | 56456856   |
| Joyel     | Raj      |   20 | 1258       |
| Arun      | Arun     |   18 | 3698521478 |
+-----------+----------+------+------------+
```
<br/>

2. Records where "firstname" is not 'Alex', 'Arun', or 'Joyel':
```sql
SELECT * FROM labour WHERE firstname NOT IN ('Alex', 'Arun', 'Joyel');
```

**Result:**
```
+-----------+----------+------+-----------+
| firstname | lastname | age  | phone     |
+-----------+----------+------+-----------+
| Maria     | Anders   |   27 | 147       |
| Ana       | Trujillo |   26 | 258       |
| Antonio   | Moreno   |   28 | 369       |
| Thomas    | Hardy    |   29 | 1047      |
| Karthi    | kaki     |   15 | 258963369 |
| Margret   | Chau     |   22 | 564615352 |
| Dell      | Company  |   65 | 563256    |
| Sony      | Company  |   75 | 7854785   |
+-----------+----------+------+-----------+
```
The queries successfully filtered records based on the "firstname" column using the `IN` and `NOT IN` operators.
<br/><hr/><br/>

### MySQL BETWEEN Operator
The BETWEEN operator selects values within a given range. The values can be numbers, text, or dates. The BETWEEN operator is inclusive: begin and end values are included.<br/>

1. Records where "firstname" is between 'Ana' and 'Margret':
```sql
SELECT * FROM labour WHERE firstname BETWEEN 'Ana' AND 'Margret';
```

**Result:**
```
+-----------+----------+------+------------+
| firstname | lastname | age  | phone      |
+-----------+----------+------+------------+
| Arun      | Britto   |   18 | 6383470154 |
| Ana       | Trujillo |   26 | 258        |
| Antonio   | Moreno   |   28 | 369        |
| Joyel     | Raj      |   20 | 1258       |
| Arun      | Arun     |   18 | 3698521478 |
| Karthi    | kaki     |   15 | 258963369  |
| Margret   | Chau     |   22 | 564615352  |
| Dell      | Company  |   65 | 563256     |
+-----------+----------+------+------------+
```
<br/>

2. The same records sorted by "firstname":
```sql
SELECT * FROM labour WHERE firstname BETWEEN 'Ana' AND 'Margret' ORDER BY firstname;
```

**Result:**
```
+-----------+----------+------+------------+
| firstname | lastname | age  | phone      |
+-----------+----------+------+------------+
| Ana       | Trujillo |   26 | 258        |
| Antonio   | Moreno   |   28 | 369        |
| Arun      | Britto   |   18 | 6383470154 |
| Arun      | Arun     |   18 | 3698521478 |
| Dell      | Company  |   65 | 563256     |
| Joyel     | Raj      |   20 | 1258       |
| Karthi    | kaki     |   15 | 258963369  |
| Margret   | Chau     |   22 | 564615352  |
+-----------+----------+------+------------+
```
<br/>

3. Records where "age" is not between 29 and 75, sorted by "age":
```sql
SELECT * FROM labour WHERE age NOT BETWEEN 29 AND 75 ORDER BY age;
```

**Result:**
```
+-----------+----------+------+------------+
| firstname | lastname | age  | phone      |
+-----------+----------+------+------------+
| Karthi    | kaki     |   15 | 258963369  |
| Arun      | Britto   |   18 | 6383470154 |
| Arun      | Arun     |   18 | 3698521478 |
| Joyel     | Raj      |   20 | 1258       |
| Alex      | Joyel    |   22 | 6383470145 |
| Margret   | Chau     |   22 | 564615352  |
| NULL      | Doni     |   22 | NULL       |
| Alex      | Raj      |   25 | 56456856   |
| Ana       | Trujillo |   26 | 258        |
| Maria     | Anders   |   27 | 147        |
| Antonio   | Moreno   |   28 | 369        |
+-----------+----------+------+------------+
```
<br/><hr/><br/>

### MySQL Aliases
* Aliases are used to give a table, or a column in a table, a temporary name.<br/>
* Aliases are often used to make column names more readable.<br/>
* An alias only exists for the duration of that query.<br/>
* An alias is created with the AS keyword.<br/>
<br/>
1. A query that selects "firstname" with an alias "Names":
```sql
SELECT firstname AS Names FROM labour;
```

**Result:**
```
+---------+
| Names   |
+---------+
| Alex    |
| Arun    |
| Alex    |
| Maria   |
| Ana     |
| Antonio |
| Thomas  |
| Joyel   |
| Arun    |
| Karthi  |
| Margret |
| NULL    |
| Dell    |
| Sony    |
+---------+
```
<br/>

2. A query that concatenates "firstname" and "lastname" with an alias "Names":
```sql
SELECT CONCAT(firstname, ' ', lastname) AS Names FROM labour;
```

**Result:**
```
+----------------+
| Names          |
+----------------+
| Alex Joyel     |
| Arun Britto    |
| Alex Raj       |
| Maria Anders   |
| Ana Trujillo   |
| Antonio Moreno |
| Thomas Hardy   |
| Joyel Raj      |
| Arun Arun      |
| Karthi kaki    |
| Margret Chau   |
| NULL           |
| Dell Company   |
| Sony Company   |
+----------------+
```
<br/><hr/><br/>

### MySQL PRIMARY KEY
The PRIMARY KEY constraint uniquely identifies each record in a table. Primary keys must contain UNIQUE values, and **cannot contain NULL values**. A table can have only ONE primary key; and in the table, this primary key can consist of single or multiple columns (fields).<br/>

**Create Primary Key Table:**

```sql
CREATE TABLE Employee (
    ID INT NOT NULL,
    Firstname VARCHAR(100),
    Lastname VARCHAR(100) NOT NULL,
    DateOfBirth VARCHAR(100),
    Gender VARCHAR(5),
    DepartmentID INT,
    PRIMARY KEY (ID)
);

**Now, you can insert Employee information:**
INSERT INTO Employee (ID, Firstname, Lastname, DateOfBirth, Gender, DepartmentID)
VALUES
    (1001, 'Aishwarya', 'Jayaram', '2005-04-24', 'F', 11),
    (1002, 'Anand', 'Venkat', '2005-05-22', 'M', 12),
    (1003, 'Bala', 'Sundaram', '2004-11-02', 'M', 13),
    (1004, 'Deepa', 'Mani', '2004-12-09', 'F', 11),
    (1005, 'Deepa', 'Mahesh', '2005-05-29', 'F', 14),
    (1006, 'Gokul', 'Ram', '2004-11-27', 'M', 13),
    (1007, 'Shreya', 'Gopi', '2005-06-20', 'F', 17),
    (1008, 'Abdul', 'Rahman', '2005-07-30', 'M', 18);

SELECT * FROM Employee;
```
<br/>

**Here are the records in the "Employee" table:**
```sql
+------+-----------+----------+-------------+--------+--------------+
| ID   | Firstname | Lastname | DateOfBirth | Gender | DepartmentID |
+------+-----------+----------+-------------+--------+--------------+
| 1001 | Aishwarya | Jayaram  | 2005-04-24  | F      | 11           |
| 1002 | Anand     | Venkat   | 2005-05-22  | M      | 12           |
| 1003 | Bala      | Sundaram | 2004-11-02  | M      | 13           |
| 1004 | Deepa     | Mani     | 2004-12-09  | F      | 11           |
| 1005 | Deepa     | Mahesh   | 2005-05-29  | F      | 14           |
| 1006 | Gokul     | Ram      | 2004-11-27  | M      | 13           |
| 1007 | Shreya    | Gopi     | 2005-06-20  | F      | 17           |
| 1008 | Abdul     | Rahman   | 2005-07-30  | M      | 18           |
+------+-----------+----------+-------------+--------+--------------+
```
This code creates the "Employee" table, inserts data into it, and then retrieves all records from the table.
<br/><hr/><br/>

### MySQL FOREIGN KEY
The FOREIGN KEY constraint is used to prevent actions that would destroy links between tables. A FOREIGN KEY is a field (or collection of fields) in one table, that refers to the PRIMARY KEY in another table. The table with the foreign key is called the child table, and the table with the primary key is called the referenced or parent table.<br/>

**Create Foreign Key**

```sql
CREATE TABLE Department (
    DepartmentID INT NOT NULL,
    DepartmentName VARCHAR(100) NOT NULL,
    ID INT,
    PRIMARY KEY (DepartmentID),
    FOREIGN KEY (ID) REFERENCES Employee (ID)
);
```
<br/>

**Now, you can insert department information:**

```sql
INSERT INTO Department (DepartmentID, DepartmentName)
VALUES
    (11, 'Engineering'),
    (12, 'Finance'),
    (13, 'Sales'),
    (14, 'Marketing'),
    (15, 'Human Resources'),
    (16, 'IT');
```
**Here are the records in the "Department" table:**

```
+--------------+-----------------+------+
| DepartmentID | DepartmentName  | ID   |
+--------------+-----------------+------+
|           11 | Engineering     | NULL |
|           12 | Finance         | NULL |
|           13 | Sales           | NULL |
|           14 | Marketing       | NULL |
|           15 | Human Resources | NULL |
|           16 | IT              | NULL |
+--------------+-----------------+------+
```
<br/><hr/><br/>

### MySQL Joins
A JOIN clause is used to combine rows from two or more tables, based on a related column between them.<br/>

* INNER JOIN: Returns records that have matching values in both tables.<br/>
* LEFT JOIN: Returns all records from the left table, and the matched records from the right table.<br/>
* RIGHT JOIN: Returns all records from the right table, and the matched records from the left table.<br/>
* CROSS JOIN: Returns all records from both tables.<br/>
<br/>

**1. MySQL INNER JOIN Keyword:**<br/>
To recreate the `employee` and `department` tables and perform the `INNER JOIN`, follow these steps:

```sql
SELECT * FROM Employee
INNER JOIN Department ON Employee.DepartmentID = Department.DepartmentID;
```
This will provide you with the joined result between the two tables.
<br/>

Certainly, here's the recreated query with the `INNER JOIN` between the "Employee" and "Department" tables:

```sql
SELECT employee.firstname, employee.lastname, department.departmentid
FROM employee
INNER JOIN department ON employee.departmentid = department.departmentid;
```
This query selects the first name and last name of employees along with their corresponding department IDs from the "Employee" and "Department" tables.
<br/><br/>

2. MySQL OUTER JOIN Keyword:**
* Right outer join
* Left outer join
* full outer join



















