## Nested Queries

Nested query is also called a subquery. The query inside another query is the inner query or subquery, and the query that contains it is the outer query.

### Types of Subqueries

1. Correlated subquery
   - The inner query depends on the outer query.
2. Non-correlated subquery
   - The outer query depends on the result of the inner query.

### Single Row Subquery

When a subquery returns exactly one value from one column, it is a single-row or single-column subquery.

Example: employee with the maximum salary

```sql
select * from employee
where salary = (select max(salary) from employee);
```

Example: employee whose name starts with `a` and has the maximum salary among such employees

```sql
select * from employee
where salary = (
    select max(salary)
    from employee
    where firstname like 'a%'
)
and firstname like 'a%';
```

Example: employees earning more than the average salary of HR and IT

```sql
select * from employee
where salary > (
    select avg(salary)
    from employee
    where deptname in ('hr', 'it')
)
order by salary;
```

### Multi-Row Subquery

When a subquery returns multiple rows, it is a multi-row subquery. Common operators are `in`, `any`, and `all`.

Example: departments with more than 10 employees

```sql
select * from employee
where deptname in (
    select deptname
    from employee
    group by deptname
    having count(deptname) > 10
);
```

Example: salary greater than at least one salary in HR

```sql
select * from employee
where salary > any (
    select min(salary)
    from employee
    where deptname = 'hr'
);
```

Example: salary greater than all salaries in HR

```sql
select * from employee
where salary > all (
    select max(salary)
    from employee
    where deptname = 'hr'
);
```

### Multi-Column Subquery

Example: department-wise maximum salary with employee details

```sql
select firstname, lastname, deptname, salary
from employee
where (deptname, salary) in (
    select deptname, max(salary)
    from employee
    group by deptname
);
```

### Subquery in FROM Clause

Use an alias for a subquery in the `from` clause.

```sql
select firstname, lastname
from (
    select *
    from employee
    where salary >= 190000 and salary <= 200000
) as result;
```

### Correlated Subquery

Example: employees earning more than their department average salary

```sql
select *
from employee e1
where salary > (
    select avg(salary)
    from employee
    where deptname = e1.deptname
)
order by salary;
```

Example: count of employees by department who earn more than their department average

```sql
select deptname, count(*)
from employee e1
where salary > (
    select avg(salary)
    from employee
    where deptname = e1.deptname
)
group by deptname;
```

### Subquery as a Column

```sql
select *, (
    select avg(salary)
    from employee
) as average_salary
from employee;
```

### Subquery with EXISTS

`exists` checks whether matching rows exist. It does not return row data.

Example: employees from the same department as employee 1002

```sql
select id, deptname
from employee
where deptname = (
    select deptname
    from employee
    where id = 1002
)
and id != 1002;
```

Example: employee details based on the same department

```sql
select *
from employee e2
where exists (
    select 1
    from employee e1
    where e1.deptname = e2.deptname
      and e1.id != e2.id
)
and deptname in ('testing', 'hr')
order by deptname;
```

Example: salary difference and percentage from company average

```sql
select firstname,
       salary,
       salary - (select avg(salary) from employee) as difference,
       ((salary - (select avg(salary) from employee)) / (select avg(salary) from employee)) * 100 as percentage
from employee;
```

