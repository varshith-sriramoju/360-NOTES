## Transactions

A transaction is a group of SQL statements executed as a single unit of work. Either all statements succeed or none are applied.

### Commands

1. `start transaction`
2. `commit`
3. `rollback`
4. `savepoint`

### Examples

```sql
create table account(id int, name varchar(100), account float);
```

```sql
start transaction;
insert into account values(2, 'b', 20000);
select * from account;
rollback;
```

```sql
start transaction;
update account set account = account + 500;
select * from account;
commit;
```

```sql
start transaction;
savepoint sp1;
insert into account values(6, 'f', 60000);
update account set account = account + 1000 where id = 1;
delete from account where id = 5;
select * from account;
commit;
```

