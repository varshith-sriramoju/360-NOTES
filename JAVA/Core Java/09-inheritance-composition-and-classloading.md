## Accessing Members of Another Class

- In java, a class can access the members of another class.
- There are 2 ways using which a class can access the members of another class:

1. **Inheritance**
2. **Composition**

**Usage:**
- If a class wants to access all the members of another class use inheritance.
- If a class wants to access few members of another class use composition.

## Inheritance

**What is inheritance?**

- Acquiring all the properties of one class into another class is called as inheritance.
- Inheritance establishes is-a relationship (parent child relationship) between the classes.
- In java, to use inheritance we use extends keyword.

### Real-time Example
- A `SavingsAccount` class inheriting common behavior from an `Account` class.

### Application
- Used to reuse code and model parent-child relationships in real systems.

**Example:**
```java
class A     //parent class or super class
{
   void m1() {
   }
   void m2() {
   }
}

class B extends A     //child class or sub class
{
   void m3() {
   }
   void m4() {
   }
}

B obj = new B();
obj.m3();
obj.m4();
obj.m1();
obj.m2();
```

### Type Casting by using Userdefined Datatypes

```java
//parent class or super class
class One  //One type (super class type)
{
   public void m1() {
   }

   public void m2() {
   }
}

//child class or sub class
class Two extends One  //Two type (sub class type), One type (super class type)
{
   public void m3() {
   }

   public void m4() {
   }
}

Two t = new Two();   //valid

One o = new Two();   //valid

One o = new One();   //valid

Two t = new One();   //invalid
```

**Notes:**
- A sub class is sub class type as well as super class type because a sub class has both sub class and super class properties.
- A super class is super class type only but not sub class type because super class has only super class properties but not sub class properties.
- As a sub class is sub class type as well as super class type that's why we can hold sub class object by using sub class reference variable as well as by using super class reference variable also.
- As a super class is super class type only that's why we can hold super class object by using super class reference variable only but not using sub class reference variable.

**Example:**
```java
class One
{
   public void methodOne() {
   }
}

class Two extends One
{
   public void methodTwo() {
   }
}

One o = new Two();
o.methodOne();
o.methodTwo();   //c.e
```

**Notes:**
- If super class reference variable is holding sub class object then by using super class reference variable we can access only super class members but we cannot access sub class members.
- If we want to access both sub class members and super class members we need sub class object as well as sub class reference variable.

**Type Casting Example:**
```java
class One
{
   public void methodOne() {
   }
}

class Two extends One
{
   public void methodTwo() {
   }
}

One o = new Two();
Two t = (Two)o;
t.methodOne();
t.methodTwo();
```

---

## instanceof

- instanceof operator is used to test object is an instance of a class type or not.

### Real-time Example
- Checking whether a received object is a `Student` before casting it in a school management system.

### Application
- Used for safe type checking before casting and for branching behavior based on object type.

**Syntax:** `boolean b = objectName instanceof ClassName;`

**Notes:**
1. Object has type and object type is classname which is a userdefined datatype.
2. Using instanceof operator we cannot test two different classes (types) which are not having parent child relationship that is inheritance.

### java.lang.Object

- It is a class available in java.lang package
- In java, for every class Object is the super class.
- As every class in java is a sub class of Object class that's why every class is Object type.

---

### Composition

![Composition Diagram](./images/composition-diagram.png)

**What is composition?**
- Composition is a relationship between two objects where one class object has the reference of another class object to access the members.
- Composition establishes has-a relationship between the classes or objects.
- In java, to use composition there is no specific but we use new operator.

### Real-time Example
- A `Car` object having an `Engine` object, or an `Order` object having a `Payment` object.

### Application
- Used when one class needs to reuse another class as a part of its state or behavior.

### Example 1: Composition without Constructor

```java
class One
{
   int i = 10;

   public void m1() {
      System.out.println("from m1");
   }

   public void m2() {
      System.out.println("from m2");
   }
}

class Two
{
   One o;  //creating reference variable of class One as instance variable

   public void m3() {
      System.out.println("from m3");
      o = new One();
      o.m1();
   }

   public void m4() {
      System.out.println("from m4");
      o.m2();
      System.out.println(o.i);
   }
}

Two t = new Two();
t.m3();
t.m4();
```

