## Packages

### What Is a Package?

- A package is a mechanism of encapsulating or binding related classes, interfaces, and sub-packages together in one place.

### Advantages of Packages

1. A package is used to make class names unique, which resolves naming collision or naming conflict problems.
2. We can control the scope of classes, interfaces, methods, variables, and constructors using packages.

- A package looks similar to a folder in the computer and contains `.class` files.
- If we want to create a class, first we should create the package and then create the class inside it.
- If a class is available inside a package, we cannot use it directly by name; we must use the fully qualified name `package-name.ClassName`.

### Creating a Package

```java
package package-name;
```

- `package` is a Java keyword used to create a package.

### Creating a Subpackage

```java
package package-name.sub-package-name1.sub-package-name2;
```

### Package Naming Convention

```text
com.projectname.module-name.sub-module-name.ClassName
```

### Notes

1. `javac` is a tool and tools take options, which are also called switches.
2. Switches start with a hyphen symbol and provide additional information to a tool.
3. `-d` is a switch that tells the Java compiler to create a package with `.class` file and place it in some directory location.

### Compiling a Class with a Package Statement

```bash
javac -d directory-location ClassName.java

javac -d d:\work One.java
javac -d . One.java
```

- `.` represents the current directory.

### Example Structure

```text
d:
|- work
   |- com.egames.racing
	  |- Game.class
   |- Test.java (Test class is using Game class)
```

## Classpath

- Class means `.class` file.
- Path means location.
- Classpath means `.class` file location.

### What Is Classpath?

- Classpath is an environment variable or system variable used by the compiler and JVM to search for the location of `.class` files.
- Compiler and JVM search for `.class` files in the classpath, and the default classpath is the current directory.
- If `.class` files are not available in the current directory, which is the default classpath, then we have to change or set the classpath.

### Ways of Setting Classpath

1. Command level
2. Command prompt level
3. Operating system level

#### 1. Command Level

- If we set the classpath at command level, it will be available only until the command runs.
- Whenever we run the command, we have to set the classpath.

```bash
javac -cp directory ClassName.java
javac -classpath directory ClassName.java

java -cp directory ClassName
java -classpath directory ClassName
```

#### 2. Command Prompt Level

- If we set the classpath at command prompt level, it will be available until the command prompt is running.
- If we close the command prompt, the classpath will be lost.

```bash
set classpath=directory
```

#### 3. Operating System Level

- If we set the classpath at operating system level, it becomes permanent.

### More Notes

- `javac` and `java` are tools and a tool takes options, which are also called switches.
- Switches start with a hyphen symbol and provide additional information to the tool.
- If we want to set the classpath at command level, we use either `-cp` or `-classpath`.
- If we want to set the classpath at command prompt level, we use the `set` command.

### Dependency Example

```text
c:
|- temp
   |- Game.class

d:
|- work
   |- Test.java (Test class is using Game class)
```

- A `.class` file is called a dependency.
- The compiler searches for one-level dependency, whereas the JVM searches for two-level dependencies.
- For the compiler, we need to set the classpath for one-level dependency, and for the JVM we need to set the classpath for two-level dependencies.

