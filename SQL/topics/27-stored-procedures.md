## Stored Procedures

A stored procedure is a collection of SQL statements stored in the database and executed by name.

### Syntax

```sql
delimiter $$
create procedure procedure_name()
begin
end $$
delimiter ;
```

### Example

```sql
delimiter $$
create procedure get_all_employee_details2()
begin
    select * from employee;
end $$
delimiter ;

call get_all_employee_details2();
```

### Parameters

#### IN Parameter

```sql
delimiter //
create procedure get_data_with_id(in myid int)
begin
    select * from employee where id = myid;
end //
delimiter ;

call get_data_with_id(1003);
```

#### OUT Parameter

```sql
delimiter //
create procedure get_average_salary(out mysal float)
begin
    select avg(salary) into mysal from employee;
end //
delimiter ;

call get_average_salary(@average);
select @average;
```

#### INOUT Parameter

```sql
delimiter //
create procedure get_dept_wise_average_salary2(inout mydeptname varchar(100))
begin
    select avg(salary) into mydeptname
    from employee
    where deptname = mydeptname;
end //
delimiter ;

set @deptname = 'hr';
call get_dept_wise_average_salary2(@deptname);
select @deptname;
```

### Show and Drop Procedures

```sql
show procedure status where db = database();
drop procedure get_employee_details2;
```

