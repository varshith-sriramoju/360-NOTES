## Garbage Collector

- Garbage collector is a program available inside the JVM and is responsible for performing garbage collection automatically.

### Garbage Collection

- Garbage collection is a process of removing or destroying the objects that are not in use from JVM's heap area when the JVM is running.

### Eligibility for Garbage Collection

- If an object does not have an external reference, then it is not in use and is eligible for garbage collection.
- If an object has an external reference, then it is in use and is not eligible for garbage collection.
- To make an object eligible for garbage collection, assign the reference variable to `null`.

### Garbage Collector Execution

- Garbage collector runs automatically at periodic intervals.
- If garbage collector has to run, the JVM must run first.
- If `main()` execution is started, the JVM is running.
- If `main()` execution is completed, the JVM shuts down.

### Guarantee of Garbage Collector

- If the JVM completes the execution of `main()` before the periodic time of the garbage collector, then the JVM shuts down and garbage collector will not run.
- If garbage collector does not run, then `finalize()` will not be called.

### Forcing Garbage Collection

- If we want to run garbage collector before the periodic time and before JVM shutdown, we can use `System.gc()`.

```java
java.lang
|- System
	|- public static void gc(): it runs garbage collector.
```

### Notes

1. If constructor is called, the object is created. If `finalize()` is called, the object is destroyed or removed.
2. Cleanup activities include closing a stream and assigning a reference to `null`.
3. Constructor is called only once after an object is created.
4. `finalize()` is called only once before an object is destroyed or removed.
