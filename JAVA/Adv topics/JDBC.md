# Java Advanced Topics

## 1. JDBC [SQL]
- introduction
- database, DBMS, RDBMS, SQL
- JDBC vs ODBC
- JDBC driver and types of JDBC drivers
- first JDBC program
- types of statements in JDBC
  - 1. Statement 2. PreparedStatement 3. CallableStatement
- ResultSet
- batch processing
- transaction management
- working with dates in JDBC (Date, Calendar, SimpleDateFormat)
- hardcoding, bowler plate code/logic, DBUtil

## 2. Servlets
- introduction
- web application, web pages, types of web pages
- stand-alone or desktop application
- disadvantages of stand-alone or desktop application
- advantages of web application
- web server, servlet container
- http protocol
- Servlet interface, HttpServlet class, GenericServlet class
- ServletConfig, ServletContext, ServletRequest, ServletResponse
- form based applications
- servlet life cycle
- RequestDispatcher
- scope variables (page, session, application, request)
- doGet() and doPost()
- `<load-on-startup>`

## 3. JSP
- introduction
- differences between servlet and JSP
- JSP elements
  i. template text
  ii. scriptlet
  iii. JSP declaration
  iv. JSP expression
  v. JSP directives
  vi. JSP action tags
  vii. JSP custom tags
  viii. EL-Expression
- JSP implicit objects/JSP implicit variables
  i. request ii. response iii. session, iv. out v. pageContext
  vi. page vii. application viii. config ix. exception
- mvc architecture, mvc-1, mvc-2
- types of logics (business logic, presentation logic, persistence logic etc)
- types of components (model component, view component, controller component)
- Java beans
- jstl

---
## JDBC
#### What is JDBC?
- JDBC stands for Java database connectivity
- JDBC is an api given by Sun Microsystems in 1997.
- using JDBC api we develop Java program to communicate or interact with
the database server.
- communicating or interacting with the database server means sending SQL
queries from Java program to the database server.

API stands for Application Programming Interface
- set of packages and whatever are available inside the packages are
called as api.
- packages contain classes, interfaces, methods, variables & constructors.

#### What is a database?
- a database is an organised collection of data which is stored digitally
in the computer system and which is retrieved digitally from the computer system.
- computer system can be local computer system or remote computer system.

## DBMS
- DBMS stands for database management system
- DBMS is a software which is used to create and manage database.
- the database which is created by using DBMS uses files internally to
store the data.
- files are having disadvantages so indirectly the disadvantages of files
are disadvantages of DBMS.
- files are also called as flat files.

### Disadvantages of Files
1. data redundancy (duplicate data)
2. data inconsistency
3. no data recovery
4. store small amount of data
5. no query language support
6. no security

## RDBMS
- RDBMS stands for relational database management system
- RDBMS is an advance version of DBMS.
- RDBMS is a software which is used to create and manage database.
- the database which is created by using RDBMS uses tables internally to
store the data.

### Advantages of RDBMS
1. no data redundancy
2. data consistency
3. data recovery
4. stores large amount of data
5. query language support
6. security

The following are the RDBMS softwares

1. Oracle Database
2. MySQL Database
3. Sybase Database
4. IBM Db2 Database
5. Microsoft SQL Server Database
- All the RDBMS softwares support one query language called as SQL.

## SQL
- SQL stands for Structured Query Language
- SQL is a query language and it is used to communicate or interact with
the database server.
- communicating or interacting with the database server means sending the
SQL queries.
- in SQL, we have commands.

### Types of SQL Commands
- there are 5 types of SQL commands

1. DDL commands
2. DML commands
3. DQL/DRL commands
4. DCL commands
5. TCL commands

1. DDL commands (Data Definition Language)
   ex: create, drop, truncate, rename, alter

2. DML commands (Data Manipulation Language)
   ex: insert, update, delete

3. DRL/DQL commands (Data Retrieval/Query Language)
   ex: select

4. DCL commands (Data Control Language)
   ex: grant, revoke

5. TCL commands (Transaction Control Language)
   ex: rollback, commit, savepoint
- in SQL, to write SQL queries we use SQL commands.

---
- database vendors develop and release database softwares.
- when we download and install a database software we get 2 softwares.

1. database server software
2. database client software
- user uses database client software to write and send SQL queries to the
database server software.
- database server software executes the SQL query and based on the SQL
query database server software performs operations like creating table,
inserting records, updating records, deleting records and retrieving
records from the database table.
- if database client software wants to communicate or interact with the
database server software we must have to create the connection between
the database client software and database server software.

