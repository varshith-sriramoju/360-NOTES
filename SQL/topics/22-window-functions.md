## Window Functions

Window functions return row-wise results instead of collapsing rows into a single grouped value.

Syntax:

```sql
function_name() over (partition by column_name order by column_name)
```

### row_number()

```sql
select id, firstname, deptname,
       row_number() over(order by id asc) as rownum
from employee;
```

### rank()

```sql
select id, firstname, deptname, salary,
       rank() over(order by salary asc) as rank
from employee;
```

### dense_rank()

```sql
select id, firstname, deptname, salary,
       dense_rank() over(order by salary asc) as dense_rank
from employee;
```

### sum()

```sql
select id, firstname, deptname, salary,
       sum(salary) over(order by id) as running_total
from employee;
```

### avg()

```sql
select id, firstname, deptname, salary,
       avg(salary) over(order by id) as moving_average
from employee;
```

### count()

```sql
select id, firstname, deptname, salary,
       count(salary) over(partition by deptname order by id) as row_wise_count_per_department
from employee;
```

### max()

```sql
select id, firstname, deptname, salary,
       max(salary) over(partition by deptname order by id) as row_wise_maximum_salary_per_department
from employee;
```

### min()

```sql
select id, firstname, deptname, salary,
       min(salary) over(partition by deptname order by id) as row_wise_minimum_salary_per_department
from employee;
```

### lag()

Returns the previous value. The first row has no previous value, so it returns `null`.

```sql
select salary, lag(salary) over(order by salary desc)
from employee;
```

### lead()

Returns the next value. The last row has no next value, so it returns `null`.

```sql
select salary, lead(salary) over(order by salary desc)
from employee;
```

### first_value()

```sql
select firstname, lastname, deptname, salary,
       salary - first_value(salary) over(partition by deptname order by salary desc)
from employee;
```

### last_value()

```sql
select firstname, lastname, deptname, salary,
       last_value(salary) over(
           partition by deptname order by salary desc
           rows between unbounded preceding and unbounded following
       )
from employee;
```

### ntile()

```sql
select firstname, lastname, deptname, salary,
       ntile(4) over(partition by deptname order by salary desc)
from employee;
```

