# Databases And Tables

when we want to create the database in MySQL, we will use

following syntax:

```sql
create database database_name;
```

example:

```sql
create database employee_fp2_3_2026;

create database hr_2026;

create database student_2026;
```

when we want to show the all available databases in the MySQL, we

will use the following syntax:

```sql
show databases;
```

when we want to create any table, when we want work with any table

inside the database, then we will always "set the database as current

database", to set the database "current database", then we will use

the following syntax MySQL:

```sql
use database_name;
```

when we want to know the "what is current database", in the MySQL ,

## we will use the following syntax

```sql
select database() ;
```

when we want to create the table in the MySQL database, we will use

the following syntax:

```sql
create table table_name(col_name datatype constraint,

col_name datatype constraint, col_name data_type constraint,

.
.
.
coln datatype constraint)
```

here data type refers "What type of data, the column can have or can

store, we need to specify while creating the table" , while inserting

data, MySQL query processor will check given data as per the "given

data type of column" or not

