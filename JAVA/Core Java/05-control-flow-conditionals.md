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

