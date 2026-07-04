## Control Flow Statements (Control Structures)

- Control flow statements are the statements which are used in the program to specify the order in which the program is executed at runtime.

**By default a program is executed at runtime in linear order that is top to bottom line by line.**

### Real-time Example
- A shopping app checks stock, applies a discount, and then decides whether to place the order.

### Application
- Used whenever a program needs to choose between actions, repeat work, or jump to another point in execution.

### Types of Control Statements

1. **Selection statements**
   - Examples: if statement, if else statement, if else ladder, switch case

2. **Iterative statements**
   - Examples: while loop, do while loop, for loop, for each loop

3. **Transfer statements**
   - Examples: break, continue, return

**Uses:**
- If we want to execute some statements or skip the execution of some statements based on some condition then we should go for selection statements.
- If we want to execute some statements repeatedly for some number of times then we should go for iterative statements.
- If we want to transfer the control from one statement to another statement in the program then we should go for transfer statements.

---

## if Statement (Simple if)

**Syntax:**
```
if(condition/expression)
   statement;
```

**Notes:**
- Here condition or expression must be boolean type
- For one statement body is optional but for more than one statement body is mandatory

### Real-time Example
- If the customer is eligible, show an offer message.

### Application
- Used when a statement should run only if a condition is true, such as validating age, balance, or stock availability.

**Examples:**
```java
1. if(2<5)
     System.out.println("hello");   //hello

2. if(5<3)
     System.out.println("hello");

3. if(2<5)
     System.out.println("hello");   //hello
     System.out.println("bye");     //bye

4. if(2>5)
     System.out.println("hello");
     System.out.println("bye");     //bye

5. if(2>5)
   {
      System.out.println("hello");
      System.out.println("hi");
   }

6. if(2<5)
   {
      System.out.println("hello");    //hello
      System.out.println("hi");       //hi
   }
```

### Nested if Statement

- If statement inside if statement is called as nested if statement.

### Real-time Example
- In a bank app, first check account active, then check balance, then check daily limit.

### Application
- Used when one decision depends on another decision inside the same flow.

**Example:**
```java
int a = 7, b = 3, c = 6;

if(a == 7)
{
   if(b == 3)
   {
      if(c == 6)
      {
         System.out.println("hello");
      }
      System.out.println("welcome");
   }
   System.out.println("hi");
}
```

---

## if else Statement

**Syntax:**
```
if(condition/expression)
   statement-1;
else
   statement-2;
```

**Notes:**
- Here condition or expression must be boolean type
- For if else statement body is optional for one statement and body is mandatory for more than one statement
- If never demands else but else always demands if so if can exist without else but else cannot exist without if

### Real-time Example
- If payment succeeds, print success; otherwise, print failure.

### Application
- Used when both true and false cases need separate actions.

**Examples:**
```java
1. if(2<5)
      System.out.println("hello");    //hello
   else
      System.out.println("bye");

2. if(2>5)
      System.out.println("hello");
   else
      System.out.println("bye");     //bye

3. if(2<5)
      System.out.println("hello");   //hello
   else
   {
      System.out.println("hi");
      System.out.println("bye");
   }

4. if(2>5)
   {
      System.out.println("hello");
      System.out.println("welcome");
   }
   else
      System.out.println("bye");       //bye

5. if(2<5)
   {
      System.out.println("hello");     //hello
      System.out.println("welcome");   //welcome
   }
   else
   {
      System.out.println("hi");
      System.out.println("bye");
   }
```

### Nested if else Statement

- If else statement inside another if else statement is called as nested if else statement.

### Real-time Example
- In an exam portal, first check login status, then check whether the user has submitted the exam or not.

### Application
- Used when one condition branches into more than one dependent decision.

**Syntax:**
```
if(condition-1)
{
   if(condition-2)
      statement-1;
   else
      statement-2;
}
else
{
   if(condition-3)
      statement-3;
   else
      statement-4;
}
```

### else if Ladder

**Syntax:**
```
if(condition-1)
  statement-1;
else if(condition-2)
  statement-2;
else if(condition-3)
  statement-3;
.
.
.
else if(condition-n)
  statement-n;
else
  default-statement;
```

### Real-time Example
- Assigning grade based on marks: `A`, `B`, `C`, `D`, or `F`.

### Application
- Used when multiple conditions must be checked one by one until one matches.

---

## switch case

**Syntax:**
```
switch(expression)
{
   case label-1: statement(s);
   break;
   case label-2: statement(s);
   break;
   .
   .
   .
   case label-n: statement(s);
   break;
   default: statement(s);
}
```

**Notes:**
i. Break is optional.
ii. Cases are optional.
iii. Switch expression and body are mandatory.
iv. Order of cases is not mandatory.
v. The types which are allowed for switch expression are: byte, short, int, char, String, Wrapper class, Enum
vi. Duplicate cases are not allowed.
vii. Switch expression can be a variable or a constant (literal).
viii. Labels must be constants.

