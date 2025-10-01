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
--

<img width="1121" height="548" alt="Screenshot 2025-10-01 153329" src="https://github.com/user-attachments/assets/b4af6282-89cf-4803-af65-4defd76f9366" />

```sql
SELECT Address,COUNT(PatientID) AS TotalPatients
FROM Patients
GROUP BY Address;
```

**Output:**

<img width="700" height="533" alt="Screenshot 2025-10-01 153435" src="https://github.com/user-attachments/assets/904df183-2977-400e-b541-0d4bfb4977d7" />

**Question 2**
---

<img width="1129" height="539" alt="Screenshot 2025-10-01 153615" src="https://github.com/user-attachments/assets/c80d0618-db40-4485-8332-4102e22e2814" />

```sql
select strftime("%Y-%m",Date) AS Month,COUNT(*) AS TotalRecords
From MedicalRecords
Group by strftime("%Y-%m",Date);
```

**Output:**

<img width="814" height="573" alt="Screenshot 2025-10-01 153650" src="https://github.com/user-attachments/assets/5653af40-ddd6-4a04-bc42-2ae80e6291b8" />

**Question 3**
---

<img width="1109" height="635" alt="Screenshot 2025-10-01 153722" src="https://github.com/user-attachments/assets/894a90f9-f889-43c3-9dfc-1bc229185292" />

```sql
select Frequency,COUNT(*) AS TotalPrescriptions
FROM Prescriptions
GROUP BY Frequency;
```

**Output:**

<img width="845" height="670" alt="Screenshot 2025-10-01 153820" src="https://github.com/user-attachments/assets/37cdc708-047f-4f08-96ba-9cf1435009e8" />

**Question 4**
---

<img width="753" height="576" alt="Screenshot 2025-10-01 153852" src="https://github.com/user-attachments/assets/8aaf7080-029f-46d5-bc32-450a27fd0663" />

```sql
select name AS Employee_Name,MIN(age) AS Age
FROM employee;
```

**Output:**

<img width="682" height="424" alt="Screenshot 2025-10-01 153934" src="https://github.com/user-attachments/assets/cc45f515-acca-43c4-b018-59062a28897d" />

**Question 5**
---

<img width="641" height="558" alt="Screenshot 2025-10-01 154005" src="https://github.com/user-attachments/assets/3e10698b-6e79-44fb-8daa-723ac9cf8123" />

```sql
select min(purch_amt) as MINIMUM
FROM orders
```

**Output:**

<img width="451" height="426" alt="Screenshot 2025-10-01 154050" src="https://github.com/user-attachments/assets/ad718e58-16da-4887-8965-2f9aa844bfb7" />

**Question 6**
---

<img width="758" height="570" alt="Screenshot 2025-10-01 154118" src="https://github.com/user-attachments/assets/85d13092-5c38-4c81-a0de-141bd8b50882" />

```sql
select avg(income)as Average_Salary
from employee
```

**Output:**

<img width="543" height="425" alt="Screenshot 2025-10-01 154209" src="https://github.com/user-attachments/assets/8c597827-23b3-493d-ad3d-43ad933b8e5c" />

**Question 7**
---

<img width="781" height="523" alt="Screenshot 2025-10-01 154233" src="https://github.com/user-attachments/assets/b64e159a-21da-4c04-a8da-98a9c1bad95f" />

```sql
select name,email,min(length(email)) as min_email_length
from customer;
```

**Output:**

<img width="1139" height="416" alt="Screenshot 2025-10-01 154313" src="https://github.com/user-attachments/assets/d070dfb3-f9f2-46af-a4ee-511ea13b1ecc" />

**Question 8**
---

<img width="1323" height="589" alt="Screenshot 2025-10-01 154337" src="https://github.com/user-attachments/assets/1e279b71-5342-4d1d-bf79-387de27aa3f1" />

```sql
select city,AVG(income)
from employee
group by city
having AVG(income)>500000;
```

**Output:**

<img width="709" height="559" alt="image" src="https://github.com/user-attachments/assets/08cca546-b2f1-4119-b864-049afc4bfaa2" />

**Question 9**
---

<img width="1305" height="561" alt="Screenshot 2025-10-01 154432" src="https://github.com/user-attachments/assets/e8f46bc7-020a-474c-a160-78ee59dcb37c" />

```sql
SELECT category_id,count(product_name)
FROM products
WHERE category_id<3
GROUP BY category_id;
```

**Output:**

<img width="851" height="474" alt="Screenshot 2025-10-01 154506" src="https://github.com/user-attachments/assets/ab068345-88de-49c3-a563-e5db4a690658" />

**Question 10**
---

<img width="1343" height="554" alt="Screenshot 2025-10-01 154533" src="https://github.com/user-attachments/assets/913a5e2d-bb40-4ad0-a1cd-9e6df1e33d0e" />

```sql
select age,SUM(income)
from employee
group by age
having SUM(income)>1000000;
```

**Output:**

<img width="650" height="536" alt="Screenshot 2025-10-01 154608" src="https://github.com/user-attachments/assets/35a50491-c4fc-4377-ae84-0473aa05fa17" />

## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.

---

<img width="1051" height="98" alt="Screenshot 2025-10-01 154708" src="https://github.com/user-attachments/assets/6c05dd90-2ac8-48b0-9845-cf7866605002" />