---
- database vendors release database softwares in 2 formats

1. database enterprise edition (commercial)
2. database express edition (open-source)

Oracle database --> express edition --> 10g, 11g, 12c, 18c, 21c, 23c

Oracle Database
  - database accounts -> system, sys
  - password -> system (all in small cases)
- all the databases support SQL queries and database commands.

Oracle database
  - SQL queries (database independent)
  - database commands (database dependent)

Oracle database commands
Example: connect, disconnect, describe, show, clear screen, edit, exit etc

**Note:**
1. all the Oracle database commands we can run without using semicolon.

2. all SQL queries or SQL statements must be executed by using semicolon.

3. in Oracle database, to create a database account we have to create user
   so creating a user means creating a database account.

### Steps to Create a User in Oracle Database
1. open Oracle database client software (run SQL command line)

2. SQL>connect system/system

3. SQL>create user bms identified by welcome1;

4. SQL>grant connect, resource to bms;

5. SQL>grant create sequence to bms;

6. SQL>show user

7. SQL>disconnect

8. SQL>connect bms/welcome1

**Note:** in Oracle database some predefined tables are available which are
created by Oracle database vendor such tables are called metadata
tables.

      ex: tab, all_users, all_procedures etc

---
- a single database client software cannot be used to communicate or
interact with all the database servers.
- Microsoft observed this problem and to resolve this problem Microsoft
released ODBC api in 1992.

## ODBC (Open Database Connectivity)
#### What is ODBC?
- ODBC is an api given by Microsoft in 1992 and by using ODBC api we
develop a client program to communicate or interact with all the
database servers.
- api is partial (incomplete) because api contains abstract classes and
interfaces so ODBC api is partial, api becomes complete if someone
provides implementation.
- Microsoft has provided the implementation to ODBC api using c and c++
languages and the implementation which is provided by Microsoft to ODBC
api is called as ODBC driver.
- ODBC driver is a software which is developed by Microsoft using c & c++.
- using ODBC driver we can communicate or interact with all the database
servers.
- as a competitor to Microsoft's ODBC api Sun Microsystems released JDBC
api in 1997.

## JDBC (Java Database Connectivity)
#### What is JDBC?
- JDBC is an api given by Sun Microsystems in 1997 and using JDBC api we
develop Java program to communicate or interact with all the database
servers.
- api's are partial because api contains abstract classes & interfaces.
- api becomes complete if someone provides the implementation so JDBC api
is partial.
- all the database vendors have provided the implementation to JDBC api
using Java language and the implementation is called as JDBC driver.
- JDBC driver is a software using which we communicate or interact with
all the database servers.
- for different databases we have different JDBC drivers, if database is
changed JDBC driver needs to be changed but the Java program is same.

### JDBC vs ODBC

| JDBC | ODBC |
|---|---|
| Stands for Java Database Connectivity | Stands for Open Database Connectivity |
| Released by Sun Microsystems in 1997 | Released by Microsoft in 1992 |
| Implementation is provided in Java | Implementation is provided in C and C++ |
| JDBC driver is platform independent | ODBC driver is platform dependent |
| JDBC driver works on any OS | ODBC driver works only on Windows OS |
| JDBC is object oriented | ODBC is procedure oriented |
| JDBC driver performance is high | ODBC driver performance is low |
| JDBC driver can be used only for Java language | ODBC driver can be used for any language |
- JDBC is an api which is a part of jse.
- Sun Microsystems has released JDBC api in the form of 2 packages.

1. java.sql
2. javax.sql
- The most important classes and interfaces of java.sql package.

### interfaces
    1. Driver
    2. Connection
    3. Statement
    4. PreparedStatement
    5. CallableStatement
    6. ResultSet
    7. ResultSetMetaData
    8. ParameterMetaData
    9. DatabaseMetaData

### classes
    1. DriverManager
    2. Date
- The most important classes and interfaces of javax.sql package.

### interfaces
    1. DataSource

### Architecture Of JDBC
JDBC Api
|
Java Program
|
JDBC Driver
|
Database Server
- if we want to develop the Java program to communicate or interact with
the database server 3 things are required :

     1. database server
     2. JDBC driver
     3. JDBC application (Java program with JDBC code)

### Steps to Develop a JDBC Application
- there are 5 steps to develop JDBC application

step-1: register the JDBC driver

step-2: create or establish the connection

step-3: create the statement object

step-4: execute the SQL query

step-5: close the connection

