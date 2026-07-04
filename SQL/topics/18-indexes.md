## indexes in MySQL

index is a  "lookup table" for any table inside the database
indexes are used to "increase the performance of the select query"
in MySQL, we will have following types of indexes:

1. primary key index
2. regular index
3. unique index
4. composite index
5. full text index

## 1. primary key index

when we define the column with "primary key constraint", then the
column automatically gets a index called "primary key index"
for table, we can have only one "primary key index"

## 2. regular index

regular index refers a index
when we want to create a index for one column of table, then index is
called as "regular index"

## 3. composite index

when we create the index for "two or more columns" at a time , then index
is called as "composite index"

## 4. unique index

when we create the index for "one or more columns" using unique , then
the index is called as "unique index"

## 5. full text index

when we create the index for "one or more columns" using full text, then
then the index is called as "full text"

## in general indexes are two types

1. clustered index:
   1. primary key index

2. non-clustered index:
   1. regular index
   2. composite index
   3. unique index
   4. full text index

## example

create the table with name "Sample12"

```sql
use employee_fp1_2024;
create table sample12(id int primary key,
firstname varchar(100) not null,
lastname varchar(100) not null,
deptid int not null,
deptname varchar(100) not null,
salary float not null,
mobileno bigint not null);
```

when we want to show all indexes of the table, in MySQL we will use the
following syntax:

```sql
show indexes from table_name;
```

## example

```sql
desc sample12;
show indexes from sample12;
```

## create the regular index or index

to create the index in MySQL, we will use the following syntax:

```sql
create index index_name on table_name(column_names)
```

## example

```sql
create index i1 on sample12(deptid);
show indexes from sample12;
```

## create the unique index

to create the  unique index in MySQL, we will use the following syntax:

```sql
create  unique index index_name on table_name(column_names)
```

## example

```sql
create unique index i2 on sample12(deptid);
show indexes from sample12;
```

## create the composite index

in MySQL composite index means "Create the index for two or more
columns"
the composite index can be unique index
the composite index can be non-unique index
to create the composite index in mysql, we will use the following syntax:

```sql
create index index_name on table(col1,col2,col3,......coln)
```

or

```sql
create unique index_name on table(col1,col2,col3,......coln)
```

## example

```sql
create index i4 on
sample12(mobileno,deptname);
show indexes from sample12;
create unique index i5 on
sample12(mobileno,deptname);
show indexes from sample12;
```

## create the full text index

when we have the column are text type or categorical type or string type,
then in MySQL, we will use  the  "full text" as index for these type columns
or
when the  columns are defined with "varchar, char, text....." , then we will
preffered this index

to create the full text in MySQL, we will use the following syntax:

```sql
create fulltext index index_name on table_name(col1, col3,...coln);
```

## example

```sql
desc sample12;
create fulltext index i7 on sample12(firstname,
lastname);
show indexes from sample12;
```

when we create the index for any column, then index will uses the  following data structures to maintain internally, those are :

1. B-tree or B+ Tree (this is regular or primary or composite or unique index)
2. Inverted index (this is for full text index)

when we want to drop the any index of the table, in MySQL we will use
the following syntax:

```sql
drop index index_name on table_name
```

## example

```sql
drop index i1 on sample12;
drop index i2 on sample12;
show indexes from sample12;
```

if table is already created , we can also create the index, using alter command in MySQL without using create command
for this we will use the following syntax with alter:

```sql
alter table table_name add index index_name(column_name1,....);
alter table table_name add unique index index_name(column_name1,....);
alter table table_name add fulltext index index_name(column_name1,....);
```

## example

```sql
alter table sample12 add index i10(salary);
alter table sample12 add unique index i11(salary);
alter table sample12 add fulltext index i12(firstname);
show indexes from sample12;
```

in MySQL, we can create the index in the following  ways:

1. after table creation:
   1. using create index
   2. using alter
2. while creating the table using create command

creating the index while creating the table using create command, for this
we will use below syntax:

```sql
create table table_name(col1 type constrint, col2 type constraint, col3
type constrint, ..............coln type constrint,index index_name(col,col2......
coln))
```

```sql
create table table_name(col1 type constrint, col2 type constraint, col3
type constrint, ..............coln type constrint,unique index index_name(col,col2......
coln))
```

```sql
create table table_name(col1 type constrint, col2 type constraint, col3
type constrint, ..............coln type constrint,fulltext index index_name(col,col2......
coln))
```

## example

```sql
create table sample13(
id int, firstname varchar(100) not null,
lastname varchar(100) not null,
salary float not null,
mobileno bigint not null,
primary key(id), index i1(salary),
unique index i2(salary,mobileno));
show indexes from sample13;
```

indexes will not good performance "while we are doing the operations
like insert or update or delete on columns"
indexes will maintain "memory physically"
for table columns, we can not create too many indexes, we create indexes
for column wisely or based on requirement .

