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
1  2  3  4  5           â†’  i = 1, j = 1, 2, 3, 4, 5
1  2  3  4  5           â†’  i = 2, j = 1, 2, 3, 4, 5
1  2  3  4  5           â†’  i = 3, j = 1, 2, 3, 4, 5
1  2  3  4  5           â†’  i = 4, j = 1, 2, 3, 4, 5
1  2  3  4  5           â†’  i = 5, j = 1, 2, 3, 4, 5

1st loop (outer loop) â†’ rows or one side
2nd loop (inner loop) â†’ columns or many side
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
