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
--

<img width="944" height="447" alt="Screenshot 2025-10-01 160013" src="https://github.com/user-attachments/assets/bd221aee-0371-49c0-b235-d72629935e75" />

```sql
SELECT department_id AS depar,department_name
FROM Departments
WHERE LENGTH(department_name)>(
SELECT AVG(LENGTH(department_name))
FROM Departments
);
```

**Output:**

<img width="640" height="468" alt="Screenshot 2025-10-01 160213" src="https://github.com/user-attachments/assets/b13ac773-7423-4485-9d40-798e43eca4c8" />

**Question 2**
---

<img width="995" height="752" alt="Screenshot 2025-10-01 160432" src="https://github.com/user-attachments/assets/5c5d5127-888a-4ebe-9f27-dc92e623e4e6" />

```sql
SELECT * FROM CUSTOMERS
WHERE SALARY >1500;
```

**Output:**

<img width="1210" height="673" alt="Screenshot 2025-10-01 160600" src="https://github.com/user-attachments/assets/3673940e-f1d9-48a4-88ae-aea1002a5ffb" />

**Question 3**
---

<img width="1051" height="682" alt="Screenshot 2025-10-01 160632" src="https://github.com/user-attachments/assets/510e23d8-5899-4abd-80b4-dfefbb7c62a6" />

```sql
select commission from salesman
where salesman_id in (select (salesman_id)
from customer
where city='Paris'
);
```

**Output:**

<img width="449" height="402" alt="Screenshot 2025-10-01 160713" src="https://github.com/user-attachments/assets/0b0006d1-dd44-40d2-85cc-d4320b231e45" />

**Question 4**
---

<img width="941" height="756" alt="Screenshot 2025-10-01 160746" src="https://github.com/user-attachments/assets/0bf02fc5-d8c1-46bc-93e7-4cf77c224afb" />

```sql
SELECT * FROM CUSTOMERS
WHERE AGE < 30;
```

**Output:**

<img width="1210" height="647" alt="Screenshot 2025-10-01 160907" src="https://github.com/user-attachments/assets/5b9b5b8d-01d0-409b-9709-85475f365ef2" />

**Question 5**
---

<img width="938" height="505" alt="Screenshot 2025-10-01 160932" src="https://github.com/user-attachments/assets/5de51df9-e737-4705-91be-6fcfc8fd6639" />

```sql
SELECT medication_id as medic,medication_name,dosage
FROM Medications
WHERE dosage = (SELECT MAX(dosage) FROM Medications);
```

**Output:**

<img width="876" height="461" alt="Screenshot 2025-10-01 161019" src="https://github.com/user-attachments/assets/04d2d663-1ed4-460f-a3da-675d24bbe0b5" />

**Question 6**
---

<img width="1052" height="561" alt="Screenshot 2025-10-01 161050" src="https://github.com/user-attachments/assets/622b4165-f9b4-4771-8bab-fe3e64e2a3cd" />

```sql
SELECT name
FROM customer
WHERE phone IN (
SELECT phone
FROM customer
GROUP BY phone
HAVING COUNT(*) = 1
);
```

**Output:**

<img width="507" height="519" alt="Screenshot 2025-10-01 161130" src="https://github.com/user-attachments/assets/ff050313-2732-49f3-930e-a87b2417807a" />

**Question 7**
---

<img width="1249" height="623" alt="Screenshot 2025-10-01 161203" src="https://github.com/user-attachments/assets/f912fccb-9f9a-45b3-a730-1c29e978a889" />

```sql
SELECT * FROM GRADES g
WHERE grade = (SELECT MIN(grade) FROM GRADES
WHERE subject  =g.subject);
```

**Output:**

<img width="1215" height="446" alt="Screenshot 2025-10-01 161256" src="https://github.com/user-attachments/assets/8484b401-ae01-4712-b8ba-4e73d8ac7654" />

**Question 8**
---

<img width="972" height="485" alt="Screenshot 2025-10-01 161320" src="https://github.com/user-attachments/assets/09a3b57f-56c8-4ef8-98e4-8c87d2347712" />

```sql
SELECT name,city
FROM customer
WHERE city IN (
SELECT city
FROM customer
WHERE id IN (3,7)
);

```

**Output:**

<img width="551" height="473" alt="Screenshot 2025-10-01 161408" src="https://github.com/user-attachments/assets/0e86b11e-0f79-4d5c-b4d2-95dc3eb044b3" />

**Question 9**
---

<img width="1258" height="516" alt="Screenshot 2025-10-01 161436" src="https://github.com/user-attachments/assets/34bcd979-5711-44c3-83fd-aeeab65abae2" />

```sql
SELECT ord_no, purch_amt, ord_date, customer_id, salesman_id
FROM Orders
WHERE salesman_id IN (
    SELECT salesman_id
    FROM Orders
    WHERE customer_id = 3007
);
```

**Output:**

<img width="1129" height="449" alt="Screenshot 2025-10-01 161520" src="https://github.com/user-attachments/assets/56707e4c-28c8-47e3-98d9-1eb712fd2884" />

**Question 10**
---

<img width="1250" height="563" alt="Screenshot 2025-10-01 161547" src="https://github.com/user-attachments/assets/07437153-cc32-4086-8144-35a0897b21f7" />

```sql
SELECT * FROM ORDERS
WHERE purch_amt>(
SELECT AVG(purch_amt)
FROM ORDERS
WHERE ord_date='2012-10-10'
);
```

**Output:**

<img width="1124" height="464" alt="Screenshot 2025-10-01 161622" src="https://github.com/user-attachments/assets/bd91e8a9-a3a2-4942-9d6c-e0327c937dd0" />

## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
---

<img width="1137" height="65" alt="Screenshot 2025-10-01 161714" src="https://github.com/user-attachments/assets/f3dc0e47-827b-4923-829e-095f267c9d08" />
