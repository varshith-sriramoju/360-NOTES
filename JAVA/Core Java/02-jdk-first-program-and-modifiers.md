## JDK vs JRE vs JVM

- **JDK** stands for Java Development Kit.
  - JDK provides an environment in the computer to develop (compile) and run java programs.

- **JRE** stands for Java Runtime Environment.
  - JRE provides an environment in the computer only to run java programs.

- **JVM** stands for Java Virtual Machine.
  - JVM reads the byte code, converts into binary code line by line and executes.

**Relationship:**
```
JDK = JRE + development tools
JRE = JVM + class libraries
```

- Java compiler is a development tool, development tool is an executable file or binary file so javac.exe is java compiler.
- Location: `c:\program files\java\jdk1.8\bin\javac.exe` (java compiler)

### Command Prompt

```
c:\users\xyz>javac -version
```

- Operating system searches for javac.exe in c:\users\xyz which is current directory as it is not available so it will not work
- To make it work we have to change the current directory

```
c:\program files\java\jdk1.8\bin>javac -version
```

- We can run javac.exe only from bin directory but we cannot run javac.exe from any directory
- If we want to run javac.exe from any directory we have to set the path.

### Path

**What is path?**
- Path is an environment variable or a system variable which is used by operating system to search for the location of executable files.
- By default operating system searches for executable files in current directory
- If executable files are not available in current directory then we have to set the path because operating system uses path which is environment variable or system variable to search for the location of executable files.

**Ways of setting path**

1. Command prompt level
2. Operating system level

**Note:** If we want to set the path command prompt level then we have to use set windows command.

#### Command Prompt Level

- If we set the path command prompt level then it will be available until the command prompt is running
- If we close the command prompt then path will be lost.

**Syntax:** `set path=location_of_executable_files`

#### Operating System Level

- If we set the path operating system level then it becomes permanent.

---

## Writing First Java Program

**3 things are required in the computer before writing the java program:**

1. JDK software
2. Java IDE (Integrated Development Environment)
3. Workspace

**Java IDEs:**
- Eclipse
- NetBeans
- IntelliJ Idea
- MyEclipse
- STS

**For Beginners** (to learn internals use text editor):
- Notepad
- Notepad++
- EditPlus

**Workspace:** A directory in the computer where we place all java programs is called as workspace.

**Extension:** The extension of a java program must be .java. A file which ends with .java extension is called as java file.

### Comments

Comments are non-executable statements present in the java program.

**Uses:**
- Comments are used to write documentation in the program.
- Comments make the program more readable and easy to understand.

**Types of comments:**

1. **Single line comments:** `//this is single line comment`

2. **Multi line comments:**
   ```
   /*
       this is multi line comments
   */
   ```

3. **Documentation comments:**
   ```
   /**
       this is documentation comments
   */
   ```

**Why do we use documentation comments?**
- If we want to create our own api document we use documentation comments.
- API means set of packages and whatever are available inside packages are api.
- Package contains classes, interfaces, methods, variables, constructors

**API Structure:**
```
API
â”œâ”€ predefined classes and interfaces
   â”œâ”€ java programs
      â”œâ”€ software/application
```

**API Location:** `C:\Program Files\Java\Jdk1.8\jre\lib\rt.jar`

**API Document:**
- Sun microsystems has developed api document and api document contains only the names of predefined classes and interfaces.
- Predefined classes and interfaces are physically available in rt.jar.
- To know the names of predefined classes and interfaces we have to use api document.

**Documentation Types:**
- **core java** â†’ jse api document
- **advance java** â†’ jee api document

### Creating a Class

**Syntax:**
```
modifier class ClassName
{
   //variables and methods
}
```

**Notes:**
- Here modifier, variables and methods are optional.
- In java, class is a keyword and it is used to create class.
- Class name and the file name must be same.
- Execution of a java program starts from main method.
- In java, main method has a standard signature: `public static void main(String args[])`
- Main method must have body.
- In java, first letter of the classname should be capital.
- String and System are predefined classes.
- Sun microsystems has placed String and System classes in java.lang package.

### Package and Naming Collision

