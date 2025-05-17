# Experiment 3: DML Commands

## AIM
To study and implement DML (Data Manipulation Language) commands.

## THEORY

### 1. INSERT INTO
Used to add records into a relation.
These are three type of INSERT INTO queries which are as
A)Inserting a single record
**Syntax (Single Row):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES (value_1, value_2, ...);
```
**Syntax (Multiple Rows):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES
(value_1, value_2, ...),
(value_3, value_4, ...);
```
**Syntax (Insert from another table):**
```sql
INSERT INTO table_name SELECT * FROM other_table WHERE condition;
```
### 2. UPDATE
Used to modify records in a relation.
Syntax:
```sql
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
```
### 3. DELETE
Used to delete records from a relation.
**Syntax (All rows):**
```sql
DELETE FROM table_name;
```
**Syntax (Specific condition):**
```sql
DELETE FROM table_name WHERE condition;
```
### 4. SELECT
Used to retrieve records from a table.
**Syntax:**
```sql
SELECT column1, column2 FROM table_name WHERE condition;
```
**Question 1**
![image](https://github.com/user-attachments/assets/e66b8a73-8553-41b1-9c55-51fe37bebff7)


```
UPDATE suppliers set supplier_name=UPPER(supplier_name) where contact_person like '%Singh%';
```

**Output:**

![image](https://github.com/user-attachments/assets/d6d34262-f339-4190-b5bc-a76f9531000d)


**Question 2**
![image](https://github.com/user-attachments/assets/fe683199-4502-4f70-bdc2-73ad1bf091ae)


```sql
update suppliers set supplier_name="A1 Suppliers" where supplier_id=8;
```

**Output:**

![image](https://github.com/user-attachments/assets/c79b7ff0-36d4-416e-9fd7-ba27cef3cb52)


**Question 3**
![image](https://github.com/user-attachments/assets/a34d1a4b-dbfe-4981-8985-0f79201dc05f)


```sql
update sales set sell_price=sell_price+0.05*sell_price where sale_date='2023-01-31';
```

**Output:**

![image](https://github.com/user-attachments/assets/7d4c3590-022f-441f-8154-2b16e8337153)


**Question 4**
![image](https://github.com/user-attachments/assets/56068db9-8454-4782-a568-8f39227c65a1)


```sql
delete from Customer  where WORKING_AREA is 'New York';
```

**Output:**

![image](https://github.com/user-attachments/assets/5863d2f2-7b35-4fca-85c3-72c385ea5174)


**Question 5**
![image](https://github.com/user-attachments/assets/19ad7026-dbc4-4cb6-a428-085773a388fe)


```
update PRODUCTS
set reorder_lvl= reorder_lvl*0.7
where product_name like '%cream%' and quantity >reorder_lvl;
```

**Output:**

![image](https://github.com/user-attachments/assets/3ebbb1e1-2033-47d2-b881-b653f56c577d)


**Question 6**
![image](https://github.com/user-attachments/assets/54d816f3-bcaa-41e8-975a-00f7ddcb8c76)

```sql
delete from Doctors
where specialization ='Cardiology';
```

**Output:**

![image](https://github.com/user-attachments/assets/40b1eb06-d6e0-43dd-827d-085818e597bd)

**Question 7**
![image](https://github.com/user-attachments/assets/b2b91a55-3c07-43be-a11a-d84575759679)

```sql
delete from Doctors
where doctor_id  = 1;
```

**Output:**

![image](https://github.com/user-attachments/assets/89c94eae-2741-4fd0-8555-b46bfd5440a7)


**Question 8**
![image](https://github.com/user-attachments/assets/13d56186-ac06-4539-b7e5-293f6861e746)


```sql
delete from Surgeries
where surgery_id = 3;
```

**Output:**

![image](https://github.com/user-attachments/assets/be13907a-6f75-4f3a-a818-e66f3e632dc8)

**Question 9**
![image](https://github.com/user-attachments/assets/127783f9-0b97-4ea2-90d9-180dfbcc5fcb)


```sql
delete from Customer
where (GRADE=2 and CUST_NAME like 'M%')
and PAYMENT_AMT<3000;
```

**Output:**

![image](https://github.com/user-attachments/assets/11f0d744-bd5d-4646-9da3-ea90b03bd9d0)


**Question 10**
![image](https://github.com/user-attachments/assets/1dff0a36-7be1-46ee-9d01-35c92e1e3474)


```sql
delete from Customer
where GRADE >2 
and PAYMENT_AMT <(select avg(PAYMENT_AMT)from Customer)
or OUTSTANDING_AMT>8000;
```

**Output:**

![image](https://github.com/user-attachments/assets/df395136-16ff-4898-aee3-97b20fb4f56c)

## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