#### What is JDBC driver?
- JDBC driver is a translator which converts Java calls into database
native function calls.
- JDBC driver is a software component which helps the Java program to
communicate or interact with the database server.

### Types of JDBC Drivers
- there are 4 types of JDBC drivers

1. Type-1 (JDBC-Odbc Bridge Driver)
2. Type-2 (Native Api Driver)
3. Type-3 (Network Protocol Driver)
4. Type-4 (Thin Driver)
- Type-4 (thin driver) is purely developed in Java and it is the fastest
JDBC driver.
- Type-1, Type-2 and Type-3 JDBC drivers are not purely developed in Java,
some part is developed in native languages and some part is developed
in Java so Java calls should be converted to native function calls and
vice versa that's why these 3 types of JDBC drivers are slow.
- the latest version of JDBC api is 4.3.
- from JDBC api 4.0 onwards type-1 JDBC driver is removed from JDBC.

java.sql
  - Driver (interface)

#### What is driver class?
- a class which provides the implementation to Driver interface is called
as driver class.
- all the database vendors have provided implementation class to Driver
interface and that class is called as driver class.
- database vendors have developed driver classes.
- in driver class, database vendors have written the code or logic to
convert Java calls into database native function calls so driver class
is nothing but JDBC driver.
- JDBC driver is driver class or driver class is JDBC driver.

```text
Oracle type-4 driver class -> oracle.jdbc.driver.OracleDriver (Oracle type-4 JDBC driver)
MySQL type-4 driver class -> com.mysql.jdbc.Driver (MySQL type-4 JDBC driver)
```
driver class <--> JDBC driver
- JDBC driver is driver class and driver class is an implementation class
of Driver interface which is developed by database vendors.

java.sql
  - DriverManager (C)
- DriverManager is a class available in java.sql package.
- DriverManager manages set of JDBC drivers.
- DriverManager maintains a list of JDBC drivers, when we try to create
or establish the connection with the database server, DriverManager
takes appropriate JDBC driver from the list of registered JDBC drivers
and helps Java program to use JDBC driver to communicate or interact
with the database server.

### Step 1: Register the JDBC Driver

```java
Driver d = new oracle.jdbc.driver.OracleDriver();
DriverManager.registerDriver(d);
```
- creating the driver class object (JDBC driver) and giving driver class
object to DriverManager class by using registerDriver() is called as
registering the JDBC driver.

DriverManager
  - public static void registerDriver(Driver d)
- registerDriver() registers the JDBC driver with DriverManager.
- database url contains the information of the database like database
name, ip address of the computer in which database is running, port
number, protocol etc.
- database vendors are responsible to provide database url.

Oracle db url --> jdbc:oracle:thin:@localhost:1521:xe

MySQL db url --> jdbc:mysql://localhost:3306/databasename

### Step 2: Create or Establish the Connection
- if the Java program wants to communicate or interact with the database
server then Java program must create or establish the connection with
the database server and the connection will be a logical connection.

```java
Connection con = DriverManager.getConnection("jdbc:oracle:thin:@localhost:1521:xe", "bms", "welcome1");
```
- here con is object of Connection which represents database connection.

DriverManager
  - public static Connection getConnection(String dburl, String dbusr, String dbpwd)
- getConnection() uses database url to know the information of the database and username, password to create or establish the connection with
the database server then getConnection() represents database connection
by creating connection object and returns connection object.
- here connection object represents database connection.

---
- a connection is like a road between Java program and database server.
- we need a vehicle who can carry SQL queries from Java program to the
database server over road (connection) so statement acts as vehicle.
- a statement is an object and using statement object we can send SQL
queries from Java program to the database server over the connection.
- in JDBC, 3 types of statements are there.

    1. Statement
    2. PreparedStatement
    3. CallableStatement
- all the 3 statements are interfaces available in java.sql.
- database vendors have provided the implementation classes to all the
above 3 statements which are interfaces.
- Sun Microsystems has provided factory methods to create and return the
object of all the above 3 interfaces implementation classes.
- we can create object to implementation class of an interface but not
interface, we can create reference variable to an interface to hold
implementation class object.

Connection
  - public Statement createStatement():
- it creates and returns statement object which is used to send the SQL
queries from Java program to the database server.

### Step 3: Create the Statement Object
- we need a statement object to send the SQL queries from Java program
to the database server over the connection.


```java
Statement stmt = con.createStatement();
```
### Step 4: Execute the SQL Query
- using the statement object sending the SQL query from Java program to
the db server over the connection is called as execute the SQL query.

