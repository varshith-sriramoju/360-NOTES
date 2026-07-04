## foreign key

## master table or parent table

```sql
create table sample10(id int primary key,
firstname varchar(100) not null,
email varchar(100) not null);
```

## derived table or child table

```sql
create table enroll(
id int not null,
cid int not null,
cname varchar(100) not null,
foreign key(id) references
sample10(id) on update cascade
on delete cascade);
```

## inserting the data into sample10

```sql
insert into sample10
values(1,'a','a@gmail.com'),
(2,'b','b@gmail.com'),
(3,'c','c@gmail.com'),
(4,'d','d@gmail.com'),
(5,'e','e@gmail.com');
```

## retrieve the data from the Sample10

```sql
select * from sample10;
```

when we are inserting the data into "enroll", we always need to take
value for "id" , only always "any id of sample10 id column ", we not take any id value which is not present in the sample10, for enroll id column

## inserting the data into enroll

```sql
insert into enroll values(1, 1, 'python');
insert into enroll values(1, 2, 'python with sql'),
(2, 2, 'python with sql'),(2, 1, 'python');
select * from enroll;
```

## updating the data into enroll

```sql
update enroll set id=100
where id=1; <=== it will not run due to master table id column not have
"100" as value
update enroll set id=3
where id=1;
select * from enroll;
```

## update the sample10 table

```sql
update sample10 set id=100
where id=2;
select * from sample10;
select * from enroll;

update sample10 set id=300
where id=4;
update sample10 set firstname='abcd'
where id=1;
select * from enroll;
select * from sample10;

update sample10 set email='abcd@gmail.com'
where id=5;
update sample10 set id=2000
where id=5;
select * from enroll;
select * from sample10;
```

## delete the data from enroll

```sql
delete from enroll where id=100;
select * from enroll;
```

## delete the from the sample10

```sql
delete from sample10 where id=3;
select * from enroll;
select * from sample10;
```

