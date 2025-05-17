# Experiment 2: DDL Commands

## AIM
To study and implement DDL commands and different types of constraints.

## THEORY

### 1. CREATE
Used to create a new relation (table).

**Syntax:**
```sql
CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);
```
### 2. ALTER
Used to add, modify, drop, or rename fields in an existing relation.
(a) ADD
```sql
ALTER TABLE std ADD (Address CHAR(10));
```
(b) MODIFY
```sql
ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));
```
(c) DROP
```sql
ALTER TABLE relation_name DROP COLUMN field_name;
```
(d) RENAME
```sql
ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;
```
### 3. DROP TABLE
Used to permanently delete the structure and data of a table.
```sql
DROP TABLE relation_name;
```
### 4. RENAME
Used to rename an existing database object.
```sql
RENAME TABLE old_relation_name TO new_relation_name;
```
### CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).
### 1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);
```
### 2. UNIQUE
Ensures that values in a column are unique.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);
```
### 3. CHECK
Specifies a condition that each row must satisfy.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);
```
### 4. PRIMARY KEY
Used to uniquely identify each record in a table.
Properties:
Must contain unique values.
Cannot be null.
Should contain minimal fields.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);
```
### 5. FOREIGN KEY
Used to reference the primary key of another table.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);
```
### 6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:
```sql
CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);
```

**Question 1**

![image](https://github.com/user-attachments/assets/8f856dc6-1930-4c78-9525-717a4849cd1f)
~~~
insert into Products(Name,Category,price,Stock)
values("Smartphone","Electronics",800,150),
("Headphones","Accessories",200,300);
~~~
**Output:**

![image](https://github.com/user-attachments/assets/c4c32ba0-168c-4e75-a1fc-1c4cdd529e22)



**Question 2**

![image](https://github.com/user-attachments/assets/7a9e4a9a-8ffc-42be-b7dd-f9652d832b73)
~~~
 create table item(
item_id varchar(50) primary key,item_desc varchar(50) not null,
rate int not null,icom_id char(4),foreign key(icom_id)
references company(com_id) on update set null on delete set null);
~~~
**Output:**


![image](https://github.com/user-attachments/assets/84d50d92-1c32-4f54-9e16-90c924a38fe3)



**Question 3**

![image](https://github.com/user-attachments/assets/63cb18ac-0b6c-47a2-a8a2-1daaf5739ff3)
~~~
create table Department(
DepartmentID int primary key,
DepartmentName varchar(50) UNIQUE NOT NULL,
Location varchar(100));

~~~
##**Output:**

![image](https://github.com/user-attachments/assets/b8d10189-4c5f-4d15-9fa7-d3076e668745)


**Question 4**

![image](https://github.com/user-attachments/assets/37eb9cc1-ee63-4752-8d59-e5384d1d2c5b)

```
create table jobs(
job_id int,
job_title varchar(50) default "",
min_salary int default 8000,max_salary int);
```

**Output:**

![image](https://github.com/user-attachments/assets/54607c4f-8c8d-4ac5-b35c-f698d25ed6a6)


**Question 5**

![image](https://github.com/user-attachments/assets/7d4fd6ee-28a0-4552-b247-c417a046ee40)

```
alter table Employees add column Date_of_joi Date;
alter table employees rename column job_title to Designation;
```

**Output:**

![image](https://github.com/user-attachments/assets/4a4eb8c3-6f09-430f-a241-4a0e9ef5748f)

**Question 6**

![image](https://github.com/user-attachments/assets/13cf65dd-7137-4eb1-bf20-7c7f9c1a6027)

```
insert into Products(ProductID,ProductName,Price,Stock)
select ProductID,ProductName,Price,Stock from Discontinued_products;

```

**Output:**

![image](https://github.com/user-attachments/assets/0f4ac5db-f7b2-46c4-bff7-4b5634fb54c6)


**Question 7**

![image](https://github.com/user-attachments/assets/25d9b1fb-5d5e-4e96-9fb3-41c03f345cc6)


```
alter table Companies add column designation varchar(50);
alter table Companies add column net_salary number;
```

**Output:**

![image](https://github.com/user-attachments/assets/0a2a7e66-088e-458a-b391-27f549a69852)


**Question 8**

![image](https://github.com/user-attachments/assets/e5048823-673d-4768-87ba-c33f0424c07b)


```
create table item(item_id varchar(50) primary key,item_desc varchar(50) not null,
rate int not null,icom_id char(4),
foreign key(icom_id) references company(com_id) on update cascade on delete cascade);
```

**Output:**

![image](https://github.com/user-attachments/assets/2cf69ccf-569f-481b-b92e-b48d83886381)


**Question 9**

![image](https://github.com/user-attachments/assets/2c69a3d3-0804-4d80-9246-2a12f7b8a25a)


```
insert into Student_details(RollNo,Name,Gender) values(204,"Samuel Black","M");
```

**Output:**

![image](https://github.com/user-attachments/assets/4c0e160d-3f9f-4fd0-b763-f9478b41e068)


**Question 10**

![image](https://github.com/user-attachments/assets/44640c44-1b3c-4bd2-bb2b-db50c0bbd98b)

```
create table Customers(CustomerID INTEGER,Name TEXT,Email TEXT,JoinDate DATETIME);
```

**Output:**

![image](https://github.com/user-attachments/assets/f4216879-d170-4c3a-ac7b-00a738d69e5d)

## GRADES:

![image](https://github.com/user-attachments/assets/05c76d13-8b21-42f4-bdd7-39fc4923e9bf)


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
