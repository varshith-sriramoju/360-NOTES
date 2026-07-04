## MySQL Functions

### Built-in Functions

#### Aggregate Functions

`avg()`, `sum()`, `min()`, `max()`, `count()`

#### Number Functions

`floor()`, `ceil()`, `round()`, `truncate()`, `sqrt()`, `log()`, `log2()`, `log10()`, `bin()`, `oct()`, `hex()`, `mod()`, `greatest()`, `least()`, `abs()`, `pow()`, `power()`

Examples:

```sql
select floor(1.234);
select floor(-1.234);
select ceil(1.234);
select round(1.2345, 3);
select bin(100);
select oct(12);
select hex(1234);
select sqrt(4);
select log(1);
select log2(100);
select log10(100);
select mod(10, 20);
select greatest(1, 2, 3, 4, 5);
select least(1, 2, 3, 4, 5);
select truncate(1.234567, 2);
select pow(1, 2);
select abs(-10);
select power(4, 10);
```

#### String Functions

`upper()`, `lower()`, `ucase()`, `lcase()`, `reverse()`, `length()`, `character_length()`, `trim()`, `ltrim()`, `rtrim()`, `replace()`, `left()`, `right()`, `insert()`, `substr()`, `substring()`, `concat()`, `concat_ws()`, `cast()`, `strcmp()`

Examples:

```sql
select upper('hello');
select lower('HELLO');
select reverse('hello');
select ltrim('           hello');
select rtrim('           hello          ');
select trim('           hello      ');
select length('hello');
select character_length('hello');
select left('hello world', 2);
select right('hello world', 5);
select substr('hello world', 2, 3);
select substring('hello world', 2, 3);
select concat('hello', 'world');
select concat_ws(',', 'hello', 'world');
select replace('hello world', 'hello', 'world');
select cast(123 as char) into @a;
select @a + 10;
select conv(101010, 2, 10);
select strcmp('hello', 'Hello');
```

#### Date and Time Functions

`curdate()`, `current_date()`, `curtime()`, `current_time()`, `current_timestamp()`, `sysdate()`, `now()`, `year()`, `month()`, `day()`, `hour()`, `minute()`, `second()`, `dayname()`, `monthname()`, `date_format()`, `date_add()`, `date_sub()`, `datediff()`

Examples:

```sql
select curdate();
select current_date();
select curtime();
select current_time();
select current_timestamp();
select sysdate();
select now();
select dayname(now());
select monthname(now());
select date_format(curdate(), '%Y-%m-%d');
select date_format(curtime(), '%H:%i:%s %p');
select date_add('2000-5-10', interval 5 day);
select date_sub('2000-5-10', interval 5 month);
select floor(datediff(curdate(), '2000-1-1') / 365) as result;
select firstname, floor(datediff(curdate(), dob) / 365) as age
from employee;
```