```java
int n = stmt.executeUpdate("insert into employee values(1, 'ravi', 'm', 1000.0)");
```
### Step 5: Close the Connection
- after using the connection, if the connection is not in use then it is
always recommended to close the connection.

```java
con.close();
```
Connection
  - public void close(): it closes the database connection.
- in JDBC, SQL queries are divided into 2 types :

    1. non-select queries  2. select queries

1. non-select queries
- the queries which do not start with select keyword.

Example: insert, update, delete
- to send non-select queries Sun Microsystems has provided a method :
```java
public int executeUpdate(String query)
```
2. select queries
- the queries which starts with select keyword.

Example: select
- to send select queries Sun Microsystems has provided a method :
```java
public ResultSet executeQuery(String query)
```
- both executeUpdate() and executeQuery() are available in Statement.

Statement
  - public int executeUpdate(String query)
  - public ResultSet executeQuery(String query)

**Req:** write a Java program to insert employee record in database table.

Oracle 10g --> ojdbc14.jar (com\jdbc\driver\OracleDriver.class)
Oracle 11g --> ojdbc6.jar (com\jdbc\driver\OracleDriver.class)
- ojdbc6.jar is available in Oracle database software folders.

**Note:**
1. all the methods of java.sql package throws SQLException which is a
   checked exception.

2. it is recommended to use JDBC to perform dml and dql operations only.

### DML Operations Using Statement
1. insert
2. update
3. delete

### DQL/DRL Operations Using Statement
1. select all the columns and all the records
2. select all the columns and specific records
3. select specific columns and all the records
4. select specific columns and specific records
5. select all the columns and one record
6. select 1 column and 1 record

### ResultSet
- ResultSet is an object which holds the result of a select query.
- the result of a select query is table of records so a ResultSet object
holds table of records.
- the data which is in the form of rows and columns is called relational
data.
- ResultSet object maintains a cursor which is initially before the first
record, to move the cursor to next record we have to use next() method.

java.sql
  - ResultSet (interface)
- ResultSet is an object of a class which is an implementation class of
ResultSet interface so indirectly we can say ResultSet is an object.

---
### Ways of Registering JDBC Driver
- there are 3 ways to register the JDBC driver.

### 1st way
Driver d = new oracle.jdbc.driver.OracleDriver();
DriverManager.registerDriver(d);
- in this way of registering the JDBC driver, JDBC driver is registered
for 2 times.

### 2nd way
- load the driver class explicitly in jvm's memory by using forName()
factory method then automatically the JDBC driver will be registered.

Class.forName("oracle.jdbc.driver.OracleDriver");
- in JDBC, loading the driver class means registering the JDBC driver.

### 3rd way
- from JDBC api 4.0v onwards we no need to register the JDBC driver, the
JDBC driver will be registered automatically.

**Note:**
1. database vendors have developed driver classes and as part of driver
   classes database vendors have written one static block and inside the
   static block database vendors have written the code to register the
   JDBC driver.
Example: Oracle driver class

```java
package oracle.jdbc.driver;

public class OracleDriver implements Driver
{
  static
  {
     Driver d = new oracle.jdbc.driver.OracleDriver();
     DriverManager.registerDriver(d);
  }

  //code
}
```

Example: MySQL driver class

```java
package com.mysql.jdbc;

public class Driver implements Driver
{
   static
   {
      Driver d = new com.mysql.jdbc.Driver();
      DriverManager.registerDriver(d);
   }

   //code
}
```

---
database client software
  - 1. cui database client
  - 2. gui database client

Oracle database --> gui tool --> Oracle SQL developer, toad

MySQL database --> gui tool --> sqlyog, MySQL workbench

---
### PreparedStatement
- PreparedStatement is an object and it is used to send parameterized SQL
queries from Java program to the database server.

### steps to develop JDBC application using PreparedStatement
step-1: register the JDBC driver (load the driver class)

step-2: create or establish the connection

step-3: create the PreparedStatement object by passing the SQL query with
positional parameters

step-4: set the values to all the positional parameters

step-5: execute the SQL query

step-6: close the connection

### Positional Parameters
- in PreparedStatement, question mark symbol is called as positional
parameter.
- positional parameters act as place holders in SQL query, in SQL query
instead of using the values we use positional parameters and we have
to pass the values to positional parameters using the setter methods
of PreparedStatement.
- every positional parameter has an index which starts from '1'.

    ex: ?, ?, ?, ?, ? ---> positional parameters
        |  |  |  |  |
        1  2  3  4  5 ---> indexes
