# Null Data In MySQL

## working with null data in MySQL

null data means "not number" or "not a string"
null refers "no value"
when we are not entered any data into column, while insertion, then MySQL can fill default as "null"
to avoid the null values inside the column of the MySQL table, we can
give the constraint called "not null"

example: Null+10000 ===>Null

```sql
create table t11(id int,firstname
varchar(100) not null, salary float);
desc t11;

insert into t11(firstname) values('a');
insert into t11(firstname) values('b');
insert into t11(firstname) values('c');
select * from t11;

insert into t11 values(100,'d',20000);
insert into t11 values(101,'e',30000);
insert into t11 values(102,'f',40000);
select * from t11;

select * from t11;
select count(*) from t11;
select count(id) from t11;
select sum(salary) from t11;
select max(salary) from t11;
select min(salary) from t11;

select * from t11
order by salary;

select * from t11
order by salary desc;

select salary,count(salary)
from t11
group by salary;

select salary,count(salary)
from t11
group by salary having count(salary)>=2;

select salary,count(salary)
from t11
where salary is not null
group by salary;

select salary,count(salary)
from t11
where salary is null
group by salary;
```

when the columns contains null data,
if use any aggregate function (count(), avg(), max(), min(), sum()) for
any column, which contains null data, then the aggregate function will not
consider the null values

when the column contains null data, if we use column with order by ASC,
the order by will give the result as " first it will keep all null values, then it
keep non null values in ascending order"

when the column contains null data, if we use column with order by DESC,
the order by will give the result as " first it will keep all non-null values in
descending order , then it keep null values at end"

when we use the column with group by clause , the it will keep null category result as always "0"

## how to check the null values in the table column

when we want to "null values" inside the a column, in MySQL we will use
a function called "isnull()"
if the column contains "null" value, then isnull() returns "1"
if the column contains "non-null" value, then isnull() returns "0"

if we want to see the total missing values or null values in a particular
column, then in MySQL we will use the following syntax:

```sql
select count(*)-count(column_name) from table_name;
```

when we want to retrieve the data from the column, if the column contains any null data, in place of null data, we want to show any default
value in the result, we will use a function called "ifnull()"

## example

```sql
select ifnull(id,10000) from t11;
```

when we working with null, in MySQL we will use a function called
"coalesce()", when we use coalesce() function with user-defined values,
always return "non-null" value

if coalesce() function got all are null values, it always return "null" as result

when we use the coalesce() function with column , it always takes one
by one value from the column, return the value based on the value what
it gets , if value is "null", then it will return "null", otherwise "non-null" value as result

## example

```sql
select null+10000;
select null*10000;
update t11 set salary=salary+10000;
select * from t11;
update t11
set salary=ifnull(salary,10000)+10000
where id is null;

delete from t11
where id is null;
select * from t11;
```

## example

```sql
select coalesce(null,null,null,1,2)
as result;
select coalesce(null)
as result;
```