### Real-time Example
- Showing menu options in an ATM, where each number selects a different operation.

### Application
- Used when one value must be matched against many fixed choices.

---

## Iterative Statements (Loops)

- If we want to execute the statements repeatedly for some number of times then go for iterative statements.
- Iterative statements are also called as loops.

### Real-time Example
- Printing a receipt number 10 times or processing 100 records from a database.

### Application
- Used for repetitive tasks like counting, searching, validation, and processing collections.

### Types of Loops

1. while loop
2. do while loop
3. for loop
4. for each loop

### Loop Classification

**1. Pre-tested loops:**
- In pre-tested loops first condition is checked and if condition is true then statements are executed or if condition is false no statements are executed.
- Examples: while loop, for loop, for each loop

**2. Post-tested loops:**
- In post-tested loops first statements are executed then condition is checked
- If condition is false one time statements are executed and loop stops
- If condition is true loop repeats.
- Examples: do while loop

---

## while Loop

**Syntax:**
```
while(condition/expression)
{
   statement(s);
}
```

### Real-time Example
- Keep reading PIN attempts while the user has not entered the correct PIN.

### Application
- Used when the number of iterations is not known in advance and depends on a condition.

---

## do while Loop

**Syntax:**
```
do
{
   statement(s);
}
while(condition/expression);
```

### Real-time Example
- Show a menu at least once and keep repeating until the user chooses exit.

### Application
- Used when the loop body must execute at least one time.

---

## for Loop

**Syntax:**
```
for(initialization;condition;increment/decrement)
{
   statement(s);
}
```

**Example:**
```java
// Display multiplication table
9 x 1 = 9
9 x 2 = 18
9 x 3 = 27
.
.
.
9 x 10 = 90
```

### Real-time Example
- Printing all product IDs from 1 to 50 in an inventory report.

### Application
- Used when the number of repetitions is known in advance.

---

## Nested Loops

- Loop inside another loop is called as nested loop.

**Example:**
```
1  2  3  4  5           →  i = 1, j = 1, 2, 3, 4, 5
1  2  3  4  5           →  i = 2, j = 1, 2, 3, 4, 5
1  2  3  4  5           →  i = 3, j = 1, 2, 3, 4, 5
1  2  3  4  5           →  i = 4, j = 1, 2, 3, 4, 5
1  2  3  4  5           →  i = 5, j = 1, 2, 3, 4, 5

1st loop (outer loop) → rows or one side
2nd loop (inner loop) → columns or many side
```

**Note:** If we have rows and columns or if we have one to many relation use nested loops.

### Real-time Example
- Printing a seating chart, calendar table, or multiplication table.

### Application
- Used for matrix-style output, tables, patterns, and row-column processing.

**Code:**
```java
for(int i=1;i<=5;i++)
{
   for(int j=1;j<=5;j++)
   {
      System.out.print(j + "  ");
   }

   System.out.println();
}
```

---

## for each Loop

- It is added in java from jdk 1.5v onwards.
- It is a special loop and it is used to access the elements of array or collection.

**Syntax:**
```
for(datatype variableName : array/collection)
{
   statement(s);
}
```

### Real-time Example
- Reading every student name from an array and printing it one by one.

### Application
- Used to traverse arrays and collections easily when index control is not needed.

---

## Transfer Statements

- There are 3 transfer statements:

1. break
2. continue
3. return

### Real-time Example
- Stop searching once the target item is found, skip invalid records, or return a computed value from a method.

### Application
- Used to control flow inside loops, switch cases, and methods.

### break

- It is a keyword and a transfer statement.
- It can be used only in 2 places:
  i. Inside the switch case
  ii. Inside the loops
- If we use break outside the switch case or loops then compiler gives error.
- Break is used inside the switch case to terminate the execution of switch case and to come out of switch case.
- Break is used inside the loop to terminate the iterations of the loop and to come out of the loop.

#### Real-time Example
- Stop scanning a list of accounts once a matching account number is found.

#### Application
- Used to exit a loop or switch immediately when the required condition is met.

### continue

- It is a keyword and a transfer statement.
- It can be used only inside the loops.
- If we use continue outside the loops then compiler gives error.
- Continue is used inside the loop to skip the iterations of the loop.

#### Real-time Example
- Skip processing invalid student records and move to the next record.

#### Application
- Used when one iteration should be ignored and the next iteration should continue.

### return

- It is a keyword and a transfer statement.
- There are 2 uses of return statement:
  1. Return statement is used to return the value to the method whose return type is other than void
  2. Return statement is used to return the control to the caller of the method

#### Real-time Example
- A method calculates a tax amount and returns it to the billing module.

#### Application
- Used to send a result back from a method or to exit method execution early.