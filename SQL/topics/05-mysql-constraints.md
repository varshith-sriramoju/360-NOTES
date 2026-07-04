## MySQL constraints

## in MySQL, we will have two types of constraints

## 1. integrity constraints (which are defined with in the table)

1. not null

2. unique

3. primary key

4. check

5. default

6. auto_increment

2. referential constraint(this constraint can be defined with two or

## more tables)

1. foreign key (this is used for data integrity)

## 1. not null

when we give the column with "not null" constraint, then the column

will take always "non-null data" or "column never take null values"

we can give the "not null" as a constraint to any number of columns

in MySQL table

when we give the "not null" as constraint , then the column will allow

the "duplicate" values

## 2. unique

when we give the column with "unique" constraint, then the column

will take always "distinct data" or "column never take duplicate values"

we can give the "unique" as a constraint to any number of columns

in MySQL table

when we give the "unique" as constraint , then the column will allow

the "null" values

when we want to make the column "never allow the duplicate values

and null values", then the column must define with both constraints

(not null and unique)

when we create the table column without constraint, the column will

allow the "null" values by default

in MySQL table, for any number of columns, we can able to take

both "not null and unique" as a constraints

## 3. primary key

when we define the "any column with primary key", the column will

always never allow the "null values and duplicate values"

primary key often called as "not null + unique"

in a table, only one column can be defined with "primary key"

when we want to make any column act as "primary key" column,

then the define the "column with both not null and unique"

## 4. default

when we are defining the column of the table with default constraint,

using default constraint, we can give the default value, when we are

inserting the into the column, if we are not specify the any value to

column, if the column default value, then the default value will inserted

as data of the column

the default value of the column in MySQL table is "null"

## 5. check

when we are inserting the data into a column, if we want to insert

right data into the column or if we want to validate the data what we

are inserting to the column, in MySQL we will use constraint called

"check"

while using "Check" constraint, we will give a condition, with this

condition, we can able to validate the data what we are inserting

into the column

in MySQL table, for any number of column can have "check" as

constraint

## 6. auto_increment

when we want to make the column gets data automatically by itself,

in MySQL, we will use a constraint called "auto_increment"

when we give or define auto_increment to any column, the column

must define with "either primary key or unique key"

when we give the any column with auto_increment, the column starts

getting value from "1" on wards by default , we can also can give

any start value for auto_increment column using "alter" command

the every new value in the auto_increment column , always "+1" to

the previous value of the column

## 7. foreign key

when we want to work with "foreign key", we require minimum two

tables or more

using this constraint we can able to "gets data integrity"

when we create the a table called "A" , based on the table "A", we want

to insert data in the another table called "B", here we are using a

constraint called "foreign key"

when we define a column in table called "A" with "primary key or

unique key", using this column we are validating the data in another

table called "B" , then the primary key column of the table "A", we

will uses a foreign key inside the table called "B" ,

complete insert, update and delete always verified first in the table "A"

, based on that table "b" will perform action

creating the table with name "employee" inside the database called

