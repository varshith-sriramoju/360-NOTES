## union

union is used to "combine the multiple query results into single result"

when we use union with multiple queries, union will give the always

"unique rows"

while joining multiple query results into single result in MySQL, we

will use "union"

while joining multiple query results into single result without duplicate

rows in MySQL, we will use "union"

while joining multiple query results into single result with duplicate

rows in MySQL, we will use "union all"

while we are doing "union or union all", the column count in all

queries what we taken for union or union all operation, should be

same

when we apply the union on the queries, the union result always

come with first query column names only

## example

```sql
select id,firstname,lastname
from employee
union
select deptid,deptname,location
from employee;
```

## example

```sql
select id,firstname,lastname
from employee
union
select id,firstname,lastname
from employee;
```

## example

```sql
select id,firstname,lastname
from employee
union all
select id,firstname,lastname
from employee;
```

