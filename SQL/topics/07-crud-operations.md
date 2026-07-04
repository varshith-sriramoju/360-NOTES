# CRUD Operations

## once we create the table, we will do the following operations

## insert the data into table

when we want to insert the data into table, we will use the following

syntax:

```sql
insert into table_name(col1,col2,col3..........coln)

values(val1,val2,val3,val4,.........valn)
```

or

```sql
insert into table_name

values(val1,val2,val3,........valn)
```

## example

```sql
insert into employee(firstname,lastname,email,
mobileno,location,zipcode,deptid,deptname,designation,
gender,dob,jod,salary)
values('ram','a','ram@gmail.com',9874561230,
'hyderabad',500047,101,'development',
'developer','male','1988-5-5','2009-8-8',
10000);
```

when we want to insert "multiple rows into MySQL table", we will use

## following example

code:

```sql
insert into employee(firstname,lastname,email,
mobileno,location,zipcode,deptid,deptname,designation,
gender,dob,jod,salary)
values('raj','p','raj@gmail.com',8874561230,
'chennai',400047,101,'development',
'developer','male','1989-12-5','2009-8-8',
20000),('madan','B','madan@gmail.com',7874561230,
'bangalore',478947,102,'QA',
'test engineer','male','1995-1-5','2019-8-8',
30000),
('suraj','k','suraj@gmail.com',6674561230,
'chennai',400047,101,'development',
'developer','male','1992-12-5','2013-8-8',
40000);
;
```

## retrieve the data from the table

when we want to retrieve the data from "MySQL" table, in MySQL

we will use a command called "select"

syntax:

```sql
select * from table_name; <=== get the all rows from the table
```

or

```sql
select col1, col2,col3,col4,...coln from table_name <=== to get the

specific column details from the MySQL
```

## example

```sql
select * from employee;
select id,firstname,lastname from employee;
```

## update data in the table

when we want to update the data inside the table, in MySQL we will

use a command called "update"

while updating the data using "update" command, we will always

give "Condition" , if we not give any condition while updating with

update command inside the table, then all rows are update, to avoid

this we will always use "update with condition"

syntax :

```sql
update table_name set col1=value, col2=value, col3=value,..........

coln=valn where condition;
```

## example

```sql
select salary from employee;
update employee set salary=salary+10000;
select id,salary from employee;
update employee set salary=salary+10000
where id=1004;
```

## delete the from the table

when we want to delete the data inside the table, in MySQL we will

use a command called "delete"

while deleting the data using "delete" command, we will always

give "Condition" , if we not give any condition while deleting with

delete command inside the table, then all rows are delete and it like

truncate the table, to avoid this we will always use "delete with

condition"

syntax :

```sql
delete from table_name where condition;
```

or

```sql
delete from table_name; <== it will remove all rows from the table

and it is as same as truncate
```

## example

```sql
select * from employee where id=1004;
delete from employee where id=1004;
```

