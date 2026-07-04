## Factory Methods

- **Factory** means which creates something

**What is factory class?**
- A class which contains factory method is called as factory class.

**What is factory method?**
- A method which creates and returns the object of another class is called as factory method.
- If the factory method is not declared using static keyword then it is called as instance factory method and to call instance factory method we need factory class object.
- If the factory method is declared by using static keyword then it is called as static factory method and to call the static factory method we no need factory class object we can call static factory method by using factory class name directly.

**Notes:**
1. If the procedure to create object to the class by using new operator is difficult in this case we should go for factory method to create object to the class.
2. Factory method creates and returns the object of the class by hiding the complexities in creating object to the class.

### Example 1: Instance Factory Method

```java
class Car
{
   int regno = 12345;

   public void drive() {
      System.out.println("driving");
   }
}

class CarFactory   //factory class
{
   public Car createCar()   //instance factory method
   {
      Car c = new Car();
      return c;
   }
}

public class InstanceFactoryMethodExample
{
   public static void main(String[] args)
   {
      CarFactory cf = new CarFactory();
      Car c = cf.createCar();
      System.out.println(c);
      System.out.println(c.regno);
      c.drive();
   }
}
```

### Example 2: Static Factory Method

```java
class Car
{
   int regno = 12345;

   public void drive() {
      System.out.println("driving");
   }
}

class CarFactory    //factory class
{
   public static Car createCar()    //static factory method
   {
      Car c = new Car();
      return c;
   }
}

public class StaticFactoryMethodExample
{
   public static void main(String[] args)
   {
      Car c = CarFactory.createCar();
      System.out.println(c);
      System.out.println(c.regno);
      c.drive();
   }
}
```

---

## Pre-defined Factory Methods

### java.lang Package

- **Object:** It is a class available in java.lang package
- **Class:** It is a class available in java.lang package

### Real-time Example
- Using `Object` to hold a common reference in framework code and `Class` to inspect a loaded type at runtime.

### Application
- These predefined factory-related classes are useful for reflection, runtime type checks, and dynamic object creation.

### Object

- It is a class available in java.lang package.
- In java, every class has Object as a super class (or) Object is the super class for every class.

#### Real-time Example
- A `String`, `Student`, or `Car` object ultimately inherits `Object` methods like `toString()` and `equals()`.

#### Application
- Used when working with common APIs that accept any Java object.

**Notes:**
1. As a sub class is sub class type as well as super class type so every class is Object type because every class has Object as a super class.
2. Using Object class reference variable we can hold any class object because every class is Object type.

### Class

- It is a class available in java.lang package.
- Class class object stores the information of other class.
- Information of class means class name, super class name, variable name, method name.

#### Real-time Example
- Frameworks use `Class` to load plugins, inspect annotations, or create objects dynamically.

#### Application
- Used in reflection, dependency injection, testing frameworks, and dynamic module loading.

**Methods:**
```
java.lang.Class
|- public static Class forName(String className)
|- public Object newInstance()
```

#### forName()

- It is a static factory method available in Class class.
- forName() loads the class explicitly in jvm's method area
- After loading the class forName() creates Class class object
- After creating the Class class object forName() stores the information of loaded class in Class class object
- forName() returns Class class object.

**Syntax:**
```java
public static Class forName(String className) throws ClassNotFoundException
```

#### newInstance()

- It is an instance factory method available in Class class.
- newInstance() takes the name of the loaded class from Class class object
- After taking the name of the loaded class from Class class object newInstance() creates loaded class object
- After creating loaded class object newInstance() stores loaded class object in Object class reference variable
- newInstance() returns loaded class object as Object type.

**Syntax:**
```java
public Object newInstance() throws IllegalAccessException, InstantiationException
```

### Can we create object to a class without using new operator?

![New Operator](./images/new-operator.png)

**Answer:** Yes, we can create object to a class without using new operator and to create object to a class without using new operator we have to follow 2 steps.

**Step 1:** Load the class explicitly in jvm's method area by using forName() factory method

**Step 2:** Create object to the loaded class whose information is available in Class class object by using newInstance() factory method

**Note:** We can create object to a class without using new operator that is by using forName() and newInstance() factory methods.

### Example: Creating Object without new Operator

```java
class Employee
{
   int id = 1;
   String name = "john";

   public void work() {
      System.out.println("working");
   }
}

public class Test
{
   public static void main(String[] args) throws Exception
   {
      Class c = Class.forName("Employee");
      Object o = c.newInstance();
      Employee e = (Employee)o;
      System.out.println(e);
      System.out.println(e.id + " - " + e.name);
      e.work();
   }
}
```

---

## java.util.Calendar

- **Calendar:** Abstract class available in java.util package

### Real-time Example
- Setting a meeting date, invoice due date, or exam timetable using calendar values.

### Application
- Used for date and time calculations, scheduling, and date-based business rules.

**Method:**
```
java.util.Calendar
|- public static Calendar getInstance()
```

**Example:**
```java
// Calendar is an abstract class so we cannot create object directly
Calendar cal = new Calendar();  //error

// Instead use getInstance() factory method
Calendar cal = Calendar.getInstance();
```

---


## Constructors

