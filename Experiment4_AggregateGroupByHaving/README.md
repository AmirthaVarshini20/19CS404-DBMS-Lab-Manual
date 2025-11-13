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
<img width="1134" height="461" alt="image" src="https://github.com/user-attachments/assets/f95416bd-d7e9-4a93-b72a-4fad80582a96" />


```sql
select Gender,count(*) as TotalPatients
from  Patients
group by Gender;
```

**Output:**


<img width="803" height="352" alt="image" src="https://github.com/user-attachments/assets/c335ba96-f48b-480f-9730-77d258c8ef1e" />


**Question 2**
---

<img width="1163" height="563" alt="image" src="https://github.com/user-attachments/assets/076a69dd-48db-462c-9c98-b26094deb651" />


```sql
select DoctorID , count(*) as  TotalAppointments
from Appointments
group by DoctorID;
```

**Output:**


<img width="843" height="616" alt="image" src="https://github.com/user-attachments/assets/ab8c47c0-c11b-4bdc-b0fd-40861c883c0c" />


**Question 3**
---

<img width="1140" height="503" alt="image" src="https://github.com/user-attachments/assets/8abd95a5-1494-438f-bcf7-9df073e99876" />


```sql
select strftime('%Y-%m',Date) as Month , count(*) as     TotalRecords
from MedicalRecords 
group by Month;

```

**Output:**


<img width="774" height="427" alt="image" src="https://github.com/user-attachments/assets/a32b3e47-cab0-4808-9508-5acc00fe5d71" />


**Question 4**
---

<img width="978" height="509" alt="image" src="https://github.com/user-attachments/assets/9f67db02-7cde-408b-b706-4ff59586439b" />


```sql
select count(distinct salesman_id) as 'COUNT'
from orders;
```

**Output:**


<img width="513" height="317" alt="image" src="https://github.com/user-attachments/assets/97c68f1f-f5c0-4d90-bf12-8ead3310ecc5" />


**Question 5**
---

<img width="1144" height="474" alt="image" src="https://github.com/user-attachments/assets/2a2d4088-80dd-47f8-b1bc-46637bac049e" />


```sql
select count(DISTINCT age) as 'COUNT'
from employee;

```

**Output:**


<img width="474" height="296" alt="image" src="https://github.com/user-attachments/assets/ed83fc49-d9ca-4bac-ac73-1b499a6e013b" />


**Question 6**
---

<img width="851" height="484" alt="image" src="https://github.com/user-attachments/assets/ccba8c22-1854-4b01-a2e1-bdbf65d16fb4" />


```sql
select count(*) as employees_count
from employee
where income>50000;
```

**Output:**


<img width="525" height="304" alt="image" src="https://github.com/user-attachments/assets/5bfe3b37-6f15-4426-ab3e-88eaee1f3ae2" />


**Question 7**
---

<img width="906" height="481" alt="image" src="https://github.com/user-attachments/assets/0d87d561-c4dd-436d-acb2-6010f3db759e" />


```sql
select name ,       email , min(length(email)) as       min_email_length
from customer;
```

**Output:**


<img width="1055" height="301" alt="image" src="https://github.com/user-attachments/assets/1090f6e6-7e5a-486e-a99a-d8cb002d32f4" />


**Question 8**
---

<img width="1229" height="489" alt="image" src="https://github.com/user-attachments/assets/0bf5a9e0-9f87-471a-9f03-c64283302c31" />


```sql
select category_id , avg(price) as  'AVG(Price)'
from products
group by  category_id
having  avg(price) between 10 and 15;
```

**Output:**


<img width="627" height="331" alt="image" src="https://github.com/user-attachments/assets/e0810d56-70bb-4e5d-b71c-627fe548ed84" />


**Question 9**
---

<img width="1221" height="546" alt="image" src="https://github.com/user-attachments/assets/4a0adcae-d937-4e8b-9c35-2cdbbd0e1ce2" />


```sql
select occupation ,min(workhour) as  'MIN(workhour)'
from employee1
group by occupation
having min(workhour) >8;
```

**Output:**


<img width="733" height="460" alt="image" src="https://github.com/user-attachments/assets/657eff59-f9be-48f5-a79f-f10b2219eb54" />


**Question 10**
---

<img width="1220" height="608" alt="image" src="https://github.com/user-attachments/assets/96fd0f1f-75ba-4459-aa78-b40f268abdfc" />


```sql
select city, sum(Income) as 'Income'
from employee
group by city
having sum(Income) >200000;
```

**Output:**


<img width="756" height="525" alt="image" src="https://github.com/user-attachments/assets/2a1e1a9e-973c-4df1-84fa-1f3a0a7d01a8" />



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
