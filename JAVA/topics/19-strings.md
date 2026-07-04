# String

String is a class in the `java.lang` package used to represent a sequence of characters.

## String literals and creation

- A string literal is a sequence of characters enclosed in double quotes. Every string literal is an instance of `String`.
- Example: `"hyderabad"`

Ways to create a `String`:

- Using a literal:

```java
String s1 = "hyderabad";
```

- Using the `new` operator:

```java
String s2 = new String("bangalore");
```

- From a character array:

```java
char[] ch = {'c','h','e','n','n','a','i'};
String s3 = new String(ch);
```

# String

String is a class in the `java.lang` package used to represent a sequence of characters.

## String literals and creation

- A string literal is a sequence of characters enclosed in double quotes. Every string literal is an instance of `String`.
- Example: `"hyderabad"`

Ways to create a `String`:

- Using a literal:

```java
String s1 = "hyderabad";
```

- Using the `new` operator:

```java
String s2 = new String("bangalore");
```

- From a character array:

```java
char[] ch = {'c','h','e','n','n','a','i'};
String s3 = new String(ch);
```

![Ways of Creating String](./images/ways-of-creating-string.png)

After creation, string operations use `String` methods. Note that `String` is immutable â€” any modification creates a new `String` object.

## Mutability

- mutable: can be changed or modified
- immutable: cannot be changed or modified

To work with mutable character sequences, Java provides `StringBuffer` and `StringBuilder`.

## Common string programs (examples)

1. Find repeated characters in a string
2. Count number of vowels in a string
3. Get the file extension
4. Check if a string is a pangram
5. Check whether a string is a palindrome

Sample I/O examples:

```
Enter a string : malayalam
Enter a character : a
'a' is repeated 4 times

Enter a string : education
Number of vowels : 5

Enter file name : tiger.jpg
File extension : .jpg

Enter a string : a quick brown fox jumps over the lazy dog
Output: given string is pangram
```

## String comparison and SCP

- Comparing two strings should compare their contents, not references â€” use `equals()`.
- The JVM maintains a String Constant Pool (SCP) where string literals are interned.

![String Constant Pool](./images/scp.png)

## StringBuffer vs StringBuilder

| Feature | StringBuffer | StringBuilder |
|---:|:---|:---|
| Synchronization | synchronized (thread-safe) | not synchronized (not thread-safe) |
| Performance | lower | higher |
| Since JDK | 1.0 | 1.5 |

Example program using `StringBuffer` (reverse characters):

```java
// input: computer
// output: r-e-t-u-p-m-o-c
StringBuffer sb = new StringBuffer("computer");
sb.reverse();
String result = sb.toString();
```

---
