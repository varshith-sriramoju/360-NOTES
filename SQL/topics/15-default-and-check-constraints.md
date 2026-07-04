# Default And Check Constraints

## working with default and check constraints

by default , MySQL table fill column with "null" value, if we are not given
any value for the column while insertion

instead null value, we can give user-defined default value to the column,
in MySQL we will use a constraint called "default"

when we are inserting the any value into the column , if the column value
need to validate, where the value is correct value or incorrect value as
per the column, then we will use a constraint called "check"

## example

```sql
create table t22(
id int primary key
check(id>=100 and id<=10000),
firstname varchar(100) not null
default 'abc',
salary float check(salary>=10000)
default 10000);
```

## example

```sql
insert into t22(id)
values(100);
insert into t22(id)
values(-10);
insert into t22(id)
values(101);

select * from t22;
```

## example

```sql
alter table t22
modify id int auto_increment;
desc t22;
insert into t22(id) values(104);
select * from t22;
truncate table t22;
```

## example

```sql
create table
t23(id int primary key);
alter table t23
modify id int auto_increment;
desc t23;
```

when we are work with check constraint, the column of the table never
define with "auto_increment", if we define, MySQL will raise an error

when we define the column with not null constraint , the column never take "null" as default value ,when we are not given any value to the column while insertion, it always seeks for the value from the user for
insertion into the column

when we change the value of the auto_increment column using alter, it
change or reset the auto_increment column value, only when the table having any auto_increment column, otherwise it will not change or reset

when we want to give the "auto_increment" to the any column of the
table using alter, we can using following syntax:

```sql
alter table table_name modify column_name data type auto_increment
```

## example

```sql
use employee_fp1_2024;
drop table t23;
create table t23 (id int primary key);
desc t23;
alter table t23 auto_increment=1000;
alter table t23 modify id int
auto_increment;
insert into t23 values();
select * from t23;
```

in MySQL,

only one column can have the auto_increment and that column must
define with constraint either primary key or not null+unique or unique, never be not null constraint

when we define the column with auto_increment with unique, the column
will never take null values and even we given null values, it always takes
number as value
example:
```sql
create table t24
(id int unique auto_increment);
desc t24;
insert into t24 values(null);
select * from t24;
```

