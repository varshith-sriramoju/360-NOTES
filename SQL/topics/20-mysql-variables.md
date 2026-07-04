## MySQL Variables

```sql
select @a := 10;
select @b := 20;
select @a;
select @b;
```

Example: store average salary in a variable

```sql
use employee_fp1_2024;
select avg(salary) into @average
from employee;
select @average;
select * from employee
where salary > @average;
```

