# Experiment 5: Subqueries and Views

## AIM
To study and implement subqueries and views.

## THEORY

### Subqueries
A subquery is a query inside another SQL query and is embedded in:
- WHERE clause
- HAVING clause
- FROM clause

**Types:**
- **Single-row subquery**:
  Sub queries can also return more than one value. Such results should be made use along with the operators in and any.
- **Multiple-row subquery**:
  Here more than one subquery is used. These multiple sub queries are combined by means of ‘and’ & ‘or’ keywords.
- **Correlated subquery**:
  A subquery is evaluated once for the entire parent statement whereas a correlated Sub query is evaluated once per row processed by the parent statement.

**Example:**
```sql
SELECT * FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```
### Views
A view is a virtual table based on the result of an SQL SELECT query.
**Create View:**
```sql
CREATE VIEW view_name AS
SELECT column1, column2 FROM table_name WHERE condition;
```
**Drop View:**
```sql
DROP VIEW view_name;
```

**Question 1**

![image](https://github.com/user-attachments/assets/a874aae4-5e63-4b75-b5dc-52d27d9c6958)

```sql
SELECT 
    o.ord_no, 
    o.purch_amt, 
    o.ord_date, 
    o.customer_id, 
    o.salesman_id
FROM 
    orders o
JOIN 
    salesman s 
ON 
    o.salesman_id = s.salesman_id
WHERE 
    s.city = 'New York';
```

**Output:**

![image](https://github.com/user-attachments/assets/1b1f3364-1f09-4406-8858-8b3edecd949d)


**Question 2**

![image](https://github.com/user-attachments/assets/37bb5d6a-77a7-4cdd-b725-4bf396da0b4b)

```sql
SELECT *
FROM customer
WHERE customer_id = (
    SELECT salesman_id - 2001
    FROM salesman
    WHERE name = 'Mc Lyon'
); 
```

**Output:**

![image](https://github.com/user-attachments/assets/cf3d29e4-0e72-41dd-84a8-a58968537af5)


**Question 3**

![image](https://github.com/user-attachments/assets/089d44c5-3263-49db-b01b-67c7a130aaac)

```sql
SELECT *
FROM CUSTOMERS
WHERE ADDRESS = 'Delhi';

```

**Output:**

![image](https://github.com/user-attachments/assets/fad77f80-7181-4db4-b4d7-2b632e42f668)


**Question 4**

![image](https://github.com/user-attachments/assets/178844e8-a6ac-46fd-9a4d-4b554ccc5755)


```sql
SELECT *
FROM CUSTOMERS
WHERE SALARY = 1500;
```

**Output:**

![image](https://github.com/user-attachments/assets/414d5250-2ba7-42a6-99cf-02101c0d3859)


**Question 5**

![image](https://github.com/user-attachments/assets/9948a505-65ff-42e4-bdc5-c297fea92a2b)


```sql
SELECT *
FROM Employee
WHERE age < (
    SELECT AVG(age)
    FROM Employee
    WHERE income > 1000000
);

```

**Output:**

![image](https://github.com/user-attachments/assets/aee888e6-8627-4c6a-9414-bbe0803ac8c4)




**Question 6**

![image](https://github.com/user-attachments/assets/9f7b77e4-1081-43eb-8f8d-55b7b3322404)


```sql
SELECT 
    o.ord_no, 
    o.purch_amt, 
    o.ord_date, 
    o.customer_id, 
    o.salesman_id
FROM 
    orders o
JOIN 
    salesman s 
ON 
    o.salesman_id = s.salesman_id
WHERE 
    s.city = 'New York';
```

**Output:**

![image](https://github.com/user-attachments/assets/992ee7df-0561-4f22-90bd-5fabbe60304a)


**Question 7**

![image](https://github.com/user-attachments/assets/ee25011f-6611-4da4-917f-4749a3665556)


```sql
SELECT 
    o.ord_no, 
    o.purch_amt, 
    o.ord_date, 
    o.customer_id, 
    o.salesman_id
FROM 
    orders o
JOIN 
    salesman s 
ON 
    o.salesman_id = s.salesman_id
WHERE 
    s.city = 'London';
```

**Output:**

![image](https://github.com/user-attachments/assets/b9972d4a-4eaf-4846-8c5d-4e0521291396)


**Question 8**

![image](https://github.com/user-attachments/assets/0677a00c-c69f-4ff3-8f4c-38d04798f7b9)


```sql
SELECT 
    department_id,
    department_name
FROM 
    Departments
WHERE 
    LENGTH(department_name) > (
        SELECT AVG(LENGTH(department_name))
        FROM Departments
    );
```

**Output:**

![image](https://github.com/user-attachments/assets/5889d7aa-63bf-484f-9da6-ec16ea4fcac2)


**Question 9**

![image](https://github.com/user-attachments/assets/591a8037-65fb-4479-bf3c-54ce713cc804)


```sql
SELECT *
FROM CUSTOMERS
WHERE SALARY > 1500;
```

**Output:**

![image](https://github.com/user-attachments/assets/e9fe643d-6237-41c4-b80c-b09618ac4fe9)

**Question 10**

![image](https://github.com/user-attachments/assets/771246f2-baa8-4d31-bd63-601257479af1)


```sql
SELECT 
    s.salesman_id, 
    s.name
FROM 
    salesman s
JOIN 
    customer c ON s.salesman_id = c.salesman_id
GROUP BY 
    s.salesman_id, s.name
HAVING 
    COUNT(c.customer_id) > 1;

```

**Output:**

![image](https://github.com/user-attachments/assets/35f9b0fc-aeff-4d79-94fb-4054cbdfde58)



## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