```
developer-1                  pkg1.Employee
-----------
package pkg1;

class Employee
{
}

developer-2
-----------
package pkg2;                pkg2.Employee

class Employee
{
}		             naming collision or naming conflict problem

developer-3
-----------
package pkg3;                pkg3.Employee

class Employee
{
}

developer-4
-----------
package pack1.pack2;         pack1.pack2.Employee

class Employee
{
}

Naming Convention:
com.projectname.modulename.submodulename.ClassName
```

**Problem:** If multiple developers create multiple classes with the same name we get naming collision or naming conflict problem.

**Solution:** Make the class name unique.

**Package Usage:**
- In java, to make the class names unique sun microsystems has provided packages.
- Package is used to make the class name unique.
- In java, to create a package we use package keyword.

**Syntax:**
```
package package-name;
package package-name.sub-package-name;
```

**Notes:**
- Package inside the package is called as sub package.
- Whenever we create a class, before creating the class we should create package then create the class and place the class inside the package.
- If the class is available inside the package then we cannot use the class directly by name
- To use the class which is available inside the package we must have to use fully qualified name of the classname.
- Fully qualified name of the classname means `package-name.ClassName`.

### Import

**What is import?**
- Import is a keyword and it is used to import the classes & interfaces of a package in the java program.
- If we import the package then we no need to use fully qualified name of the class name that is `packageName.className`, we can use the class name directly.

**Syntax:**
```
import package-name.sub-package-name.ClassName;  //explicit import
import package-name.sub-package-name.*;  //implicit import
```

**Note:** `java.lang` package is the default package in every java program.
- If we dont import any package in the java program then java compiler at compile time automatically imports java.lang package.
- Java compiler compiles java program and jvm runs java program.
- `javac` is a command and tool which is used to run java compiler so javac means java compiler.

### Compiling and Running Java Programs

**Compiling Java Program:**
```
Syntax: javac ClassName.java
```

- After compilation java compiler generates .class file (class file) which contains byte code.
- Byte code is special code and only jvm understands byte code.

**Running/Executing Java Program:**
```
Syntax: java ClassName
```

- The above commands we have to run in command prompt.
- Java is a command and tool which is used to run jvm so java means jvm.

---

## Modifiers

**What are modifiers?**
- Modifiers are keywords.

**Examples:** public, private, protected, default, static, final, abstract, native, synchronized, transient, volatile, strictfp

### Types of Modifiers

1. **Access modifiers**
   - public, private, protected, default

2. **Non-access modifiers**
   - static, final, abstract, strictfp, transient, volatile, native, synchronized

**Scope:** Means accessibility and visibility

- Access modifiers are used to specify the scope of classes, interfaces, methods and variables.
- Non-access modifiers are used to provide some functionality.

**Example:**
```java
public class One
{
   private int i = 10;
   public int j = 20;

   private void m1() {
   }

   public void m2() {
   }
}
```

**Non-Access Modifier Examples:**

```java
// Example 1: final (constant variable)
final int a = 10;
a = 20;   //c.e (compile error)

// Example 2: static method
class One
{
   public static void m1() {   //static method
   }
}

One.m1();   // Can call without creating object
```

**Notes:**
- In java, to call a method of a class object is required.
  ```java
  One obj = new One();
  obj.m1();
  ```
- If we want to call the method of a class without creating the object we should declare the method as static which is a non-access modifier.
- To call the static method object is not required, we can call static method by using Classname directly.
- Execution of a java program starts from main method so jvm calls main method.

### public static void main(String args[])

**public :**
- public is an access modifier.
- jvm calls main method so main method must be accessible and visible to jvm that's why main method is public.

**static :**
- static is a non-access modifier.
- jvm calls main method without creating the object that is by using the classname internally that's why main method is static.

**void :**
- void is a keyword and return type of main method which indicates main method will not return any value.

**main() :**
- It is the name of the main method from where the execution of a java program starts.

**String args[] :**
- Main method has 1 parameter whose name is args, whose type is String[] and main method uses args parameter to receive command line arguments.

**Note:** jvm always looks for main method signature as `public static void main(String[] args)`

---
