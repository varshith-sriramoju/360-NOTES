## Types of Variables in Java

- A variable can hold single value or multiple values
- So based on the value which is stored by a variable, all variables are divided into 2 types in java.

1. Primitive variables
2. Reference variables

### Real-time Example
- `int age = 21;` for a primitive value and `Employee emp = new Employee();` for an object reference.

### Application
- Used to decide whether a program stores a simple value directly or keeps a reference to an object.

### Primitive Variables

- These variables hold single value.

#### Real-time Example
- Storing a product quantity, marks, or age.

#### Application
- Useful when only one simple value is needed for calculations or checks.

**Examples:**
```java
1. int a = 10;
2. double b = 2.5;
3. char ch = '@';
```

### Reference Variables

- These variables hold object and object contains multiple values.

#### Real-time Example
- Holding a `Customer`, `Car`, or `Account` object in a shopping or banking system.

#### Application
- Useful when a program must work with structured data or multiple related fields together.

**Examples:**
```java
1. String str = new String("hyderabad");
2. class Employee
   {
      int id = 1;
      String name = "john";
      double salary = 1000.0;
   }

   Employee emp = new Employee();
```

**Notes:**
1. The datatype of primitive variable is primitive datatype.
2. The datatype of reference variable is class name which is userdefined datatype.

---

## Variable Types by Position and Purpose

- Based on the purpose and position of declaration of a variable, all variables are divided into 3 types in java.

1. Instance variables
2. Static variables
3. Local variables

### Real-time Example
- A banking app can use instance variables for each account, static variables for shared bank name, and local variables for temporary transaction values.

### Application
- Helps choose the right scope and lifetime for data in a program.

### Instance Variables

1. If the value of the variable has to be different from one object to another object then go for instance variables.
2. Instance variables are declared directly inside the class but not inside the method or block or constructor.
3. Instance variables are created (memory allocated) at the time of object is created and instance variables are created inside the object.
4. Initialization of instance variables is optional, if we dont initialize instance variables then jvm takes the responsibility to initialize the instance variables with default values.

**Default Values:**
| Datatype | Default Value |
|----------|---------------|
| byte, short, int, long | 0 |
| float, double | 0.0 |
| char | '\u0000' |
| boolean | false |
| String | null |
| reference variable | null |

5. Instance variables are also called as object variables or non-static variables.
6. Instance variables belong to object.
7. The scope of instance variables is same as object scope because when object is created instance variables are created and we can access instance variables and if object is not created instance variables are also not created and we cannot access instance variables.
8. Lifetime of instance variables is same as object life time because instance variables are created when object is created and instance variables are destroyed when object is destroyed.
9. From static method and static block we cannot access instance variables of the same class directly.
10. In every object a seperate copy of instance variables are created and available.

#### Real-time Example
- In a `Student` object, `name`, `rollNo`, and `marks` can be instance variables because they differ for each student.

#### Application
- Used when each object needs its own state.

**Syntax:** `objectName.instanceVariableName;`

---

## Static Variables

1. If the value of the variable has to be same from one object to another object then go for static variables.
2. Static variables are declared directly inside the class by using static keyword but not inside the method or block or constructor.
3. Static variables are created (memory allocated) only once at the time of classloading in method area.
4. Initialization of static variables is not mandatory, it is optional and if we dont initialize static variables then jvm takes the responsibility to initialize static variables with the default values.
5. Static variables are also called as class variables.
6. Static variables belong to class.
7. **Scope and Lifetime:**
   i. The scope of static variables is same as class scope which means if class is loaded static variables are created so we can access static variables, if class is not loaded static variables are not created so we cannot access static variables.
   ii. The lifetime of static variables is same as class lifetime which means static variables are created when class is loaded and static variables are destroyed when class is unloaded.
8. From static method and static block we can access static variables of the same class directly.
9. Every object in heap area shares a single copy of static variable which is created in method area.

#### Real-time Example
- A company name, interest rate, or school name can be kept as static because it is common for all objects.

#### Application
- Used for shared data, counters, constants, and utility values.

**Syntax:** `ClassName.staticVariableName;` (recommended) or `objectName.staticVariableName;`

---

## Local Variables

1. If the requirement of the program or the programmer is to use some variables for temporary purpose then go for local variables.
2. Local variables are declared directly inside the method or block or constructor but not inside the class.
3. Local variables are created (memory allocated) in java stacks when the method or block or constructor execution starts.
4. Initialization of local variables is mandatory at the time of declaring and before accessing.
5. Local variables are also called as temporary variables or automatic variables.
6. Local variables belong to method or block and local variables are method or block members.
7. **Scope and Lifetime:**
   i. We can access local variables only within the method or block or constructor where they are declared but not outside the method or block or constructor so the scope of local variables is method scope or block scope.
   ii. When method or block or constructor execution starts local variables are created and when the method or block or constructor execution completes local variables are destroyed this is called as lifetime of local variables.
8. For instance variables and static variables all modifiers are allowed but for local variables only final modifier is allowed.

#### Real-time Example
- A loop counter, method input total, or temporary tax value inside a billing method.

#### Application
- Used for intermediate calculations and temporary processing inside methods.

**Notes:**
i. We can use primitive variable as instance variable or static variable or local variable.
ii. We can use reference variable as instance variable or static variable or local variable.

---

## Example - Using All Variable Types

```java
class One
{
}

class Two
{
   int i;  //using primitive variable as instance variable
   One o;  //using reference variable as instance variable

   static int j;  //using primitive variable as static variable
   static One o1;  //using reference variable as static variable

   public void methodOne()
   {
      int k; //using primitive variable as local variable
      One o2; //using reference variable as local variable
   }
}
```

