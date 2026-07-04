## aliasing with MySQL

when we are retrieving the data from the "MySQL table" , we can

change the name of column, in the user defined format using "aliasing"

to alias the column name in the result, we will use a keyword called

"as"

syntax:

```sql
select col1 as "alias_name", col2 as "alias_name",..........

coln as "alias_name" from table name where condition
```

## example

```sql
select id as employee_id from employee;
select id as "employee id" from employee;
```

