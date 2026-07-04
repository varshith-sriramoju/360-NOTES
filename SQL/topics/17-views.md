## views in MySQL

views are called as "virtual tables"
views are not "physical tables"
views are created for another tables in MySQL
views are act as alias tables for "another table" with specific data
when we are retrieving the data from the table, it will scan entire table
to get the any data, instead of scanning the entire table for given query ,
we can scan the data only a part of data of the table, using "views"

when we want to create the view for any table in the MySQL, we will use
following syntax:

```sql
create view view_name as query;
```

when the table data is updated, view data is also updated
when the table data is deleted, view data is also deleted
when the new data is added into table, the data in view also can able
to get same new data
views are used to "get the data from table" based on the given query
the structure of the table and view , both are look like table, but in the view we can able retrieve data "What we need only using select"

## example

```sql
use employee_fp1_2024;
create view fp23 as select * from employee
where deptname='hr';
select * from fp23;
select firstname,lastname,salary from fp23
where salary>=60000 and salary<=140000;
```

## example

```sql
create or replace view fp23
as select firstname,lastname,salary from employee
where deptname='hr' order by salary desc limit 10;
select * from fp23;
select firstname,lastname,salary from fp23
where salary>=60000 and salary<=140000;
```

## example

```sql
create or replace view fp23 as
select * from employee where deptname='hr';
select * from fp23;
select * from employee where firstname='vikram';
update fp23 set salary=salary+10000;
delete from fp23 where firstname='vikram';
```

## example

```sql
create or replace view fp23 as
select id,firstname,lastname,salary,
joining_date,dob,blood_group,deptname,
deptid,gender,location,email,mobileno,designation
from employee where deptname='hr';
update fp23 set salary=salary-10000;
delete from fp23 where salary>=160000;
select max(salary) from fp23 where
deptname='hr';
update employee set salary=salary+10000
where deptname='hr';
```

## example

```sql
create or replace view fp23 as
select deptname,count(*) from employee
group by deptname;
select * from fp23;
update fp23 set deptname='xyz'
where deptname='abc';
```

when we want to drop the view or delete the view from the database
permanently, we will use the following syntax:

```sql
drop view view_name;
```

## example

```sql
drop view fp23;
select * from fp23;
```