---

## Methods

**What is a method?**

- A method is a reusable block of statements and a method is used to perform some operation.

### Real-time Example
- A `calculateInterest()` method in a banking app or a `sendEmail()` method in a notification system.

### Application
- Methods break a program into reusable units and reduce repeated code.

**Syntax:**
```
modifier return-type methodName(parameters/arguments)
{
   statement(s);
   return statement;
}
```

### Return Type

- Before the method name if we use any datatype or void keyword then it is called as return type of the method.
- In java, a method may return some value or may not return some value so the return type of the method indicates whether a method returns a value or not.
- The method whose return type is other than void such method returns some value and the method whose return type is void such method will not any value.
- Return type of the method is mandatory.

### Return Statement

- Return statement is used to return the value to the method whose return type is other than void.
- We cannot use return statement to return the value to the method whose return type is void if we use then compiler gives error.
- We must have to use return statement to return the value to the method whose return type is other than void if we dont use then compiler gives error.
- Return statement depends on return type of the method.

### Parameters (Arguments)

- If we use any variables inside the parenthesis of the method such variables are called as parameters or arguments.
- Method uses parameters or arguments to pass the data and to receive the data.
- Parameters or arguments are optional.
- There are 2 types of parameters:
  1. Actual parameters
  2. Formal parameters
- Method uses actual parameters to pass the data to formal parameters and method uses formal parameters to receive the data from actual parameters.
- Parameters of a method or a constructor are local variables.

### Method Body

- Method body contains statements.
- Method body is also known as implementation.
- Method body is mandatory.

### Method Name

- A method must have a name and ends with parenthesis.

### Modifier

- It is used to specify the scope of the method.

### Different Sections of the Method

**Method has 2 sections:**

1. **Method header or method prototype**
   - Consists of method name, return type, parameters and modifier.
   - Example: `public int add(int a, int b);`

2. **Method body or implementation**
   - Consists of statements.
   - Example:
     ```java
     public int add(int a, int b)
     {
        statement(s);
        return statement;
     }
     ```

---

## Types of Methods

1. **Predefined methods**
   - The methods which are developed and provided by sun microsystems are called as predefined methods.
   - Examples: read(), readLine(), charAt(), equals(), toString()

2. **Userdefined methods**
   - The methods which are developed by the programmer are called as user defined methods.
   - Examples: add(), sub(), mul(), work(), show(), display()

### Real-time Example
- `println()` is a predefined method and `calculateSalary()` is a userdefined method in a payroll system.

### Application
- Predefined methods save time, while userdefined methods represent business rules.

---

## Categories of Methods

1. **A method without parameters or arguments and without return statement**
   ```java
   public void add()
   {
   }
   ```

2. **A method without parameters or arguments and with return statement**
   ```java
   public int add()
   {
      return value;
   }
   ```

3. **A method with parameters or arguments and without return statement**
   ```java
   public void add(int a, int b)
   {
   }
   ```

4. **A method with parameters or arguments and with return statement**
   ```java
   public int add(int a, int b)
   {
      return statement;
   }
   ```

### Real-time Example
- A `login()` method may take username and password, while a `getBalance()` method may return a value without parameters.

### Application
- Different method categories are used depending on whether input or output is needed.

---

## Types of Methods in Java

1. **Instance methods**
   i. Mutator or setter methods
   ii. Accessor or getter methods
2. **Static methods**
3. **Factory methods**
   i. Instance factory methods
   ii. Static factory methods

### Instance Methods

**What is instance method?**
- A method which is not declared using static keyword and which requires object to call is called as instance method.
- Instance method is also called as non-static method.
- Instance methods are stored in jvm's method area at the time of object is created.
- Instance methods belong to object.
- Instance method can access instance variables of the same class directly.
- Instance methods can access static variables of the same class directly.

**Syntax:** `objectName.instanceMethodName();`

#### Real-time Example
- `deposit()` and `withdraw()` methods in a bank account object.

#### Application
- Used when behavior depends on object state.

**Note:** If we want to perform any operations on instance variables then use instance methods.

**Example:**
```java
class One
{
   int a = 10;   //instance variable
   static int b = 20;   //static variable

   public void methodOne()   //instance method or non-static method
   {
      System.out.println("from methodOne");
      System.out.println(a);  //10
      System.out.println(b);  //20
   }
}

One o = new One();
o.methodOne();
```

### Mutator or Setter Methods

- Mutator or setter methods are instance methods and they are used to set or modify the values of instance variables.

### Accessor or Getter Methods

- Accessor or getter methods are instance methods and they are used to get or access the values of instance variables.

**Note:** Mutator or setter methods and accessor or getter methods are called as setters and getters.

### Static Methods

**What is static method?**
- A method which is declared by using static keyword and which does not require object to call is called as static method.
- Static methods are stored in jvm's method area at the time of class loading or loading the class.
- Static methods belong to class.
- Static method cannot access instance variables of the same class directly.
- Static method can access static variables of the same class directly.

**Syntax:** `ClassName.staticMethodName();` (recommended) or `objectName.staticMethodName();`

#### Real-time Example
- `Math.max()`, `Math.sqrt()`, or a utility method like `Utility.formatDate()`.

#### Application
- Used for common operations that do not need object state.

**Note:** If we want to perform any operations on static variables use static methods.

**Example:**
```java
class Two
{
   int a = 10;   //instance variable
   static int b = 20;   //static variable

   public static void methodTwo()   //static method
   {
      System.out.println("from methodTwo");
      System.out.println(a);   //c.e
      System.out.println(b);   //20
   }
}
```

**When should we declare the method as static?**
- If we want to call the method of the class without creating the object then we should declare the method as static.

---

