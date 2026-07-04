# Alter Command

## working with "alter" command

when the table is already created inside the database, in that table if we

want to do the following actions :

1. if we want to add the new columns into existing table, in MySQL we
will use a command called "alter"
syntax:

```sql
alter table table_name add column_name data type constraint, add

column_name data type constraint, add column_name data type

constraint,..................................................
```

when we are adding the new columns into existing table using "Alter",
"alter" always add the new columns into table at end of the table by
default.

if we want to add the column into table using alter, then we specify the

position using following flags:

1. first (add the column as starting column of the table)

2. after (add the column after the given column in the alter)

## example

```sql
create table s23(firstname varchar(100),
lastname varchar(100));

desc s23;

alter table s23
add email varchar(100) not null unique,
add location varchar(100) not null;

alter table s23 add id int primary key first,
add midname varchar(100) not null;

alter table s23 add deptname
varchar(100) not null after lastname;
```

2. if we want to change the name of the columns in existing table, in

## MySQL we will use a command called "alter"

syntax:

```sql
alter table table_name change column original column_name new_column_name data type constraint, change column original column_name new_column_name data type constraint,...............
```

## example

```sql
desc s23;
alter table s23 change column id empid int;
alter table s23 add deptid int
not null after deptname,
change column
email emp_email varchar(500);
```

3. if we want to change the datatype of the columns in existing table, in
MySQL we will use a command called "alter"
syntax:

```sql
alter table table_name modify column_name data type constraint,
modify column_name datatype constraint,.......................
```

## example

```sql
desc s23;
alter table s23 add zipcode int,
modify emp_email varchar(100) not null;
alter table s23 modify zipcode bigint not null;
```

4. if we want to remove of the columns of existing table, in
MySQL we will use a command called "alter"

## syntax

```sql
alter table table_name drop column_name, drop column_name, drop
column_name,.......................
```

## example

```sql
desc s23;
alter table s23 drop emp_email, drop deptid;
```

5)if we want to change the name of the existing table, in
MySQL we will use a command called "alter"

## syntax

```sql
alter table table_name rename to new_table_name
```

## example

```sql
alter table s23 rename to s24;
desc s24;
```

6. when we want to reset the auto_increment column of the table in

MySQL, we will use "alter" command

syntax:

```sql
alter table table_name auto_increment=value;
```

## example

```sql
create table s25(id int primary key auto_increment);
insert into s25 values();
select * from s25;
alter table s25 auto_increment=10000;
```