### Example 2: Composition with Constructor

```java
class One
{
   int i;

   public One(int i) {
      this.i = i;
   }

   public void m1() {
      System.out.println("from m1");
   }

   public void m2() {
      System.out.println("from m2");
   }
}

class Two
{
   One o;  //creating reference variable of class One as instance variable

   public Two(One o) {
      this.o = o;
   }

   public void m3() {
      System.out.println("from m3");
      o.m1();
   }

   public void m4() {
      System.out.println("from m4");
      o.m2();
      System.out.println(o.i);
   }
}

One o = new One(10);
Two t = new Two(o);
t.m3();
t.m4();
```

---

## Classloading and Classpath

### Class and Classloading

- class means .class file which contains byte code.

What is classloading or loading the class?
- Taking the .class file which contains byte code and placing inside the jvm's method area is called as classloading or loading the class.

### Real-time Example
- When you run a Java program, the JVM loads `Main` and all required library classes before execution starts.

### Application
- Used to locate and load compiled classes from the correct folders or jars at runtime.

### Classloaders

What are classloaders?
- Classloaders are special java classes developed by sun microsystems.
- Classloaders are responsible to load the classes from some directory location in the computer into jvm's memory.

There are 3 classloaders:

1. bootstrap classloader
   - jre\lib\rt.jar
2. extension classloader
   - jre\lib\ext
3. system/app classloader
   - -cp or -classpath
   - set classpath

~~~
api --> predefined classes and interfaces --> jre\lib\rt.jar
                                       |
                                 bootstrap classloader

version to version --> new features --> new classes --> extension classes
                                                |
                                             jar files
                                                |
                                             jre\lib\ext
                                                |
                                         extension classloader
~~~

- system/app classloader loads the classes from classpath location.

### Classpath Basics

- class means .class file
- path means location
- classpath means .class file location

What is classpath?
- Classpath is an environment variable or a system variable which used by compiler and jvm to search for the location of .class files.
- Compiler and jvm search for .class files in the classpath and default classpath is current directory.
- If the .class files are not available in the current directory which is default classpath then we have to change or set the classpath.

### Ways of Setting Classpath

There are 3 ways to set classpath:

1. command level
2. command prompt level
3. operating system level

#### Command Level

- If we set the classpath command level then it will be available until we run the command, so whenever we run the command we have to set the classpath.

Syntax:

~~~
javac -cp directory_location ClassName.java
            (or)
javac -classpath directory_location ClassName.java

java -cp directory_location ClassName
           (or)
java -classpath directory_location ClassName
~~~

#### Command Prompt Level

- If we set the classpath command prompt level then it will be available until command prompt is running. If we close the command prompt then classpath is lost.

Syntax:

~~~
set classpath=directory_location
~~~

#### Operating System Level

- If we set the classpath operating system level it becomes permanent.

### Notes

- javac and java are tools.
- A tool takes options which are also called as switches.
- Switches start with hyphen symbol.
- Switches provide additional information to a tool.
- If we want to set the classpath command level we have to use either -cp or -classpath switches.
- If we want to set the classpath command prompt level we have to use set windows command.
# Inner classes

A class defined inside another class is called an inner (nested) class.

Types:

1. Member inner class
2. Static inner class
3. Local inner class
4. Anonymous inner class

### Member inner class

- Declared as a member of the outer class.
- To create an instance outside the outer class: `Outer.Inner obj = outer.new Inner();`
- If private, it can only be instantiated inside the outer class.

### Static inner class

- Declared `static` inside an outer class.
- It cannot access instance members of the outer class directly.
- Instantiate with: `Outer.StaticInner obj = new Outer.StaticInner();`

### Local inner class

- Declared inside a method or constructor and only visible within it.

### Anonymous inner class

- A class without a name used to create a single object with specific behavior.

---

