# File IO

Sun Microsystems has developed and provided some predefined classes using which we write Java programs either to read data from a file or to write data to a file. Such predefined classes are called **File IO**.

## File IO Classes

1. `File`
2. `FileReader`
3. `FileWriter`
4. `BufferedReader`
5. `BufferedWriter`
6. `PrintWriter`

All these classes are available in the `java.io` package.

## File

`File` is a class available in the `java.io` package.

A `File` class object represents file and directory pathnames.

```text
d:
|- temp
   |- abc.txt
```

```text
d:\temp         -> directory pathname
d:\temp\abc.txt -> file pathname
```

### Program

Write a Java program to create a directory and inside the directory create a file.

```text
notes
|- core-java.txt
```

### Program

Write a Java program to display all the names of subdirectories and files.

```text
stories
|- horror
|- comedy
|- action
|- harry-potter.txt
|- jungle-book.txt
|- rabbit-tortoise.txt
|- the-lion-king.txt
```

## FileReader

`FileReader` is a class and character stream available in the `java.io` package.

`FileReader` reads characters from a file character by character.

```java
FileReader fr = new FileReader("abc.txt");
```

or

```java
FileReader fr = new FileReader(new File("abc.txt"));
```

### Note

`FileReader` is a character stream which reads one character at a time. This takes time and impacts performance. To improve the performance of `FileReader`, we have to use `BufferedReader`.

## BufferedReader

`BufferedReader` is a class available in the `java.io` package.

`BufferedReader` is a character stream and it is used to improve the performance of character streams by buffering the characters.

```java
FileReader fr = new FileReader("abc.txt");
BufferedReader br = new BufferedReader(fr);
```

## FileWriter

`FileWriter` is a class and character stream available in the `java.io` package.

`FileWriter` writes characters to the file character by character.

```java
FileWriter fw = new FileWriter("abc.txt");
```

### Methods of FileWriter

1. `public void write(char ch)`
2. `public void write(char[] ch)`
3. `public void write(String str)`
4. `public void close()`

### Note

`FileWriter` writes one character to the file at a time. This takes time and impacts performance. To improve the performance of `FileWriter`, we have to use `BufferedWriter`.

## BufferedWriter

`BufferedWriter` is a class available in the `java.io` package.

`BufferedWriter` is a character stream and it is used to improve the performance of character streams by buffering the characters.

```java
FileWriter fw = new FileWriter("xyz.txt");
BufferedWriter bw = new BufferedWriter(fw);
```

## PrintWriter

`PrintWriter` is a class available in the `java.io` package.

`PrintWriter` is a character stream and it writes characters and primitive values.

```java
PrintWriter pw = new PrintWriter("test.txt");
```

### Methods of PrintWriter

1. `public void println(String s)`
2. `public void println(char ch)`
3. `public void println(int i)`
4. `public void println(float f)`
5. `public void println(double d)`
6. `public void println(boolean b)`

---

# Serialization and Deserialization

## What is Serialization?

The process of converting the state of an object into binary is called **serialization**.

or

The process of converting Java-supported format into network-supported format is called **serialization**.

```text
java.io
|- ObjectOutputStream
   |- public void writeObject(Object o)
```

In the program, after serialization we are going to write binary to a file. To write binary to a file, we have to use `FileOutputStream`.

## What is Deserialization?

The process of converting binary into an object is called **deserialization**.

or

The process of converting network-supported format into Java-supported format is called **deserialization**.

```text
java.io
|- ObjectInputStream
   |- public Object readObject()
```

In the program, before deserialization we have to read the binary from a file. To read binary from a file, we have to use `FileInputStream`.

### Note

In deserialization, a new object is created but constructor will not be called.

## transient

`transient` is a keyword and a modifier which is allowed only for variables except local variables.

By default, all the state of an object will participate in serialization and deserialization. If we do not want any state to participate in serialization and deserialization, then we have to declare the state by using the `transient` keyword.

If we declare any state by using the `transient` keyword, then the state will not participate in serialization and deserialization.

Because of some security reasons, we do not want some state to participate in serialization and deserialization. That is why we have to declare the state by using `transient`.

### Comparisons

- `transient` vs `final`
- `transient` vs `static`

---
