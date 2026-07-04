# java.lang Package

1. Object
2. String
3. StringBuffer
4. StringBuilder

## Object

- Object is a class available in the `java.lang` package.
- Object is the root class in the class hierarchy.
- Every class has Object as a superclass.
- Since Object is the superclass for every class in Java, every class is an Object type.
- Using an Object class reference variable, we can hold any class object.
- There are 11 methods available in the Object class, and all 11 methods are inherited and available in every class.

### Methods of Object Class

1. `toString()`
2. `getClass()`
3. `clone()`
4. `hashCode()`
5. `equals()`
6. `finalize()`
7. `wait()`
8. `wait(long)`
9. `wait(long, int)`
10. `notify()`
11. `notifyAll()`

## `toString()`

- It returns a string representation of the object.

```java
public String toString()
```

### Notes

1. If we display or print an object, the JVM automatically calls `toString()` on the object.
2. If we do not override Object class `toString()` in the subclass and if we display a subclass object, the JVM calls Object class `toString()`, which returns a string consisting of the class name, `@`, and the hexadecimal representation of the object's hash code.

```text
ClassName + "@" + hexadecimalNumber
```

### Method Overriding

- Overriding a superclass method in a subclass with a different implementation is called method overriding.
- The superclass method is called the overridden method.
- The subclass method is called the overriding method.
- In method overriding, the same method is available in both superclass and subclass, but with different implementation.

```java
class Parents
{
	public void property()
	{
		System.out.println("houses, flats, plots, cars, gold, silver etc");
	}

	public void study()   // overridden method
	{
		System.out.println("m.b.a");
	}
}

class Son extends Parents
{
	public void study()   // overriding method
	{
		System.out.println("engineering");
	}
}

public class Test
{
	public static void main(String[] args)
	{
		Son s = new Son();
		s.property();
		s.study();  // subclass overriding method will be called
	}
}
```

## `getClass()`

- Before creating an object, the JVM creates a `Class` object to store the information of the loaded class, so `getClass()` returns this `Class` object.

```java
public final Class getClass()
```

- In the `Class` class, which is a subclass of Object class, Sun Microsystems has overridden `toString()` to return a string consisting of the `class` keyword, a space, and the `ClassName`.

```text
java.lang
|- Class
	|- String getName(): it returns the name of the class whose information is available in the Class object as a string.
```

- A `Class` object stores the information of another class.
- Information of another class means class name, superclass name, variable names, method names, and constructor names.

## `clone()`

- `clone()` creates and returns a copy of the object.
- In other words, `clone()` is used for object cloning.

```java
protected Object clone() throws CloneNotSupportedException
```

### What Is Object Cloning?

- Creating the exact copy of an object is called object cloning.

### Notes

1. `clone()` creates a new object without calling a constructor.
2. If we use the `new` operator or `newInstance()` factory method to create an object, then the constructor is called.

### Protected Method Note

- Superclass protected methods are inherited in a subclass and become private in the subclass.

```java
class One   // super class
{
	protected void methodOne() {
		// addition of two numbers logic
	}
}

class Two extends One   // sub class
{
}

public class Test
{
	public static void main(String[] args)
	{
		Two t = new Two();
		t.methodOne();  // c.e
	}
}
```

```java
class One      // super class
{
	protected void methodOne() {
		// addition of two numbers logic
	}
}

class Two extends One   // sub class
{
	public void methodOne() {
		super.methodOne();
	}
}

public class Test {
	public static void main(String[] args) {
		Two t = new Two();
		t.methodOne();
	}
}
```

## `hashCode()` and `equals()`

- Object class `hashCode()` returns the object hash code, also called reference number.

```java
public int hashCode()
```

- Object class `equals()` compares object hash codes, which are returned by `hashCode()`.

```java
public boolean equals(Object o)
```

```java
String s1 = new String("sdfsafwerwqreqwertasdasfxcv");  // 1 lakh characters
String s2 = new String("sdfsafwerwqreqwertasdasfxcv");  // 1 lakh characters

System.out.println(s1 == s2);   // false
System.out.println(s1.equals(s2));   // true
```

### Notes

1. If `equals()` compares two strings character by character and each string has 1 lakh characters, then `equals()` has to do 1 lakh comparisons, which takes time and impacts performance. That is why Sun Microsystems provided `hashCode()`, so `equals()` compares hash codes instead of characters.
2. A hash code is an integer number.
3. In Java, the use of `hashCode()` is to generate and return the hash code based on the data present inside the object, and the use of `equals()` is to compare the hash codes generated by `hashCode()`.
4. If 2 objects have the same data, then `hashCode()` generates and returns the same hash codes. If 2 objects have different data, `hashCode()` generates and returns different hash codes.
- In `String` class, which is a subclass of Object class, Sun Microsystems has already overridden `hashCode()` and `equals()` to generate and return hash code based on data.
- Data is not available in Object class, but data is available in subclasses, so Object class `hashCode()` cannot access data and cannot generate hash code based on data.
- If we want Object class `hashCode()` and `equals()` to generate and return hash codes based on data, we must override them in the subclass.
- When we override Object class `hashCode()` and `equals()` in a subclass, `hashCode()` uses data to generate the hash code.

## `finalize()`

- `finalize()` is called by the garbage collector automatically before destroying or removing an object from JVM memory to perform cleanup activities.

```java
protected void finalize()
```

### What Is Object Life Cycle?

- The entire process of object creation until destruction is called object life cycle.
- Managing the birth of an object and managing the death of an object is also called object life cycle.
- After the object is created, initializing the instance variables of an object using constructor is called managing the birth of an object.
- Before the object is destroyed or removed from JVM memory, performing cleanup activities using `finalize()` is called managing the death of an object.
- Object life cycle can be managed by using constructor and `finalize()`.

### Notes

1. Constructor is called immediately after an object is created, and constructor is used to initialize instance variables.
2. `finalize()` is called immediately before an object is destroyed or removed from JVM memory, and `finalize()` is used to perform cleanup activities.
3. JVM calls constructor automatically after an object is created.
4. Garbage collector calls `finalize()` automatically before an object is destroyed or removed from JVM memory.
5. JVM creates objects inside heap area when JVM starts running and removes objects from heap area before JVM shutdown.