- in JDBC, to set the values to positional parameters we have to use
setter methods of PreparedStatement.

public void setInt(int positionalParamIndex, int value)
public void setString(int positionalParamIndex, String value)
public void setFloat(int positionalParamIndex, float value)
public void setDouble(int positionalParamIndex, double value)
public void setDate(int positionalParamIndex, java.sql.Date d)

java.sql
  - PreparedStatement (I)
  - Connection
  - public PreparedStatement prepareStatement(String query)

### DML Operations Using PreparedStatement
1. insert
2. update
3. delete

### DQL/DRL Operations Using PreparedStatement
1. select all the columns and all the records
2. select all the columns and specific records
3. select specific columns and all the records
4. select specific columns and specific records
5. select all the columns and one record
6. select 1 column and 1 record
- if we have dynamic values in SQL query use PreparedStatement or else
use Statement.
- PreparedStatement improves performance because in PreparedStatement
query compiles only once.
- if we send same query multiple times with different values then only
PreparedStatement improves performance.
- if we want to send different queries then use Statement.

---
### Assignment
my_images
  - img_id (number)
  - img_name (varchar2)
  - image (blob)

d:\pictures\tiger.jpg

req: write a Java program to insert the image in the database table.

---
### CallableStatement
- CallableStatement is an object and CallableStatement is used to call
database stored procedure from Java program.

java.sql
  - Connection
  - public CallableStatement prepareCall(String SQL)
  - CallableStatement (I)
  - public boolean execute()

#### What is a stored procedure?
- a stored procedure is a reusable block of statements which is written
to perform some operation.
- a stored procedure is used to write business logic and SQL queries.
- a stored procedure is created in the database, resided in the database
and executed in the database.

---
```sql
SQL> create table product
(
pid number(5) primary key,
pname varchar2(20),
price number(8, 2),
);

SQL> create or replace procedure myproc
as
begin
insert into product values(1, 'dolo', 100.0);
end myproc;
/
- we can call a stored procedure from database client software

SQL> exec myproc
```

---
### Batch Processing (Batch Updates)
- grouping multiple related SQL queries as one batch and submitting the
batch in one call to the database server is called as batch processing.
- as we are not communicating with the database server multiple times over
the network so batch processing improves performance.

Statement
  - void addBatch(String query)
  - int[] executeBatch()

---
### Transaction Management
#### What is a transaction?
- executing sequence of steps as a single unit of work is called as
transaction.
(or)
- executing group of operations to perform one task is called as
transaction.

Example: transferring funds
depositing amount
withdrawing amount
- a transaction has a starting point and an ending point.
- in a transaction if all the operations are executed completely then
it is called as successful transaction and in a transaction if any
operation is failed to execute then it is called failure transaction.
- whether the transaction is successful or failure after the transaction
some changes will happen in the database, in case of successful transaction complete changes will happen in the database and in case of failure
transaction incomplete changes will happen in the database.
- on successful transaction we have to make all the changes permanent
in the database by commit and on failure transaction we should not make
the incomplete changes permanent in the database we should rollback all
the incomplete changes by rollback.

### Types of Transactions
- there are 2 types of transactions

1. local transaction
2. global transaction
- if we perform transaction with a single resource (database) then it is
called as local transaction.
- if we perform transaction with two resources (databases) then it is
called as global transaction.

**Note:**
1. JDBC supports local transaction but not global transaction.

2. in Java, to work with global transaction Sun Microsystems has provided
   JTA (Java Transaction Api).
- if multiple people want to perform multiple transactions then everyone
should use a separate connection.
- by default in JDBC applications JDBC driver manages transaction which
means by default JDBC driver will do auto commit for every transaction
whether it is successful or failure.
- we should not allow JDBC driver to manage the transaction, we should
write the code to manage the transaction.
- we have to manage the transaction only for dml queries but not for dql
queries.

java.sql
  - Connection
  - void setAutoCommit(boolean b)
  - void commit()
  - void rollback()

Java.util
  - Date
  - Calendar

Java.text
  - SimpleDateFormat

java.sql
  - Date
- Calendar is an abstract class available in Java.util package.

Calendar
  - public static Calendar getInstance()
  - public void set(int field, int value)
  - public int get(int field)
  - public void add(int field, int value)
  - public static final int MONTH
  - public static final int YEAR
  - public static final int DAY_OF_MONTH
  - public static final int HOUR
  - public static final int MINUTE
  - public static final int SECOND
  - public static final int AM
  - public static final int PM
  - public static final int AM_PM

### Assignment
connection pooling
