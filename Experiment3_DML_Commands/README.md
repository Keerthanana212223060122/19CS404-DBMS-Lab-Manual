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
--
-- <img width="1056" height="539" alt="Screenshot 2025-10-01 150742" src="https://github.com/user-attachments/assets/1cd1acfd-e7b6-4586-aed2-c786f4e05d59" />

```sql
UPDATE products
SET
sell_price=CAST(cost_price*1.35 AS INTEGER)
WHERE
(sell_price-cost_price)/sell_price<0.30;
```

**Output:**

<img width="1693" height="387" alt="Screenshot 2025-10-01 151316" src="https://github.com/user-attachments/assets/2a2ec537-c67f-492b-bcb7-a73bcb7fbc66" />

**Question 2**
---
<img width="680" height="215" alt="Screenshot 2025-10-01 151349" src="https://github.com/user-attachments/assets/d36192a8-6eba-432a-9897-a2396a957ff8" />

```sql
UPDATE suppliers
SET supplier_name ='A1 Suppliers'
WHERE supplier_id=8;
```

**Output:**

<img width="1553" height="313" alt="Screenshot 2025-10-01 151433" src="https://github.com/user-attachments/assets/ba23ba5b-ed7d-4db3-b573-4fef0e411e7e" />

**Question 3**
---
<img width="1139" height="416" alt="Screenshot 2025-10-01 151507" src="https://github.com/user-attachments/assets/76db53eb-93a8-47b2-b28c-620805c3cefa" />


```sql
UPDATE Products
SET reorder_lvl =20
WHERE quantity<10
AND category='Snacks';
```

**Output:**

<img width="1638" height="425" alt="Screenshot 2025-10-01 151558" src="https://github.com/user-attachments/assets/d6d04b87-1093-4eaa-b909-5ae92bf5e6ca" />

**Question 4**
---

<img width="649" height="372" alt="Screenshot 2025-10-01 151634" src="https://github.com/user-attachments/assets/256e073c-405d-4178-9998-35bacb26fbff" />

```sql
UPDATE Products
SET reorder_lvl =40
WHERE category ='Grocery';
```

**Output:**

<img width="1768" height="312" alt="Screenshot 2025-10-01 151742" src="https://github.com/user-attachments/assets/e1e8dd23-af2d-4d02-a4ad-32f1316f9dc6" />

**Question 5**
---

<img width="734" height="378" alt="Screenshot 2025-10-01 151813" src="https://github.com/user-attachments/assets/6258202d-a53b-49bb-b2f1-14a6182ec990" />

```sql
UPDATE Products
SET category ='Household'
WHERE product_name LIKE '%Detergent%';
```

**Output:**

<img width="1768" height="383" alt="Screenshot 2025-10-01 151905" src="https://github.com/user-attachments/assets/b35de5a6-8694-4f45-8a02-6825c1b3497e" />

**Question 6**
---

<img width="652" height="387" alt="Screenshot 2025-10-01 151944" src="https://github.com/user-attachments/assets/341a3b60-ae95-40ea-a442-12d4cfbb5425" />

```sql
DELETE FROM Doctors
WHERE last_name is NULL;
```

**Output:**

<img width="882" height="534" alt="Screenshot 2025-10-01 152019" src="https://github.com/user-attachments/assets/bfcff163-1703-4b52-82c3-4213d380fb03" />

**Question 7**
---

<img width="1118" height="383" alt="Screenshot 2025-10-01 152044" src="https://github.com/user-attachments/assets/82242d7d-3dc6-4fd0-9d46-b0a4af76989f" />

```sql
DELETE FROM customer
WHERE CUST_NAME LIKE '%Holmes%';
```

**Output:**

<img width="1814" height="345" alt="Screenshot 2025-10-01 152138" src="https://github.com/user-attachments/assets/51418d2b-4698-49f5-8280-243be703a2d9" />

**Question 8**
---

<img width="617" height="426" alt="Screenshot 2025-10-01 152214" src="https://github.com/user-attachments/assets/e9f53cf0-728e-4aa8-8e57-3da80e386dc0" />

```sql
DELETE FROM Surgeries
WHERE surgery_id=3;
```

**Output:**

<img width="1079" height="365" alt="Screenshot 2025-10-01 152252" src="https://github.com/user-attachments/assets/b1d866cd-1cfa-4a86-81ad-e7e75178131d" />

**Question 9**
---

<img width="1291" height="403" alt="Screenshot 2025-10-01 152317" src="https://github.com/user-attachments/assets/09f4ef74-be5b-46df-99a5-93988e2796a7" />

```sql
DELETE FROM Customer
WHERE GRADE % 2 <> 0;
```

**Output:**

<img width="1861" height="291" alt="Screenshot 2025-10-01 152418" src="https://github.com/user-attachments/assets/889906ec-4a0e-47a6-822f-655a4fa7d897" />

**Question 10**
---

<img width="910" height="274" alt="Screenshot 2025-10-01 152448" src="https://github.com/user-attachments/assets/4f2e4f34-b1bf-46c7-a514-1344e68df9ab" />

```sql
DELETE FROM Customer
WHERE
CUST_COUNTRY ='UK'
AND WORKING_AREA ='London'
AND GRADE <3;
```

**Output:**

<img width="1819" height="309" alt="Screenshot 2025-10-01 152532" src="https://github.com/user-attachments/assets/e1a5ea89-d2d1-41a3-8e26-4d72e152024d" />

## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.

---
<img width="1088" height="71" alt="Screenshot 2025-10-01 152946" src="https://github.com/user-attachments/assets/5628eb98-af51-47fe-aa42-7c58318fb7f3" />
