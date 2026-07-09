# Interfaces

## Meaning

- Any service requirement specification (SRS) is considered an interface.
- From the service provider perspective, an interface defines the features or services being offered.
- From the client perspective, an interface defines the features or services being expected.
- Any contract between two people is called an interface.
- An interface shows only the features or services that are being offered and expected.
- An interface does not show implementation, so it contains only method headers or method prototypes, not method bodies.
- Such methods are called abstract methods, so an interface contains only abstract methods.
- A class which contains only abstract methods is called a 100% incomplete class, and a 100% incomplete class is called an interface.

## What Is an Interface?

- Any service requirement specification, a contract between two people, or a 100% incomplete class is called an interface.

## Creating an Interface

```java
modifier interface InterfaceName {
	// abstract methods
}
```

- In Java, we use the `interface` keyword to create an interface.

### Notes

1. By default, all methods in an interface are `public` and `abstract`.
2. JVM cannot create an object for an interface because an interface is a 100% incomplete class.

## Using an Interface

- If we cannot create an object for an interface, then to use it we create an implementation class using the `implements` keyword.
- In the implementation class, we must override and provide implementation to all abstract methods of the interface.
- If we do not override and implement even one abstract method, the implementation class becomes an abstract class.

## What Is an Implementation Class?

- A class which provides implementation to all the abstract methods of an interface is called an implementation class.
- Implementation means writing the method body.
- If all abstract methods are implemented, the implementation class becomes a concrete class and we can create an object of it.
- To create an implementation class, we use the `implements` keyword.

### More Notes

3. We cannot create an object of an interface, but we can create an object of its implementation class.
4. We can create a reference variable to an interface and use it to hold an implementation class object.
5. Like in inheritance, a subclass is both a subclass type and a superclass type; similarly, in interfaces, an implementation class is both an implementation class type and an interface type.
6. We can write variables inside an interface, and when declaring them we must initialize them.
7. By default, all variables in an interface are `public`, `static`, and `final`.
8. The purpose of writing variables inside an interface is to define static constant variables.
9. Interface variables can be accessed directly in the implementation class and outside it by using the interface name.
10. We cannot write a constructor inside an interface.
11. The only modifiers allowed for methods of an interface are `public` and `abstract`.
12. The only modifiers allowed for variables of an interface are `public`, `static`, and `final`.

---

## Abstraction

- Interface is one of the abstraction mechanisms in Java, which means we can achieve abstraction using interfaces.
- Using an interface, we achieve 100% abstraction.
- If we want to hide the complete implementation, we should use an interface.
- If we want partial abstraction or if we do not want to hide the complete implementation, we should use an abstract class.
- If we want 100% abstraction or if we want to hide the complete implementation, we should use an interface.

---

## Interface Reference Use Cases

1. If a method or a constructor has an interface reference variable as a parameter, then while calling it we must pass an implementation class object.
2. If the return type of a method is an interface, then such a method returns the object of an implementation class as interface type.

## Marker Interfaces

- A interface which contains zero abstract methods is called a marker interface.
- In Java, several predefined marker interfaces are available.

### Examples

- Cloneable
- Serializable
- RandomAccess

### Meaning

- By default, an object of a class does not have some abilities.
- Marker interfaces act as metadata for the JVM, which means using marker interfaces we can give information to add some ability to an object of a class.

### Example

```java
class Employee implements Cloneable {
	int id = 1;
	String name = "john";
	double salary = 1000.0;

	public Object clone() throws CloneNotSupportedException {
		Object o = super.clone();
		return o;
	}
}

public class Test {
	public static void main(String[] args) throws CloneNotSupportedException {
		Employee e1 = new Employee();
		Object o = e1.clone();
		Employee e2 = (Employee) o;

		System.out.println(e1.hashCode());
		System.out.println(e2.hashCode());

		System.out.println("e1 == e2 : " + (e1 == e2));

		System.out.println(e1.id + " - " + e1.name + " - " + e1.salary);
		System.out.println(e2.id + " - " + e2.name + " - " + e2.salary);
	}
}
```

### Syntax

```java
protected Object clone() throws CloneNotSupportedException
```

---

## Lambda Expression

- Lambda expression is a feature added in Java 8.
- Lambda expression is an anonymous function.
- A function which does not have a name is an anonymous function.

### Example Without Lambda

```java
public void methodOne() {
}
```

### Example With Lambda

```java
() -> {
	System.out.println("from methodOne");
};
```

- The `->` arrow symbol represents the lambda expression.
- Lambda expression is based on functional interface, so we can use lambda expressions only with functional interfaces.
- To call a lambda, we need a functional interface.
- Using lambda expression, we can refer to the method of a functional interface.
- If an interface contains only one abstract method, it is called a functional interface.
- If we use lambda expression with an interface that contains more than one abstract method, the compiler gives an error.

### Example

```java
interface One {
	void methodOne();
}

public class Test {
	public static void main(String[] args) {
		One o = () -> {
			System.out.println("from methodOne");
		};

		o.methodOne();
	}
}
```

### Inline Lambda

```java
interface One {
	void methodOne();
}

class Test {
	public static void main(String[] args) {
		One o = () -> System.out.println("from methodOne");

		o.methodOne();
	}
}
```

### Advantages of Lambda Expression

1. Lambda expression provides a clear and concise way of writing code.
2. Lambda expression reduces the length of code.
3. We can achieve functional programming.

## Functional Interface

- An interface which contains only one abstract method is called a functional interface.
- A functional interface can have non-abstract methods also in the form of `static` and `default`.
- An interface which contains only one abstract method and can have non-abstract methods in the form of `static` and `default` is also called a functional interface.
- The only condition is that it must have only one abstract method.
- From Java 8 onwards, we can write non-abstract methods inside interfaces in the form of `static` and `default`.

### Example 1

```java
interface One {
	void methodOne();
}
```

### Example 2

```java
interface One {
	void methodOne();

	static void methodTwo() {
	}

	default void methodThree() {
	}
}

public class Test {
	public static void main(String[] args) {
		One o = () -> System.out.println("from methodOne");

		o.methodOne();
		o.methodThree();

		One.methodTwo();
	}
}
```

### Notes

1. A static method in an interface helps provide security by not allowing the implementation class to override the method.
2. Java 8 introduces a new concept called default method.
3. A method declared using the `default` keyword is called a default method, and it can be written only inside an interface.

### Lambda Parameter Examples

#### Example 1

```java
interface One {
	void methodOne(int a);
}

public class Test {
	public static void main(String[] args) {
		One o = (int a) -> System.out.println(a);

		o.methodOne(10);
	}
}
```

#### Example 2

```java
interface One {
	void methodOne(int a, int b);
}

public class Test {
	public static void main(String[] args) {
		One o = (a, b) -> {
			System.out.println(a);
			System.out.println(b);
		};

		o.methodOne(10, 20);
	}
}
```

#### Example 3

```java
interface One {
	int methodOne(int a, int b);
}

public class Test {
	public static void main(String[] args) {
		One o = (a, b) -> {
			return a + b;
		};

		System.out.println(o.methodOne(10, 20));
	}
}
```

- You can also write this as `One o = (a, b) -> { return a + b; };` or `One o = (a, b) -> a + b;`.
- When the method body has only one statement, braces can be removed.

---

