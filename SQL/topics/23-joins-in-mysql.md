## Joins in MySQL

Join is used to get data from multiple tables based on a condition.

### Inner Join

```sql
select t.id, t.firstname, e1.id, e1.project_id, e1.project_name
from t1 t
inner join employee_project e1
on t.id = e1.id;
```

### Left Join

```sql
select t.id, t.firstname, e1.id, e1.project_id, e1.project_name
from t1 t
left join employee_project e1
on t.id = e1.id;
```

### Right Join

```sql
select t.id, t.firstname, e1.id, e1.project_id, e1.project_name
from t1 t
right join employee_project e1
on t.id = e1.id;
```

### Full Join

MySQL does not support full join directly, so use `union` of left and right join.

```sql
select t.id, t.firstname, e1.id, e1.project_id, e1.project_name
from t1 t
left join employee_project e1
on t.id = e1.id
union
select t.id, t.firstname, e1.id, e1.project_id, e1.project_name
from t1 t
right join employee_project e1
on t.id = e1.id;
```

### Cross Join

```sql
select t.id, t.firstname, e1.project_id, e1.project_name
from t1 t
cross join employee_project e1
order by id;
```

### Self Join

Example: employee name with manager name

```sql
select t.firstname as employee_name,
       t11.firstname as manager_name
from t1 t
left join t1 t11
on t.manager_id = t11.id;
```

Example: employees reporting to Sneha

```sql
select t.firstname as employeename
from t1 t
left join t1 t11
on t.manager_id = t11.id
where t11.firstname = 'sneha';
```

Example: employee count under each manager

```sql
select t.firstname as manager_name,
       count(t.id) as employee_count
from t1 t
inner join t1 t11
on t.id = t11.manager_id
group by t.id, t.firstname;
```

Example: employees without a manager

```sql
select t.firstname as employee_name
from t1 t
left join t1 t11
on t.manager_id = t11.id
where t.manager_id is null;
```

