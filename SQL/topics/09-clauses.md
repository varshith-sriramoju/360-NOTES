## clauses in MySQL

1. from

using this, we can specify, where are retrieving the data from the

"table or view"

2. where

using this, we can specify the condition in the select or update or

delete query

using this "We can filter the data" , based on the given condition

## example

```sql
select id, firstname,deptname from employee
where deptname='hr';

select id, firstname,deptname,location from employee
where location='chennai';
```

## 3. order by

using this clause , we can able to sort the any column data in the

result of select either in "Ascending or Descending"

when we want to sort the any column data using order by , it default

sort the given column always in Ascending order

when we want to sort the any column either in "Ascending or

descending order" , we will use the following keywords with order

by:

asc ===> ascending order

desc ===> descending order

## example

```sql
select id, firstname,deptname from employee
where deptname='hr'
order by id;
select id, firstname,deptname from employee
where deptname='hr'
order by id desc;
select id, firstname,deptname from employee
where deptname='hr'
order by 2 desc;
select * from employee order by 3 desc;
```

## 4. distinct

using this column, we can able to retrieve the "unique data from the

table"

when we are using "distinct" with one column, it always give the

unique values

when we are using "distinct" with multiple columns, it always give

the "unique rows"

syntax:

```sql
select distinct col1, col2, col3,....coln from the table_name

where cond order by column asc|desc;
```

## example

```sql
select distinct deptname from
employee;
select distinct deptname, deptid from employee;
select distinct * from employee;

select distinct deptid,deptname
from employee
order by 1 desc;
```

## 5. limit

limit clause is used to "specify how many rows only need to show in the

result"

syntax:

```sql
limit rownumber, offset;
```

offset is used to "tell how many rows need to show in the result"

row number is used to "Tell , in the result from which row number

onwards we need to display the result"

in MySQL , row number always starts from "0" onwards

while using "limit", if we give only one number, then limit is consider

as "offset" only

syntax:

```sql
select distinct col1, col2, col3,....coln from the table_name

where cond order by column asc|desc limit rownumber, offset;
```

## example

```sql
select id,firstname from employee limit 5;
select id,firstname from employee limit 2,3;
-- first highst salary
select salary from employee order by salary
desc limit 1;
-- second highst salary
select distinct salary from employee order by salary
desc limit 1,1;
-- thrid lowest salary
select distinct salary from employee order by salary
asc limit 2,1;
```

## Aggregate functions

1. max() :

using this function, we can able to find the maximum value in the

given column

2. min()

using this function, we can able to find the minimum value in the

given column

3. count()

using this function, we can able to find the "number of values" in

the given column

4. sum()

using this function , we can able to find the "sum of the all values of

given column"

5. avg()

using this function, we can able to find "average value of the given

column"

## example

```sql
select avg(salary) as "average salary"
from employee;
select min(salary) as "minimum salary"
from employee;
select max(salary) as "maximum salary"
from employee;
select sum(salary) as "sum" from
employee;
```

## 6. group by

this clause is used to "group the data based on the given column"

generally we will use the group by columns are "categorical columns"

"categorical columns" means "which able to categorize the data"

when we are working with group by, we will use the aggregate

functions

example:

gender , deptname, deptid, designation, order_date, joining date, .......

## example

```sql
-- get the employee count based on the department
select deptname, count(deptname)
as employee_count
from employee
group by deptname;

select deptname, count(deptname)
as employee_count
from employee
group by deptname order by 2 desc;

/*get the employee maximum salary
based on the department*/
select deptname, max(salary)
as employee_maximum_salary
from employee
group by deptname;
/*get the employee maximum salary
based on the department*/
select deptname, max(salary)
as employee_maximum_salary
from employee
group by deptname order by 2 desc;
```

## 7. having

having is used with "group by clause"

when we want to filter the "group by" result, along with group by

column , we will specify the condition for group by result, we will

use "having" clause

## example

-- get the employee count based on the department

```sql
select deptname, count(deptname)
as employee_count
from employee
group by deptname
having employee_count>=20;

select deptname, count(deptname)
as employee_count
from employee
group by deptname
having employee_count<=20;

select deptname, count(deptname)
as employee_count
from employee
group by deptname
having employee_count<=20

order by 2 desc;
```

## example

```sql
select location,deptname,count(deptname)
from employee
group by 1,2;
select location,deptname,count(deptname)
from employee
group by 1,2
order by 1;
```

## example

```sql
select deptname, count(deptname)
from employee
where salary>=100000
group by deptname
having count(deptname)>=10
order by 1;
```

## example

```sql
select distinct deptname, count(deptname)
from employee
where salary>=100000
group by deptname
having count(deptname)>=10
order by 1;
```

