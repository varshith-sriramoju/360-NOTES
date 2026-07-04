# IO Streams
![My project screenshot](./images/IO-STREAMS.png)


- Sun Microsystems provided predefined classes to write Java programs that read data from a resource or write data to a resource.
- Such predefined classes are called IO streams.
- IO streams are predefined classes in the API.

## Resource

- A resource can be a file, keyboard, console, array, object, or network computer.

## What Is a Stream?

- A stream is a logical connection between the Java program and a resource.
- It is used to transfer data.
- Transferring data means either reading or writing data.

## Types of Streams

There are 2 types of streams:

1. Byte streams (binary streams)
2. Character streams

- Byte streams are used to transfer bytes or binary data.
- Character streams are used to transfer characters.

## Byte Streams vs Character Streams

| Byte Streams | Character Streams |
|---|---|
| Used to transfer binary or byte data | Used to transfer characters |
| Transfer data byte by byte | Transfer data character by character |
| Transfer 8 bits at a time | Transfer 16 bits at a time |
| Suitable for multimedia such as image, video, and audio | Suitable for text or characters |
| Not suitable for universal characters | Suitable for universal characters |
| Available from JDK 1.0 onwards | Available from JDK 1.1 onwards |

## Byte Stream Classes

- For reading binary or byte data, a separate stream is needed.
- For writing binary or byte data, a separate stream is needed.
- So byte streams are divided into 2 types:

1. `InputStream`
2. `OutputStream`

- `InputStream` is a byte stream used for reading binary or byte data.
- `OutputStream` is a byte stream used for writing binary or byte data.

## Character Stream Classes

- For reading characters, a separate stream is needed.
- For writing characters, a separate stream is needed.
- So character streams are divided into 2 types:

1. `Reader`
2. `Writer`

- `Reader` is a character stream used for reading characters.
- `Writer` is a character stream used for writing characters.

## Stream Classes

- In Java, everything is represented as class and object, so all streams are classes.
- A stream is a class whose object acts as a logical connection between the Java program and a resource.
- `InputStream`, `OutputStream`, `Reader`, and `Writer` are abstract classes available in the `java.io` package.
- The JVM cannot create an object of an abstract class because an abstract class is incomplete.
- We cannot create an object of an abstract class, but we can create an object of its subclass.
- For every source resource, Sun Microsystems created one subclass for `InputStream` and `Reader`.
- For every destination resource, Sun Microsystems created one subclass for `OutputStream` and `Writer`.

---

## Standard Streams

- **Standard input stream** is a subclass of `InputStream` and represents the keyboard.
- Sun Microsystems already created a standard input stream object named `in` and placed it in the `System` class as a static variable.

`System.in` -> standard input stream (keyboard)

- **Standard output stream** is a subclass of `OutputStream` and represents the console.
- Sun Microsystems already created a standard output stream object named `out` and placed it in the `System` class as a static variable.

`System.out` -> standard output stream (console)

## InputStreamReader

- It is a subclass of `Reader` and a character stream.
- It is a bridge between byte streams and character streams.
- `InputStreamReader` reads binary data and converts it into characters by using character encoding.

```java
InputStreamReader isr = new InputStreamReader(System.in);
```

- `InputStreamReader` reads one character at a time, which takes time and affects performance.
- Byte streams also transfer one byte at a time, which affects performance.
- To improve byte stream performance, Sun Microsystems provided `BufferedInputStream` and `BufferedOutputStream`.
- To improve character stream performance, Sun Microsystems provided `BufferedReader` and `BufferedWriter`.
- `BufferedReader`, `BufferedWriter`, `BufferedInputStream`, and `BufferedOutputStream` are buffered classes used to improve performance by buffering characters or bytes.

## BufferedReader

- It is a character stream.
- It is used to improve the performance of character streams.
- `BufferedReader` uses a buffer for buffering characters and can read multiple characters.

```java
InputStreamReader isr = new InputStreamReader(System.in);
BufferedReader br = new BufferedReader(isr);
```

or

```java
BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
```

## String to Primitive Conversion

Note: If one variable is a primitive datatype and another variable is a user-defined datatype, then we cannot use the type cast operator.

### Question

How do we convert a string into a primitive datatype?

### Answer

In Java, to convert a string into a primitive datatype, we use parse methods.

- `parseInt()`
- `parseFloat()`
- `parseBoolean()`
- `parseDouble()`

- All parse methods are static methods available in wrapper classes.
- A wrapper class is used to convert a primitive value into an object.
- For every primitive datatype, Sun Microsystems provided one wrapper class.
- All wrapper classes are available in the `java.lang` package.

## Primitive Datatypes and Wrapper Classes

| Primitive Datatype | Wrapper Class |
|---|---|
| byte | Byte |
| short | Short |
| int | Integer |
| long | Long |
| float | Float |
| double | Double |
| char | Character |
| boolean | Boolean |

## Parse Methods

- `Integer`
	- `public static int parseInt(String s)`
- `Float`
	- `public static float parseFloat(String s)`
- `Boolean`
	- `public static boolean parseBoolean(String s)`

### Examples

```java
String s1 = "10";
int i = Integer.parseInt(s1);
```

```java
String s2 = "2.5";
float f = Float.parseFloat(s2);
```

```java
String s3 = "true";
boolean b = Boolean.parseBoolean(s3);
```

## Initialization

- Assigning or storing a value to a variable is called initialization.

## Types of Initialization

There are 2 types of initialization:

1. Compile-time initialization
2. Runtime initialization

### Compile-Time Initialization

- Assigning or storing the value to the variable at the time of writing the program before compilation is called compile-time initialization.

### Runtime Initialization

- Assigning or storing the value to the variable at the time of running the program is called runtime initialization.

---

# Scanner

- `Scanner` is a class available in the `java.util` package.
- It is used to read user input from the keyboard at runtime.
- Using `Scanner`, we can read character, string, and primitive values.

## Methods of Scanner Class

1. `String next()`
2. `String nextLine()`
3. `int nextInt()`
4. `float nextFloat()`
5. `double nextDouble()`
6. `boolean nextBoolean()`
7. `byte nextByte()`
8. `short nextShort()`
9. `long nextLong()`
10. `void close()`

### Example

```java
Scanner sc = new Scanner(System.in);
```
