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

## `wait()`

- `wait()` is used to make the current thread wait until another thread calls `notify()` or `notifyAll()` on the same object.
- `wait()` is available in Object class because every object in Java can act as a lock.

```java
public final void wait() throws InterruptedException
```

### Notes

1. `wait()` must be called from a synchronized method or synchronized block.
2. If we call `wait()` without getting the object lock, we get `IllegalMonitorStateException`.
3. When a thread calls `wait()`, it releases the lock of that object.
4. The waiting thread moves into the waiting state.
5. The waiting thread comes out of waiting state when another thread calls `notify()` or `notifyAll()` on the same object.
6. `wait()` throws `InterruptedException`, so we must handle it using `try-catch` or declare it using `throws`.

```java
class Shared
{
	public synchronized void methodOne()
	{
		try
		{
			wait();
		}
		catch (InterruptedException e)
		{
			e.printStackTrace();
		}
	}
}
```

## `wait(long)`

- `wait(long)` is used to make the current thread wait for the given amount of time or until another thread calls `notify()` or `notifyAll()`.

```java
public final void wait(long milliseconds) throws InterruptedException
```

### Notes

1. The time is given in milliseconds.
2. `wait(1000)` means the current thread waits up to 1 second.
3. The thread can come out of waiting state before the given time if another thread calls `notify()` or `notifyAll()`.
4. Like `wait()`, `wait(long)` must also be called from a synchronized method or synchronized block.

```java
class Shared
{
	public synchronized void methodOne()
	{
		try
		{
			wait(1000);
		}
		catch (InterruptedException e)
		{
			e.printStackTrace();
		}
	}
}
```

## `wait(long, int)`

- `wait(long, int)` is used to make the current thread wait for the given milliseconds and nanoseconds or until another thread calls `notify()` or `notifyAll()`.

```java
public final void wait(long milliseconds, int nanoseconds) throws InterruptedException
```

### Notes

1. The first argument represents milliseconds.
2. The second argument represents nanoseconds.
3. Nanoseconds must be in the range `0` to `999999`.
4. If nanoseconds are outside this range, we get `IllegalArgumentException`.
5. Like other `wait()` methods, this method must also be called from a synchronized method or synchronized block.

```java
class Shared
{
	public synchronized void methodOne()
	{
		try
		{
			wait(1000, 500);
		}
		catch (InterruptedException e)
		{
			e.printStackTrace();
		}
	}
}
```

## `notify()`

- `notify()` is used to wake up one waiting thread that is waiting on the same object.

```java
public final void notify()
```

### Notes

1. `notify()` must be called from a synchronized method or synchronized block.
2. If we call `notify()` without getting the object lock, we get `IllegalMonitorStateException`.
3. `notify()` wakes up only one waiting thread.
4. If multiple threads are waiting on the same object, the JVM decides which thread should be notified.
5. The notified thread does not execute immediately. It has to wait until the current thread releases the object lock.

```java
class Shared
{
	public synchronized void methodOne()
	{
		notify();
	}
}
```

## `notifyAll()`

- `notifyAll()` is used to wake up all waiting threads that are waiting on the same object.

```java
public final void notifyAll()
```

### Notes

1. `notifyAll()` must be called from a synchronized method or synchronized block.
2. If we call `notifyAll()` without getting the object lock, we get `IllegalMonitorStateException`.
3. `notifyAll()` wakes up all waiting threads on the same object.
4. Even though all waiting threads are notified, only one thread can get the object lock at a time.
5. Remaining notified threads wait until the lock becomes available.

```java
class Shared
{
	public synchronized void methodOne()
	{
		notifyAll();
	}
}
```

## Difference Between `notify()` and `notifyAll()`

| Method | Description |
|---|---|
| `notify()` | Wakes up only one waiting thread. |
| `notifyAll()` | Wakes up all waiting threads. |

## Example

```java
class Shared
{
	public synchronized void waitMethod()
	{
		try
		{
			System.out.println("Thread is waiting");
			wait();
			System.out.println("Thread got notification");
		}
		catch (InterruptedException e)
		{
			e.printStackTrace();
		}
	}

	public synchronized void notifyMethod()
	{
		System.out.println("Thread is sending notification");
		notify();
	}
}

public class Test
{
	public static void main(String[] args)
	{
		Shared s = new Shared();

		Thread t1 = new Thread()
		{
			public void run()
			{
				s.waitMethod();
			}
		};

		Thread t2 = new Thread()
		{
			public void run()
			{
				s.notifyMethod();
			}
		};

		t1.start();
		t2.start();
	}
}
```
