## User-Defined Functions

A function is a database object that accepts parameters, performs logic, and returns exactly one value.

### Syntax

```sql
delimiter $$
create function function_name(parameter1 datatype)
returns return_type
deterministic
begin
end $$
delimiter ;
```

### Examples

```sql
delimiter //
create function mysum(a int, b int)
returns int
deterministic
begin
    return a + b;
end //
delimiter ;

select mysum(10, 20);
```

```sql
delimiter //
create function evenOrOdd(a int)
returns varchar(100)
deterministic
begin
    if a % 2 = 0 then
        return 'even';
    else
        return 'odd';
    end if;
end //
delimiter ;

select evenOrOdd(10);
```

### Show and Drop Functions

```sql
show function status;
show function status where db = database();
drop function mysum;
```

