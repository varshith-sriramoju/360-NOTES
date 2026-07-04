## CASE Statement

```sql
select firstname, salary,
case
    when salary >= 50000 and salary <= 100000 then 'Low'
    when salary > 100000 and salary <= 200000 then 'medium'
    when salary > 200000 and salary <= 350000 then 'high'
    else 'out of range'
end as salary_type
from employee
order by salary;
```