**What is a constructor?**

- A constructor is a special method which is called by jvm automatically at the time of creating the object to initialize instance variables.

**Purpose:** The purpose of constructor is to initialize instance variables.

### Real-time Example
- Creating a `Customer` object with name, id, and balance already set through a constructor.

### Application
- Used to ensure every object starts in a valid state.

### Rules for Writing Constructor

1. Constructor name must be same as classname and ends with parenthesis
2. Constructor cannot have return type
3. Constructor can have access modifier like public, private, protected
4. Constructor may or may not have parameters or arguments
5. Constructor must have body
6. Constructor cannot have return satement

### Types of Constructors

1. **Zero parameterized constructor** (zero argument constructor)
2. **Parameterized constructor** (argument constructor)

- A constructor which has 0 parameters is called as zero parameterized constructor or zero argument constructor.
- A constructor which has 1 or more parameters is called as parameterized constructor or argument constructor.

### Default Constructor

**What is default constructor?**
- If we dont write any constructor in a class then java compiler at the time of compilation writes one constructor such constructor is called as default constructor.
- Default constructor is a zero parameterized constructor.
- If we write any constructor in a class java compiler will not write default constructor.

### Constructor Overloading

**What is constructor overloading?**
- Writing two or more constructors in the same class with different parameters is called as constructor overloading and such constructors are called as overloaded constructors.

**Difference in parameters:**
- Number of parameters
- Type of parameters
- Order of parameters

**Example:**
```java
class One
{
   public One() {
   }

   public One(int i) {
   }

   public One(float j) {
   }

   public One(int i, float j) {
   }

   public One(float i, int j) {
   }
}
```

### Constructor Examples

#### Case 1: No Constructor Written

```java
class One
{
}

One obj1 = new One();   //it works (default constructor)
One obj2 = new One(10);   //error
```

#### Case 2: Zero Parameterized Constructor Written

```java
class One
{
   public One() {
   }
}

One obj1 = new One();  //it works
One obj2 = new One(10);   //error
One obj3 = new One(2.5);  //error
```

#### Case 3: Parameterized Constructor Written

```java
class One
{
   public One(int i) {
   }
}

One obj1 = new One(10);  //it works
One obj2 = new One();    //error
One obj3 = new One(2.5);   //error
One obj4 = new One(10, 20);   //error
```

#### Case 4: Multiple Constructors

```java
class One
{
   public One() {
   }

   public One(double a) {
   }

   public One(int a, float b) {
   }
}

One obj1 = new One();    //it works
One obj2 = new One(2.5);   //it works
One obj3 = new One(10);    //it works
One obj4 = new One(10, 20);   //it works
One obj5 = new One(10, 2.5);   //error
One obj6 = new One(10, 2.5f);   //it works
One obj7 = new One(true);    //error
One obj8 = new One(10, 20, 30);   //error
```

---

## Static Block

- A block which is declared by using static keyword is called as static block.

### Real-time Example
- Loading configuration values, reading environment settings, or initializing shared constants once when the class loads.

### Application
- Used for one-time initialization tasks that should happen before any object is created.

**Syntax:**
```java
static  //static block
{
}
```

**Characteristics:**
- Static block is executed only once at the time of class loading or loading the class.
- If we want to execute any code only once immediately after the class is loaded use static block.
- Static block is used to initialize static variables of the class.
- Static block is executed before the main method.
- Static block cannot access instance variables of the same class directly.

---

## Execution Order in Java

```java
class One
{
   int i;  //instance variable             #4

   static int j;  //static variable        #1

   {                   //instance block      #5
   }

   static {   //static block               #2
      j = 10;
   }

   public One() {  //constructor           #6
      i = 20;
   }

   public void methodOne() {   //instance method      #7
   }

   public static void methodTwo() {   //static method     #3
   }
}

One obj = new One();
```

**Execution Order:**

### Real-time Example
- During application startup, class loading happens first and object creation happens later when the object is needed.

### Application
- Helps predict initialization order when debugging object creation and startup logic.

1. When we create object of class One, first jvm loads class One in jvm's method area
2. At the time of classloading or loading the class:
   - First static variables are created in method area
   - Then static block is executed
   - Then static methods are stored
3. After classloading or loading the class jvm creates object of class One
4. At the time of creating the object:
   - First instance variables are created inside the object
   - Then instance block is executed
   - Then constructor is called to initialize instance variables
   - Then instance methods are stored

---

## this Keyword

- this is a keyword and a reference variable which holds the reference of current class object and points to current class object.
- Using this keyword we can access or refer to current class object and the members of current class object.

### Real-time Example
- In a `Student` constructor, `this.name = name;` is used to assign the parameter value to the instance variable.

### Application
- Used to resolve naming conflicts and chain constructors in the same class.

### Uses of this Keyword

1. **Access current class instance variables**
   - Syntax: `this.instanceVariableName;`

2. **Access current class instance methods**
   - Syntax: `this.instanceMethodName();`

3. **Access current class constructors**
   - Syntax: `this();` or `this(parameters);`

4. **Access current class object**
   - Syntax: `this`

**Note:** When we call a constructor from another constructor using this keyword then this keyword must be the first statement.

---

