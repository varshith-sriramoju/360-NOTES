# Duplicate And Temporary Tables

working with duplicate tables or copy the data from one table to

another table:

in MySQL, when we want to create the duplicate table or copy the data

from one table to another table, we will have the following ways:

1. using like operator

when we create the duplicate table using like command , only the table

structure copied , but not data

when we want to create the duplicate table in MySQL, we will use the

following syntax:

```sql
create table table_name like original table_name;
```

in order to copy the data into duplicate table, while we create the duplicate table using "like" operator, we will use the following syntax
in MySQL:

```sql
insert into duplicate_table_name like select * from original_table_name;
```

## example

```sql
create table emp_fp2_3 like employee;
desc emp_fp2_3;
insert into emp_fp2_3 select * from employee;
select * from emp_fp2_3;
```

## 2. using select command

when we create the duplicate table using "Select" command , it will

copy the both "table structure and table data" into duplicate table

when we want to create the duplicate table, using select command we

will use the following syntax:

```sql
create table table_name select * from original_table_name
```

example:

```sql
create table emp_fp2_3_2
select * from employee;
desc emp_fp2_3_2;
select * from emp_fp2_3_2;
```

when we want to copy the data from one table to another table, in
MySQL we will use "select" command , when we are using the "Select"
command to copy the data, in the select command , we will give always
columns order as per the "duplicate table column order"

syntax:

```sql
insert into duplicate_table_name select col1, col2,col3, col4,.....coln
from original_table_name;
```

if the columns in the "original table" and "duplicate table" are same

in both types of the columns ,column order, column count, then we will use

the following syntax:

```sql
insert into duplciate_table_name select * from original_table_name;
```

## example

```sql
create table
dummy(firstname varchar(100) not null,
lastname varchar(100) not null,
id int primary key);
desc dummy;
insert into dummy select firstname,
lastname,id from employee;
select * from dummy;
```

## temporary tables or session tables in the MySQL

temporary table or session tables are exist in the MySQL, until we close

the MySQL workbench or MySQL command line

these table are "Memory efficient" table, these tables are automatically

deleted, when we close the MySQL workbench or command line

these tables will not be visible, when you run the following syntax:

```sql
show tables;
```

temporary tables or session tables are created in MySQL, using following

syntax:

```sql
create temporary table table_name(col1 type constraint,..........):
```

## example

```sql
create temporary table dummy3(firstname varchar(100));
desc dummy3;
insert into dummy3 values ('a');
select * from dummy3;
```

