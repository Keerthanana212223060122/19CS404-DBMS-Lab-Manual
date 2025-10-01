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
--

<img width="1318" height="308" alt="Screenshot 2025-09-29 142137" src="https://github.com/user-attachments/assets/98684450-1a31-485f-8bc0-477046880bea" />

```sql
create table Invoices(
InvoiceID INTEGER primary key,
InvoiceDate Date,
Amount REAL check (Amount>=0),
DueDate DATE check (DueDate>=InvoiceDate),
OrderID INTEGER,
FOREIGN KEY (OrderID)references Orders(OrderID)
);
```

**Output:**

<img width="1762" height="248" alt="Screenshot 2025-09-29 142030" src="https://github.com/user-attachments/assets/ecddd02c-0c2d-48bf-80a2-003515df6b64" />

**Question 2**
---

<img width="951" height="222" alt="Screenshot 2025-09-29 140920" src="https://github.com/user-attachments/assets/7e6f08a5-7f8a-43bb-90de-cc85eac48719" />

```sql
ALTER TABLE employee
ADD COLUMN first_name varchar(50);
ALTER TABLE employee
ADD COLUMN last_name varchar(50);
```

**Output:**

<img width="1519" height="298" alt="Screenshot 2025-09-29 141000" src="https://github.com/user-attachments/assets/e45adfa6-7204-4867-a8de-49fc25e73385" />

**Question 3**
---

<img width="685" height="282" alt="Screenshot 2025-09-29 141027" src="https://github.com/user-attachments/assets/5f15e2e4-690b-4e65-b6e3-42a600d007ed" />


```sql
INSERT INTO Employee(EmployeeID,Name,Department,Salary)
SELECT EmployeeID,Name,Department,Salary
FROM Former_employees;
```

**Output:**

<img width="1247" height="265" alt="Screenshot 2025-09-29 141056" src="https://github.com/user-attachments/assets/fd5cc51c-cb6e-4020-93ee-f4a1305f88f3" />

**Question 4**
---

<img width="942" height="202" alt="Screenshot 2025-09-29 141121" src="https://github.com/user-attachments/assets/d062ccaa-3e2c-461c-91b5-12182cd99409" />

```sql
INSERT INTO Student_details(Rollno,Name,Gender,Subject,MARKS)
VALUES(201,'David Lee','M','Physics',92);
```

**Output:**

<img width="1338" height="225" alt="Screenshot 2025-09-29 141201" src="https://github.com/user-attachments/assets/bf6d668f-4f89-4bee-9a2c-5b27bcdc8971" />

**Question 5**
---

<img width="1372" height="344" alt="Screenshot 2025-09-29 141228" src="https://github.com/user-attachments/assets/d85da441-571a-444f-b2e9-a5f6250da274" />

```sql
insert into books(ISBN,Title,Author,Publisher,Year)
values("978-1234567890","Introduction to AI","John Doe",NULL,NULL),("978-9876543210","Deep Learning","Jane Doe","TechPress",2022),("978-1122334455","Cybersecurity Essentials","Alice Smith",NULL,2021);
```

**Output:**

<img width="1539" height="259" alt="Screenshot 2025-09-29 141304" src="https://github.com/user-attachments/assets/3480cb5e-7a29-4093-98c4-6da8ee6134ea" />

**Question 6**
---

<img width="1191" height="306" alt="Screenshot 2025-09-29 141330" src="https://github.com/user-attachments/assets/307f0a5f-539c-4f54-a0be-84e68af8a7b5" />


```sql
CREATE TABLE Products(
ProductID INTEGER primary key,
ProductName TEXT unique not NULL,
Price REAL CHECK(Price>0),
StockQuantity INTEGER CHECK (StockQuantity>0)
);
```

**Output:**

<img width="1766" height="262" alt="Screenshot 2025-09-29 141407" src="https://github.com/user-attachments/assets/1859bb45-ba70-41f1-821d-3b23b4970438" />

**Question 7**
---

<img width="1250" height="277" alt="Screenshot 2025-09-29 141431" src="https://github.com/user-attachments/assets/67063d71-2c6d-4a3c-a780-4d02a2760d6e" />

```sql
create table ProjectAssignments(
AssignmentID INTEGER primary key,
EmployeeID INTEGER,
ProjectID INTEGER,
AssignmentDate DATE NOT NULL,
foreign key(EmployeeID)references Employees(EmployeeID),
foreign key(ProjectID)references Projects(ProjectID)
);
```

**Output:**

<img width="1652" height="248" alt="Screenshot 2025-09-29 141511" src="https://github.com/user-attachments/assets/64e9d17a-a471-4d70-bf53-2aba124bf29f" />

**Question 8**
---

<img width="922" height="458" alt="Screenshot 2025-09-29 141627" src="https://github.com/user-attachments/assets/543fa0d1-246b-428f-a83c-c7e8e03bc667" />

```sql
ALTER TABLE Student_details
ADD COLUMN State TEXT;
```

**Output:**

<img width="1371" height="312" alt="Screenshot 2025-09-29 141703" src="https://github.com/user-attachments/assets/12ee6046-e329-4d31-b87f-39e90ee9c47a" />

**Question 9**
---

<img width="1224" height="281" alt="Screenshot 2025-09-29 141727" src="https://github.com/user-attachments/assets/6f225f56-febd-4f4f-b974-da6dc5eb157e" />

```sql
CREATE TABLE Attendance(
AttendanceID INTEGER primary key,
EmployeeID INTEGER,
AttendanceDate DATE,
Status TEXT check(Status='Present'or Status='Absent' or Status='Leave'),
foreign key(EmployeeID)references Employees(EmployeeID)
);
```

**Output:**

<img width="1647" height="253" alt="Screenshot 2025-09-29 141804" src="https://github.com/user-attachments/assets/7b7326bd-a39f-4ec4-83e5-d8011ca531b7" />

**Question 10**
---

<img width="779" height="338" alt="Screenshot 2025-09-29 141849" src="https://github.com/user-attachments/assets/3655b954-3e6f-4d76-8eb6-51b07f81ae9e" />

```sql
create table Employees(
EmployeeID INTEGER,
FirstName TEXT,
LastName TEXT,
HireDate DATE
);
```

**Output:**

<img width="1237" height="274" alt="Screenshot 2025-09-29 141920" src="https://github.com/user-attachments/assets/11df597a-8281-45c8-b531-bbc3548daba1" />

## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
---

<img width="1086" height="67" alt="Screenshot 2025-09-29 142544" src="https://github.com/user-attachments/assets/e92b5a52-932d-4734-a02c-f71ffb7111c3" />

