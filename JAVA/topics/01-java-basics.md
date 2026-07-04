# Core Java

## What is Java?

- Java is a programming language, high level language and object oriented programming language.
- Java is a programming language and using programming language we write programs to develop or build software or application and we use software or application to perform some task.
- As java uses english words and it is user-friendly that's why java is called as high level language.

## What is Object Oriented Programming (OOP)?

Object oriented programming is a programming paradigm.

### Principles of OOP

1. Class
2. Object
3. Data Hiding
4. Abstraction
5. Encapsulation
6. Polymorphism
7. Inheritance
8. Composition

As java follows the principles of object oriented programming paradigm that's why java is called as object oriented programming language.

### Java History

- **Java:** Technology â†’ Sun Microsystems â†’ James Gosling â†’ 1995
- Java is a technology given by sun microsystems and developed by james gosling in 1995.
- Every technology has api as java is a technology so java has api.

## What is API?

- **API** stands for Application Programming Interface
- The predefined classes and interfaces which are developed and provided by sun microsystems in java are called as api.
- We use api (predefined classes and interfaces) to write java programs in order to develop or build software or application.

## Java Editions (Java Platforms)

1. **JSE** (Java Standard Edition)
2. **JEE** (Java Enterprise Edition)
3. **JME** (Java Micro/Mobile Edition)

Sun microsystems has given different java editions or java platforms to develop different types of applications.

## Types of Applications

1. Stand-alone or desktop applications
   - GUI applications
   - CUI applications
2. Web applications
3. Enterprise web applications
4. Distributed applications
5. Mobile applications
6. Embedded systems

### Stand-alone or Desktop Applications

- The applications which runs locally on client machine such applications are called as stand-alone or desktop applications.
- Stand-alone or desktop applications are single user applications.
- To use stand-alone or desktop application internet is not required so without internet we can use stand-alone or desktop applications.
- Stand-alone or desktop applications are 2 types:
  - **GUI applications** (Graphical User Interface)
  - **CUI applications** (Command or Character User Interface)
- To use gui applications we no need to use any commands but to use cui applications we must have to use commands.
- GUI applications provide graphical interface where as cui applications provide command line interface.
- GUI applications are user-friendly than cui applications.

**Examples:** text editors, calculator, calendar, media players, command prompt

### Web Applications

- The application which runs inside the web server is called as web application.
- Web server runs inside server machine.
- Web applications are multi-user applications.
- To use the web applications internet is required.

**Examples:** gmail, online tutorial websites, a company static website

### Enterprise Web Applications

- The large web applications which are developed for business purpose are called as enterprise web applications.
- All enterprise web applications are web applications but every web application is not enterprise web application.

**Examples:** e-commerce websites, banking websites, ticket booking websites

### Distributed Applications

- Two different applications which are running on two different servers and which can share business services over the network to each other are called as distributed applications.

**Examples:** irctc.co.in and makemytrip.com

### Mobile Applications

- The applications which are developed to run on mobile devices are called as mobile applications.

**Examples:** mobile apps

### Embedded Systems

- Embedded systems is a combination of hardware and software, in embedded systems the software is developed and embedded in a hardware.

**Examples:** computer, television

### Platform Mapping

```
JSE  â†’  client side programming
    â”œâ”€ stand-alone or desktop applications (gui and cui applications)

JEE  â†’  server side programming
    â”œâ”€ web applications, enterprise web applications, distributed applications

JME  â†’  micro programming
    â”œâ”€ mobile applications, embedded systems
```
![My project screenshot](./images/networking.png)
---

## Features of Java (Java Buzzwords)

1. Simple
2. Secure
3. Object oriented
4. High performance
5. Robust
6. Multi-threaded
7. Portable
8. Platform independent
9. Architectural neutral


### Simple

- Java follows the similar syntaxes of c and c++ languages which makes learning java simple.
- All the confusing concepts of c and c++ languages like pointers, goto statement and multiple inheritance are eliminated from java to make java simple.

### Object Oriented

- In java, which is an object oriented programming language everything is represented as object that's why java is called as object oriented.

### Robust (Strong)

- Java has better memory management mechanism
- Java has better exception handling mechanism
- In java, programmer is responsible for only allocating the memory but programmer is not responsible for deallocating the memory, the memory deallocation is automatically performed by garbage collector so java has automatic garbage collection.
- In java, sun microsystems has developed and provided api (pre-defined classes and interfaces) to work with exception handling that's why java has better exception handling mechanism.

**Memory Management:** Allocating and deallocating the memory

Types:
1. Static memory allocation - ex: declaring variable, declaring array
2. Dynamic memory allocation - ex: malloc(), calloc(), realloc(), free()

### Platform Independent
![My project screenshot](./images/platform-independent.png)

- After we compile the java program, java compiler generates .class file with byte code, .class file is not specific to any operating system and byte code is also not specific to any processor
- This is called as **WORA** (Write Once Run Anywhere)
- That's why java is called as platform independent.

### Portable

- After compilation java compiler generates the .class file which can be carried on any operating system this is why java is portable.

### Architectural Neutral

- In java, the size of primitive datatype int is same that is 4 bytes irrespective of micro processor architecture that's why java is as architectural neutral.

### Secure

- Before executing the byte code, jvm loads the class which contains byte code in jvm's method area then byte code verification is performed to check whether the byte code which is loaded is valid or invalid
- If the byte code is valid then only byte code is executed by the jvm inside jre and if the byte code is invalid then jvm will not execute the byte code, jvm gives error
- This is why java is secure.

### Multi-threaded

- In java, sun microsystems has developed and provided api (pre-defined clasess and interfaces) to develop multi-threaded applications that's why java is called as multi-threaded.

### Distributed

- Sun microsystems has provided several distributed technologies in java like corba, rmi, ejb to develop distributed applications that's why java is called as distributed.

### High Performance

- In java, along with interpreter sun microsystems has developed and provided JIT compiler (Just In Time compiler) to improve performance
- As java uses interpreter and JIT compiler that's why java is high performance.

### Interpreted

- Java uses interpreter as a translator that's why java is called as interpreted.

### Dynamic

- In java, classloaders load the classes dynamically at runtime that's why java is called as dynamic.

---
![My project screenshot](./images/computer-languages.png)

## What is a Class?

- Anything which does not exist physically which is an imagination about an object is called as class.
- As a class is an imagination about an object so a class will not occupy memory or space.
- A class is a blueprint for creating object.
- A class represents the structure of the object.
- A class is the logical form of the object.
- A class contains variables and methods.
- As variables and methods are available in a class that's why variables and methods are called as members of the class.
- Variables are used to hold data that's why variables are called as data members of the class
- Methods use data members to perform operations that's why methods are called as member methods of the class.
- A class will not have state and behaviours but a class represents the state and behaviours of an object.
- A class is a userdefined datatype in java so creating a class means creating a userdefined datatype
- A userdefined datatype allows a variable to store multiple values which can be homogeneous or heterogeneous.


## What is an Object?

- Anything which exists physically in this real world is called as object.
- As an object is existing physically so an object will occupy memory or space.
- An object is the physical form of the class.
- An object is called as an instance (physical form) of the class.
- Object has state and behaviours, what an object posses or owns represent state
- Using the state what operations an object performs represents behaviours.
- In java, variables represent state and methods represent behaviours.

## Real Word Ex & Appli
- Class : Car
- Obj : Swift, Santro, etc

**Notes:**
1. We can create a class without creating an object but we cannot create object without creating a class so to create object class is mandatory.
2. We can create multiple objects of same class and all objects are called as instances of same class.

---

