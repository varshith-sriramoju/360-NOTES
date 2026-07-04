# Employee Table

## "Employee_fp23_2026"

## employee

```sql
create table employee(
id int primary key auto_increment,
firstname varchar(100) not null,
lastname varchar(100) not null ,
email varchar(100) not null unique,
mobileno bigint not null unique,
location varchar(100) not null ,
zipcode int not null ,
deptid int not null,
deptname varchar(100) not null,
designation varchar(100) not null,
gender varchar(100) not null,
dob date not null,
jod date not null,
salary float not null);
```

once we create the table, we get the table structure, to see the table

structure, we will use the following syntax:

```sql
desc table_name;
```

or

```sql
describe table_name;
```

## example

```sql
describe employee;

or

desc employee;
```

