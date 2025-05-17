# Experiment 4: Aggregate Functions, Group By and Having Clause

## AIM
To study and implement aggregate functions, GROUP BY, and HAVING clause with suitable examples.

## THEORY

### Aggregate Functions
These perform calculations on a set of values and return a single value.

- **MIN()** – Smallest value  
- **MAX()** – Largest value  
- **COUNT()** – Number of rows  
- **SUM()** – Total of values  
- **AVG()** – Average of values

**Syntax:**
```sql
SELECT AGG_FUNC(column_name) FROM table_name WHERE condition;
```
### GROUP BY
Groups records with the same values in specified columns.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name;
```
### HAVING
Filters the grouped records based on aggregate conditions.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;
```

**Question 1**

![image](https://github.com/user-attachments/assets/8a9c6661-e5bd-46b6-b283-e6fd3f317853)

```sql
select 
PatientID,
count(*) as TotalAppointments
from
Appointments
group by
PatientID
order by
PatientID;
```

**Output:**

![image](https://github.com/user-attachments/assets/d972e1a7-41ef-4964-ba2a-faa8eb92b02b)

**Question 2**

![image](https://github.com/user-attachments/assets/034ff13b-61bd-46b2-b6c7-563ef4abee7f)


```sql
select
strftime('%H',AppointmentDateTime) as "HourOfDay",
count(*) as "TotalAppointments"
from
Appointments
group by
strftime('%H',AppointmentDateTime)
order by
HourOfDay;
```

**Output:**

![image](https://github.com/user-attachments/assets/a10934b3-bb65-4256-93ca-076c8d949a4f)

**Question 3**

![image](https://github.com/user-attachments/assets/aa95aa42-4a38-440e-89e9-766814336c17)


```sql
select
strftime('%Y',ValidityPeriod) as "ValidityYear",
count(*) as "TotalPatients"
from
Insurance 
group by
strftime('%Y',ValidityPeriod)
order by
ValidityYear;
```

**Output:**

![image](https://github.com/user-attachments/assets/56f00a4c-18c1-4a7c-aeeb-92589f03dfd7)


**Question 4**

![image](https://github.com/user-attachments/assets/fbd62112-c5f7-4677-8f5b-a8c957416a7e)

```sql
select
count(*) as "COUNT"
from
customer
where
city!= 'Noida';
```

**Output:**

![image](https://github.com/user-attachments/assets/a096f6f9-e6b0-46a1-a14a-f5ba697f2c3e)


**Question 5**

![image](https://github.com/user-attachments/assets/2fa46b4c-5434-480b-bb03-9e661bd1a00d)


```sql
select
name as "fruit_name",
min(inventory) as "lowest_quantity"
from
fruits
group by
name
order by
min(inventory)asc
limit 1;
```

**Output:**

![image](https://github.com/user-attachments/assets/775ef9fd-f6ef-43fb-b768-9c126bf90389)

**Question 6**

![image](https://github.com/user-attachments/assets/747ecbda-528d-4267-bc82-0c9d25c9c9c1)


```sql
select
name,
max(length(name)) as "length"
from
customer
order by
max(length(name))asc
 limit 1;
```

**Output:**

![image](https://github.com/user-attachments/assets/cbfb4d43-933c-4c6b-9185-9e1c34a0a019)


**Question 7**

![image](https://github.com/user-attachments/assets/956d5aef-7742-47c1-b45d-8922ea6aa164)


```sql
select
name,
email,
min(length(email)) as"min_email_length"
from
customer
order by
min(length(email))
limit 1;
```

**Output:**

![image](https://github.com/user-attachments/assets/32202734-9d8c-4eba-b1c5-f5c461ebfbaa)

**Question 8**

![image](https://github.com/user-attachments/assets/87fb53d7-4bad-4a4a-835c-f8736a890ec0)


```sql
select 
(age/5)*5 as "age_group",
min(salary) as"MIN(salary)"
from
customer1
group by
(age/5)*5
having
min(salary)<2000
order by
age_group;
```

**Output:**

![image](https://github.com/user-attachments/assets/111bddf3-d72e-4713-862e-60b855da930a)


**Question 9**

![image](https://github.com/user-attachments/assets/b54be57f-fb64-41f2-bf05-bdb6589157e6)

```sql
select
jdate,
sum(workhour) as "SUM(workhour)"
from
employee1
group by
jdate
having
sum(workhour)>40
order by
jdate;
```

**Output:**

![image](https://github.com/user-attachments/assets/bd40229e-f5c4-4418-b648-d708f3276e2c)


**Question 10**

![image](https://github.com/user-attachments/assets/3dd66104-20d3-4e0b-a3b8-583f57262164)

```sql
select
address,
sum(salary) as "SUM(salary)"
from
customer1
group by
address
having
sum(salary)>2000
order by
address;
```

**Output:**

![image](https://github.com/user-attachments/assets/338f6bbe-8352-4127-afc2-5efb2d070a4c)



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
