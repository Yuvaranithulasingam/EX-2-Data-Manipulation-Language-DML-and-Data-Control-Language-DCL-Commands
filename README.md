# EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands

## Date:

## AIM:
To create a manager database and execute DML queries using SQL.

## DML(Data Manipulation Language)
The SQL commands that deal with the manipulation of data present in the database belong to DML or Data Manipulation Language and this includes most of the SQL statements. It is the component of the SQL statement that controls access to data and to the database. Basically, DCL statements are grouped with DML statements.

## List of DML commands:
INSERT: It is used to insert data into a table.
UPDATE: It is used to update existing data within a table.
DELETE: It is used to delete records from a database table.

## Create the table as given below:
```
create table manager(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),Hiredate date,designation char(10),deptno number(2),reporting char(10));
insert the following values into the table
insert into manager values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into manager values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into manager values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);
insert into manager values(7788,'Vikash',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
```
#### OUTPUT:
![original](https://github.com/Yuvaranithulasingam/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121418522/6427dafe-71dd-4a11-8d39-b23ff6ef5ead)

### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.

#### QUERY: 
```
update managers set salary=salary+(salary*10/100);
```
#### OUTPUT:
![salary](https://github.com/Yuvaranithulasingam/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121418522/3bc9e016-776d-46e2-aec6-281f705eefe2)

### Q2) Delete the records from manager table where the salary less than 2750.

#### QUERY:
```
delete managers where salary<2750;
```
#### OUTPUT:
![image](https://github.com/Yuvaranithulasingam/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121418522/81f40d34-4f96-4869-82ed-49c00c6f13d7)

### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)

#### QUERY:
```
SELECT
ename AS "Name",
salary*12 AS "Annual Salary"
FROM
managers;
```
#### OUTPUT:
![annual](https://github.com/Yuvaranithulasingam/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121418522/ab1a5036-e509-4171-bd12-76369acd5d52)

### Q5) List the names of Clerks from emp table.

#### QUERY:
```
select ename from managers where designation='clerk';
```
#### OUTPUT:
![clerk](https://github.com/Yuvaranithulasingam/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121418522/d78ee914-f73d-4e77-8ed4-147ff16a7e4f)

### Q6) List the names of employee who are not Managers.

#### QUERY:
```
select ename from managers where designation!='manager';
```
#### OUTPUT:
![manager](https://github.com/Yuvaranithulasingam/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121418522/99ac32a3-d2f4-44b6-a8b8-d4c9ac4aff9e)

### Q7) List the names of employees not eligible for commission.

#### QUERY:
```
select ename from managers where commission=0;
```
#### OUTPUT:
![commission](https://github.com/Yuvaranithulasingam/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121418522/b46b58f1-4483-4cc8-bee4-9d4ab37a1987)

### Q8) List employees whose name either start or end with ‘s’.

#### QUERY:
```
select ename from managers where ename LIKE 'S%' OR ename LIKE '%S';
```
#### OUTPUT:
![s name](https://github.com/Yuvaranithulasingam/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121418522/ef741729-484d-452a-b927-835684ec0209)

### Q9) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.

#### QUERY:
```
select ename,designation,deptno,hiredate from managers order by hiredate ASC;
```
#### OUTPUT:
![ascending](https://github.com/Yuvaranithulasingam/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121418522/014d3812-d8d8-4ea1-9299-2ba286bbc391)

### Q10) List the Details of Employees who have joined before 30 Sept 81.

#### QUERY:
```
select * from managers where hiredate < '30 SEP 81';
```
#### OUTPUT:
![hire](https://github.com/Yuvaranithulasingam/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121418522/fdd4b2fa-d1ef-400e-8866-24a7e6a38765)

### Q11) List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.

#### QUERY:
```
select ename,deptno,salary from managers ORDER BY deptno ASC,salary desc;
```
#### OUTPUT:
![ascend and desend](https://github.com/Yuvaranithulasingam/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121418522/1845f1dd-7780-47f2-a660-1ecd0611b1db)

### Q12) List the names of employees not belonging to dept no 30,40 & 10

#### QUERY:
```
select ename from managers where deptno NOT IN (30,40,10);
```
#### OUTPUT:
![not in](https://github.com/Yuvaranithulasingam/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121418522/d6d3bd0d-214a-4193-97d4-46a7277f6622)

### Q13) Find number of rows in the table EMP

#### QUERY:
```
select count(*) as rownumber from managers;
```
#### OUTPUT:
![row](https://github.com/Yuvaranithulasingam/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121418522/cd5b4aed-55c2-4fac-9503-fe42f8dac85a)

### Q14) Find maximum, minimum and average salary in EMP table.

#### QUERY:
```
select MAX(salary) as maximumsal,MIN(salary) as minimumsal,AVG(salary)
as averagesal from managers;
```
#### OUTPUT:
![maxmin](https://github.com/Yuvaranithulasingam/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121418522/7b4f70a5-a783-4886-9dec-06fbbdf98629)

### Q15) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

#### QUERY:
```
select designation,count(*) as number_employee from managers GROUP BY designation ORDER BY number_employee DESC;
```
#### OUTPUT:
![Screenshot 2023-09-28 194303](https://github.com/Yuvaranithulasingam/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121418522/3737eb50-a938-4086-bb9c-fa180630920c)

## RESULT:
    Executing DML queries using SQL was executed successfully.
