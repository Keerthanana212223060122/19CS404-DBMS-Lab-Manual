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
--

<img width="1203" height="776" alt="Screenshot 2025-10-01 162021" src="https://github.com/user-attachments/assets/94132028-2f82-425d-90da-3d4a99f4fa99" />

```sql
SELECT c.cust_name, c.city, c.grade, s.name AS Salesman, s.city
FROM customer c
INNER JOIN salesman s
ON c.salesman_id = s.salesman_id
ORDER BY c.customer_id;
```

**Output:**

<img width="1307" height="786" alt="Screenshot 2025-10-01 162126" src="https://github.com/user-attachments/assets/41e10bb7-988f-404c-95de-6106f34d5aa7" />

**Question 2**
---

<img width="1282" height="656" alt="Screenshot 2025-10-01 162156" src="https://github.com/user-attachments/assets/2e1ec373-4d8d-4e0e-9240-8ee99e46748f" />

```sql
select p.*,
       d.specialization as "doctor_specialization"
from PATIENTS p
inner join DOCTORS d
on p.doctor_id=d.doctor_id;
```

**Output:**

<img width="1737" height="423" alt="Screenshot 2025-10-01 162326" src="https://github.com/user-attachments/assets/9e909bd2-493c-40e5-b42f-d070b0b00e71" />

**Question 3**
---

<img width="1774" height="284" alt="Screenshot 2025-10-01 162401" src="https://github.com/user-attachments/assets/7ba1aa16-ac0e-41ae-a5d6-a4444be03577" />

```sql
SELECT s.name
FROM salesman s
LEFT JOIN customer c ON s.salesman_id=c.salesman_id
WHERE c.city='New York';
```

**Output:**

<img width="393" height="432" alt="Screenshot 2025-10-01 162445" src="https://github.com/user-attachments/assets/41a688f8-37cb-4400-a074-76c07dc8d64c" />

**Question 4**
---

<img width="1764" height="428" alt="Screenshot 2025-10-01 162522" src="https://github.com/user-attachments/assets/4828156a-a9d5-404c-b408-c66ce79e4834" />

```sql
SELECT p.first_name AS patient_name, d.first_name AS doctor_name
FROM PATIENTS p
INNER JOIN DOCTORS d
ON p.doctor_id = d.doctor_id
WHERE p.date_of_birth > '1990-01-01';
```

**Output:**

<img width="471" height="298" alt="Screenshot 2025-10-01 162610" src="https://github.com/user-attachments/assets/0bde285e-b43c-4ed0-96f8-c7755855ee5b" />

**Question 5**
---

<img width="933" height="815" alt="Screenshot 2025-10-01 162655" src="https://github.com/user-attachments/assets/21d071d3-7feb-48ca-b6f3-8b647c43e5e5" />

```sql
SELECT 
    s.name AS Salesman, 
    c.cust_name AS cust_name, 
    s.city 
FROM 
    salesman s 
JOIN 
    customer c ON s.city = c.city;
```

**Output:**

<img width="944" height="692" alt="Screenshot 2025-10-01 162734" src="https://github.com/user-attachments/assets/64bd1e40-d617-456e-b662-026b7cddd835" />

**Question 6**
---

<img width="1346" height="852" alt="Screenshot 2025-10-01 162831" src="https://github.com/user-attachments/assets/f8593a0c-940a-4485-b8db-ca67f4b5284f" />

```sql
SELECT c.cust_name,c.city,o.ord_no,o.ord_date,o.purch_amt AS "Order Amount",s.name,s.commission
FROM customer c
LEFT JOIN orders o
ON c.customer_id=o.customer_id
LEFT JOIN salesman s
ON c.salesman_id=s.salesman_id;
```

**Output:**

<img width="1436" height="824" alt="Screenshot 2025-10-01 162917" src="https://github.com/user-attachments/assets/4fd54e78-db1a-4d49-b2d3-b62f89cc0015" />

**Question 7**
---

<img width="989" height="399" alt="Screenshot 2025-10-01 162945" src="https://github.com/user-attachments/assets/b19d908f-bcf5-4a87-962e-64a181cf15f2" />

```sql
select c.cust_name
from CUSTOMER c
left join ORDERS o
on c.customer_id=o.customer_id;
```

**Output:**

<img width="288" height="828" alt="Screenshot 2025-10-01 163119" src="https://github.com/user-attachments/assets/c3d169a2-d5c8-43fa-860e-829ec1663d73" />

**Question 8**
---

<img width="1166" height="824" alt="Screenshot 2025-10-01 163155" src="https://github.com/user-attachments/assets/dcf09706-5c9e-48a7-a989-6a4731800924" />

```sql
SELECT o.ord_no, o.purch_amt, c.cust_name, c.city
FROM orders o
INNER JOIN customer c
ON o.customer_id = c.customer_id
WHERE o.purch_amt BETWEEN 500 AND 2000;
```

**Output:**

<img width="1143" height="460" alt="Screenshot 2025-10-01 163235" src="https://github.com/user-attachments/assets/b2e63630-e3a4-456d-aa3d-9268706ea007" />

**Question 9**
---

<img width="1785" height="683" alt="Screenshot 2025-10-01 163324" src="https://github.com/user-attachments/assets/52f2a3cc-b90b-4317-922e-aeb7be63fc4a" />

```sql
SELECT c.cust_name AS "Customer Name", c.city, s.name AS Salesman, s.city AS city, s.commission
FROM customer c
INNER JOIN salesman s
ON c.salesman_id = s.salesman_id
WHERE c.city <> s.city
AND s.commission > 0.12;
```

**Output:**

<img width="1206" height="531" alt="Screenshot 2025-10-01 163405" src="https://github.com/user-attachments/assets/75f0998a-b535-4963-8d91-f2a51c1eba8c" />

**Question 10**
---

<img width="1728" height="478" alt="Screenshot 2025-10-01 163433" src="https://github.com/user-attachments/assets/19ee899e-adc3-4593-82a6-60e83dcf26e0" />

```sql
select p.first_name as "patient_name "
from PATIENTS p
inner join DOCTORS d
on p.doctor_id=d.doctor_id
where d.first_name="Emily" and d.last_name="Johnson";
```

**Output:**

<img width="314" height="339" alt="Screenshot 2025-10-01 163516" src="https://github.com/user-attachments/assets/42380e1c-2193-4b22-8bef-2c3269c44c06" />

## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
---
