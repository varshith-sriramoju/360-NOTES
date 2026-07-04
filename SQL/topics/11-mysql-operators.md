## MySQL operators

arithmetic operators: +, *, -, /,%

logical operators: or, and , not

bitwise operators: |, &,^

is operator:

is operator is used in MySQL, to retrieve the "any null data from the

table"

example:

salary is null <=== get the salary data from the table, where the

data is null

salary is not null <=== get the salary data from the table, where the

data is not null

in operator:

in MySQL, we will use "in" operator , to get the data from the table,

related to multiple values

in ===> related to multiple values

not in ===> not related to given multiple values

example:

location in ('hyd','che','blr')

location not in ('hyd','che','blr')

## between operator

between is used to get the data from the table for given range

col_name between cond1 and cond2;

example:

salary between 10000 and 20000;

(salary>=10000 and salary<=20000)

salary not between 10000 and 20000)

(salary<=10000 and salary>=20000)

## example

```sql
use employee_fp1_2024;

select * from employee where
salary>=10000 order by salary asc;

select * from employee where
salary<=10000 order by salary asc;

select * from employee where
salary=10000 order by salary asc;

select * from employee where
salary!=10000 order by salary asc;

select * from employee where
salary<>10000 order by salary asc;

select * from employee
where
salary between 60000 and 100000;

select * from employee
where
salary >=60000 and salary<=100000;

select * from employee
where
salary <=60000 or salary>=100000;

select * from employee
where location in ('pune','hyderabad')
order by 8;

select * from employee
where location='pune' or
location='hyderabad'
order by 8;

select * from employee
where location not in ('pune','hyderabad')
order by 8;

select * from employee
where salary is null;

select * from employee
where salary is not null;
```

## like operator

using this operator, we can able to get the data from the table

based on the given "pattern"

to create the pattern for " like" , we will use the following characters:

1. _ (this refers exactly one character)

2. % (this refers zero or more characters)

the above characters are called as "wild-card characters"

like pattern

example:

like "a%" ====> a,anil, arun, ajay, anaconda, aaaaaaaaaaaa,.....

like "%a" ===> a, ana, aba, accccccca,...................

like '%a%' ===> a,mallayya, yellamma, yadhamma,

like '_a' ===> la, ba, pa,.............

like 'a_a' ===> aba, aca, ada,..........

like '____' ===> abcd, dcbb,acbb,..........

## example

```sql
select firstname from
employee where firstname like 'a%';

select firstname from
employee where firstname like '%a';

select firstname from
employee where firstname like '%a%';

select firstname from
employee where firstname like 'a____';

select email from employee
where email like '%@%';

select salary from employee
where salary like '%45%';

select firstname from
employee where firstname like 'a%';

select firstname from
employee where firstname like '%a';

select firstname from
employee where firstname like '%a%';

select firstname from
employee where firstname like 'a____';

select email from employee
where email like '%@%';

select dob from employee
where dob like '%1998%';
```

