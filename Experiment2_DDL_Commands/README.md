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
<img width="1089" height="391" alt="image" src="https://github.com/user-attachments/assets/b0291ff2-f49e-4605-8c6c-5af37859618b" />


```
ALTER TABLE Student_details ADD ParentsNumber number;
ALTER TABLE Student_details ADD Adhar_Number number;
```

**Output:**

<img width="943" height="348" alt="image" src="https://github.com/user-attachments/assets/0ebe5f39-e608-4681-827e-1a663c85da16" />
<img width="641" height="270" alt="image" src="https://github.com/user-attachments/assets/36ca6a28-8b5d-4508-a5fc-0c56598bcb70" />



**Question 2**
---
<img width="922" height="341" alt="image" src="https://github.com/user-attachments/assets/39a55fa4-02e3-4bbf-ae06-dd15eb262e5c" />


```
INSERT INTO Books(ISBN,Title,Author,Publisher,YearPublished)
SELECT ISBN,Title,Author,Publisher,YearPublished
FROM Out_of_print_books;
```

**Output:**

<img width="906" height="256" alt="image" src="https://github.com/user-attachments/assets/a4886ecd-0fae-45ae-9476-9da1d0483ca4" />
<img width="714" height="244" alt="image" src="https://github.com/user-attachments/assets/53a8b356-1878-467e-8ae7-66cf299bf720" />



**Question 3**
---
<img width="1253" height="459" alt="image" src="https://github.com/user-attachments/assets/8b132e96-a47d-4e40-831b-88e248603d08" />


```
CREATE TABLE products(
    product_id INTEGER PRIMARY KEY,
    product_name TEXT NOT NULL,
    list_price DECIMAL(10,2) NOT NULL,
    discount DECIMAL(10,2) DEFAULT 0 NOT NULL,
    CHECK (list_price>= discount AND discount >= 0 AND list_price >=0)
    );
```

**Output:**

<img width="952" height="245" alt="image" src="https://github.com/user-attachments/assets/b9c4c138-fc2d-497e-8b4a-64b21f114f88" />
<img width="858" height="238" alt="image" src="https://github.com/user-attachments/assets/e1608cbb-b8ad-45a0-b05c-0e5a60652a5f" />



**Question 4**
---
<img width="1132" height="368" alt="image" src="https://github.com/user-attachments/assets/0416aef7-beca-4cdd-9da2-ea05268fb95a" />
<img width="582" height="187" alt="image" src="https://github.com/user-attachments/assets/f96897bb-75ef-4f8a-b2e3-c3d90d9ae1d3" />



```
CREATE TABLE contacts(
    contact_id INTEGER NOT NULL,
    first_name TEXT NOT NULL,
    last_name TEXT NOT NULL,
    email TEXT,
    phone TEXT NOT NULL CHECK(length(phone)>=10)
    );
```

**Output:**

<img width="1166" height="277" alt="image" src="https://github.com/user-attachments/assets/a402a294-065d-4403-9aa1-7dc508fe846a" />
<img width="1237" height="273" alt="image" src="https://github.com/user-attachments/assets/6ff90e1b-8ede-4c53-a94e-51d1f3f4e34a" />



**Question 5**
---
<img width="883" height="443" alt="image" src="https://github.com/user-attachments/assets/8579f070-fb7d-440f-a2e6-c5ab66b6a136" />


```
INSERT INTO Customers(ID,NAME,AGE,ADDRESS,SALARY)
VALUES(1,'Ramesh',32,'Ahmedabad',2000);
INSERT INTO Customers(ID,NAME,AGE,ADDRESS,SALARY)
VALUES(2,'Khilan',25,'Delhi',1500);
INSERT INTO Customers(ID,NAME,AGE,ADDRESS,SALARY)
VALUES(3,'Kaushik',23,'Kota',2000);

```

**Output:**

<img width="1212" height="245" alt="image" src="https://github.com/user-attachments/assets/3ff2193e-6e55-44f5-b668-5525838a6c93" />


**Question 6**
---
<img width="1232" height="301" alt="image" src="https://github.com/user-attachments/assets/e9636c3a-59b7-4e26-97c3-293c0f720a71" />


```
CREATE TABLE Shipments(
    ShipmentID INTEGER PRIMARY KEY,
    ShipmentDate DATE,
    SupplierID INTEGER,
    OrderID INTEGER,
    FOREIGN KEY (SupplierID) REFERENCES Suppliers(SupplierID),
    FOREIGN KEY (OrderID) REFERENCES Orders(OrderID)
 );
```

**Output:**

<img width="899" height="202" alt="image" src="https://github.com/user-attachments/assets/118abe0a-6598-4354-9ffe-a98b2ed9f047" />
<img width="666" height="206" alt="image" src="https://github.com/user-attachments/assets/b9e1cd58-6aa9-4ed0-a991-3080e2ee2b00" />



**Question 7**
---
<img width="985" height="323" alt="image" src="https://github.com/user-attachments/assets/84f6a490-c854-439e-a2f7-30e068db9893" />
<img width="354" height="160" alt="image" src="https://github.com/user-attachments/assets/89938e08-69e2-4852-8e37-7faa724526b4" />



```
CREATE TABLE ProjectAssignments(
    AssignmentID INTEGER PRIMARY KEY,
    EmployeeID INTEGER,
    ProjectID INTEGER,
    AssignmentDate DATE NOT NULL,
    FOREIGN KEY (EmployeeID) REFERENCES Employees(EmployeeID),
    FOREIGN KEY (ProjectID) REFERENCES Projects(ProjectID)
);
```

**Output:**

<img width="1019" height="245" alt="image" src="https://github.com/user-attachments/assets/be643e12-d759-4dc3-9998-ca491e6b272b" />
<img width="935" height="249" alt="image" src="https://github.com/user-attachments/assets/de555fba-b9d9-4c1a-89cf-47d17f67b9d3" />




**Question 8**
---
<img width="940" height="352" alt="image" src="https://github.com/user-attachments/assets/fc8da2f3-f8a9-4331-b37f-06ec234aaefa" />


```
INSERT INTO Employee(EmployeeID,Name,Position)
VALUES(4,'Emily White','Analyst');
```

**Output:**

<img width="1151" height="290" alt="image" src="https://github.com/user-attachments/assets/b058319c-afa3-4544-9b27-4d54aa54ef29" />


**Question 9**
---
<img width="1123" height="527" alt="image" src="https://github.com/user-attachments/assets/9aefda85-d439-4968-bb98-831f05943bd0" />


```
ALTER TABLE customer
RENAME COLUMN city TO location;
```

**Output:**

<img width="1090" height="282" alt="image" src="https://github.com/user-attachments/assets/a3e3f316-f71a-41c2-98dc-88e3d7c37638" />
<img width="838" height="294" alt="image" src="https://github.com/user-attachments/assets/859cacb6-9ad3-41ec-be75-0588bd163c41" />



**Question 10**
---
<img width="1043" height="371" alt="image" src="https://github.com/user-attachments/assets/db7c5d7b-8990-413a-9a71-66fd5a36f186" />


```
CREATE TABLE Members(
    MemberID INTEGER,
    MemberName TEXT,
    JoinDate DATE
);
```

**Output:**

<img width="1062" height="320" alt="image" src="https://github.com/user-attachments/assets/840a003f-ea9b-4424-adb4-5ea8d31c0464" />
<img width="633" height="324" alt="image" src="https://github.com/user-attachments/assets/b3ba460f-69ca-408c-ab82-02e149f568b1" />




## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
