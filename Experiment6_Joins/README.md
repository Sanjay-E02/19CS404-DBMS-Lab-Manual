# Experiment 6: Joins

## AIM
To study and implement different types of joins.

## THEORY

SQL Joins are used to combine records from two or more tables based on a related column.

### 1. INNER JOIN
Returns records with matching values in both tables.

**Syntax:**
```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

### 2. LEFT JOIN
Returns all records from the left table, and matched records from the right.

**Syntax:**

```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```
### 3. RIGHT JOIN
Returns all records from the right table, and matched records from the left.

**Syntax:**

```sql
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```
### 4. FULL OUTER JOIN
Returns all records when there is a match in either left or right table.

**Syntax:**

```sql
SELECT columns
FROM table1
FULL OUTER JOIN table2
ON table1.column = table2.column;
```

**Question 1**
![image](https://github.com/user-attachments/assets/32d86539-57f2-4aff-85f6-8e5aa4eb1981)


```sql
SELECT patients.first_name, surgeries.*
FROM patients
INNER JOIN surgeries
ON patients.patient_id = surgeries.patient_id
WHERE patients.date_of_birth > '1990-01-01';

```

**Output:**

![image](https://github.com/user-attachments/assets/334ac365-4642-4c17-b4b9-0b10f1321a82)


**Question 2**
![image](https://github.com/user-attachments/assets/ef50324f-9860-49a6-bfa7-f605cf265078)

```sql
SELECT orders.ord_no, 
       orders.purch_amt, 
       orders.ord_date, 
       customer.cust_name, 
       customer.city AS customer_city, 
       customer.grade, 
       salesman.name AS salesman_name, 
       salesman.city AS salesman_city, 
       salesman.commission
FROM orders
INNER JOIN customer ON orders.customer_id = customer.customer_id
INNER JOIN salesman ON orders.salesman_id = salesman.salesman_id;

```

**Output:**

![image](https://github.com/user-attachments/assets/0d771d4b-1fc0-4c86-ad5b-c5f34db089a3)

**Question 3**
![image](https://github.com/user-attachments/assets/46228113-4ab7-4686-a271-df60de297535)

```sql
SELECT customer.cust_name, 
       customer.city AS city, 
       customer.grade, 
       salesman.name AS Salesman, 
       salesman.city AS city
FROM customer
INNER JOIN salesman ON customer.salesman_id = salesman.salesman_id
WHERE customer.grade < 300
ORDER BY customer.customer_id ASC;

```

**Output:**

![image](https://github.com/user-attachments/assets/44e3876a-afeb-4070-96f1-3d07812841ed)


**Question 4**
![image](https://github.com/user-attachments/assets/ee36b59e-f0fd-4a9a-9a7d-19ad3309286b)


```sql
SELECT n.nurse_id, d.department_name
FROM nurses n
INNER JOIN departments d ON n.department_id = d.department_id
WHERE n.first_name = 'David' AND n.last_name = 'Moore';

```

**Output:**

![image](https://github.com/user-attachments/assets/75666ca2-c207-458c-96ec-dbae1a4922f2)


**Question 5**
![image](https://github.com/user-attachments/assets/f947416c-0d12-4950-bf4f-3f9e590ba409)


```sql
SELECT o.ord_no, o.ord_date, o.purch_amt, c.cust_name AS "Customer Name", c.grade, s.name AS Salesman, s.commission
FROM orders o
INNER JOIN customer c ON o.customer_id = c.customer_id
INNER JOIN salesman s ON o.salesman_id = s.salesman_id;

```

**Output:**

![image](https://github.com/user-attachments/assets/ab0ce201-a34b-4cfe-9236-99ef5f77c536)


**Question 6**
![image](https://github.com/user-attachments/assets/dab2d322-9373-45f3-ad48-53cd647c2a0d)

```sql
SELECT c.*
FROM customer c
LEFT JOIN orders o ON c.customer_id = o.customer_id
WHERE o.ord_date > '2012-08-17';


```

**Output:**

![image](https://github.com/user-attachments/assets/b1a183cb-07de-4427-8ae3-26541a9d2a54)


**Question 7**
![image](https://github.com/user-attachments/assets/23158152-c915-4495-a671-a7dae033b425)


```sql
SELECT c.cust_name, s.name
FROM customer c
LEFT JOIN salesman s ON c.salesman_id = s.salesman_id
WHERE c.city = s.city;

```

**Output:**

![image](https://github.com/user-attachments/assets/46b8e6d8-0da3-4962-b2ab-9c4371dc59ea)


**Question 8**
![image](https://github.com/user-attachments/assets/42f6e935-713b-45ae-bbf8-e890dcbbd943)

```sql
SELECT c.cust_name AS "Customer Name", 
       c.city AS "city", 
       s.name AS "Salesman", 
       s.commission AS "commission"
FROM customer c
JOIN salesman s ON c.salesman_id = s.salesman_id;

```

**Output:**

![image](https://github.com/user-attachments/assets/b88e71f6-3813-4f90-b669-d30fe8d48f4e)

**Question 9**
![image](https://github.com/user-attachments/assets/f35a39e8-4772-462b-b43b-ecc2f143ad9e)


```sql
SELECT n.*
FROM nurses n
INNER JOIN departments d ON n.department_id = d.department_id
WHERE d.department_name = 'Pediatrics';

```

**Output:**

![image](https://github.com/user-attachments/assets/cf0baa34-e5b6-4600-9a9f-3794db33de54)


**Question 10**
![image](https://github.com/user-attachments/assets/ff5f2d0d-7516-423c-8074-033e96a7959e)


```sql
SELECT c.cust_name as "Customer Name", c.city AS city, s.name AS Salesman, s.city AS city, s.commission
FROM customer c
INNER JOIN salesman s ON c.salesman_id = s.salesman_id
WHERE c.city != s.city
AND s.commission > 0.12;

```

**Output:**

![image](https://github.com/user-attachments/assets/655cf55a-a330-45a5-8d0e-ae3e07a98d65)



## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
