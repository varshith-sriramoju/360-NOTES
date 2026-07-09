# String

- `String` is a class available in the `java.lang` package.
- `String` is used to represent a sequence of characters.
- Every string literal is an object of `String` class.
- `String` objects are immutable.

```java
String s = "java";
```

## Ways to Create String

### Using String Literal

```java
String s1 = "hyderabad";
```

- String literals are stored in String Constant Pool.

### Using `new` Operator

```java
String s2 = new String("bangalore");
```

- When we create a string using `new`, object is created in heap memory.

### Using Character Array

```java
char ch[] = {'c', 'h', 'e', 'n', 'n', 'a', 'i'};
String s3 = new String(ch);
```

![Ways of Creating String](../images/ways-of-creating-string.png)

## String Constant Pool

- String Constant Pool is a special memory area inside heap memory.
- It stores string literals.
- If the same string literal is created again, JVM reuses the existing object from the pool.

```java
String s1 = "java";
String s2 = "java";

System.out.println(s1 == s2);      // true
System.out.println(s1.equals(s2)); // true
```

![String Constant Pool](../images/scp.png)

## Literal vs `new`

```java
String s1 = "java";
String s2 = new String("java");

System.out.println(s1 == s2);      // false
System.out.println(s1.equals(s2)); // true
```

### Notes

1. `==` compares references.
2. `equals()` compares content.
3. String literals are stored in String Constant Pool.
4. Strings created using `new` are stored in heap memory.

## Immutability

- Mutable means changeable.
- Immutable means not changeable.
- `String` is immutable, so once a `String` object is created, its content cannot be changed.

```java
String s = "java";
s.concat(" language");

System.out.println(s);   // java
```

```java
String s = "java";
s = s.concat(" language");

System.out.println(s);   // java language
```

### Why String Is Immutable

1. To improve security.
2. To support String Constant Pool.
3. To make strings thread-safe.
4. To make hash code caching possible.
5. To improve performance in collections like `HashMap`.

## Important Constructors

```java
String s1 = new String();
String s2 = new String("java");
String s3 = new String(new char[]{'j', 'a', 'v', 'a'});
String s4 = new String(new byte[]{65, 66, 67});
```

## Important String Methods

| Method | Description |
|---|---|
| `length()` | Returns number of characters. |
| `charAt(index)` | Returns character at given index. |
| `substring(begin)` | Returns substring from begin index. |
| `substring(begin, end)` | Returns substring from begin index to end - 1. |
| `equals(str)` | Compares content with case. |
| `equalsIgnoreCase(str)` | Compares content without case. |
| `compareTo(str)` | Compares strings lexicographically. |
| `contains(str)` | Checks whether string contains given sequence. |
| `startsWith(str)` | Checks starting text. |
| `endsWith(str)` | Checks ending text. |
| `indexOf(ch)` | Returns first index of character. |
| `lastIndexOf(ch)` | Returns last index of character. |
| `toLowerCase()` | Converts to lowercase. |
| `toUpperCase()` | Converts to uppercase. |
| `trim()` | Removes leading and trailing spaces. |
| `replace(old, new)` | Replaces characters or strings. |
| `split(regex)` | Splits string based on regex. |
| `toCharArray()` | Converts string to character array. |
| `isEmpty()` | Checks length is zero. |
| `isBlank()` | Checks empty or only spaces. |

```java
String s = " Java Programming ";

System.out.println(s.length());
System.out.println(s.charAt(1));
System.out.println(s.trim());
System.out.println(s.toUpperCase());
System.out.println(s.contains("Java"));
```

## `length()` vs `length`

```java
String s = "java";
int arr[] = {10, 20, 30};

System.out.println(s.length());  // String method
System.out.println(arr.length);  // Array variable
```

## `equals()` vs `equalsIgnoreCase()`

```java
String s1 = "Java";
String s2 = "java";

System.out.println(s1.equals(s2));           // false
System.out.println(s1.equalsIgnoreCase(s2)); // true
```

## `compareTo()`

- `compareTo()` compares two strings lexicographically.

```java
String s1 = "apple";
String s2 = "banana";

System.out.println(s1.compareTo(s2)); // negative value
```

### Return Values

1. Negative value: first string is smaller.
2. Zero: both strings are equal.
3. Positive value: first string is greater.

## `substring()`

```java
String s = "programming";

System.out.println(s.substring(3));    // gramming
System.out.println(s.substring(0, 7)); // program
```

### Note

- In `substring(begin, end)`, begin index is included and end index is excluded.

## `split()`

```java
String s = "apple,banana,mango";
String fruits[] = s.split(",");

for (String fruit : fruits) {
	System.out.println(fruit);
}
```

## Convert String to Character Array

```java
String s = "java";
char ch[] = s.toCharArray();

for (char c : ch) {
	System.out.println(c);
}
```

## Convert Other Types to String

```java
int a = 10;
double d = 12.5;

String s1 = String.valueOf(a);
String s2 = String.valueOf(d);
```

## Convert String to Number

```java
String s1 = "10";
String s2 = "12.5";

int a = Integer.parseInt(s1);
double d = Double.parseDouble(s2);
```

### Note

- If the string does not contain a valid number, we get `NumberFormatException`.

## Common String Exceptions

### `StringIndexOutOfBoundsException`

```java
String s = "java";

System.out.println(s.charAt(4));      // runtime exception
System.out.println(s.substring(2, 6)); // runtime exception
```

### `NullPointerException`

```java
String s = null;

System.out.println(s.length()); // runtime exception
```

### `NumberFormatException`

```java
String s = "10a";

int n = Integer.parseInt(s); // runtime exception
```

## String Concatenation

```java
String s1 = "java";
String s2 = "language";

System.out.println(s1 + " " + s2);
System.out.println(s1.concat(s2));
```

### Notes

1. `+` operator can concatenate strings.
2. `concat()` joins one string at the end of another string.
3. If one operand is a string, `+` converts the other operand into string.

```java
System.out.println(10 + 20 + "java"); // 30java
System.out.println("java" + 10 + 20); // java1020
```

## String Interning

- `intern()` returns the string from String Constant Pool.
- If the string is not available in the pool, it adds the string to the pool and returns it.

```java
String s1 = new String("java");
String s2 = s1.intern();
String s3 = "java";

System.out.println(s2 == s3); // true
```

## StringBuffer and StringBuilder

- `StringBuffer` and `StringBuilder` are mutable character sequence classes.
- Use them when many string modifications are required.

| Feature | StringBuffer | StringBuilder |
|---|---|---|
| Mutability | Mutable | Mutable |
| Synchronization | Synchronized | Not synchronized |
| Thread-safety | Thread-safe | Not thread-safe |
| Performance | Slower | Faster |
| Introduced | JDK 1.0 | JDK 1.5 |

### When to Use

1. Use `String` when content changes rarely.
2. Use `StringBuffer` in multithreaded environment.
3. Use `StringBuilder` in single-threaded environment.

```java
StringBuilder sb = new StringBuilder("java");
sb.append(" language");

System.out.println(sb); // java language
```

## Reverse a String

### Using Loop

```java
public static String reverse(String s)
{
	String result = "";

	for (int i = s.length() - 1; i >= 0; i--) {
		result = result + s.charAt(i);
	}

	return result;
}
```

### Using `StringBuilder`

```java
public static String reverse(String s)
{
	return new StringBuilder(s).reverse().toString();
}
```

## Check Palindrome String

```java
public static boolean isPalindrome(String s)
{
	int left = 0;
	int right = s.length() - 1;

	while (left < right) {
		if (s.charAt(left) != s.charAt(right)) {
			return false;
		}
		left++;
		right--;
	}

	return true;
}
```

## Count Vowels

```java
public static int countVowels(String s)
{
	int count = 0;
	s = s.toLowerCase();

	for (int i = 0; i < s.length(); i++) {
		char ch = s.charAt(i);

		if (ch == 'a' || ch == 'e' || ch == 'i' || ch == 'o' || ch == 'u') {
			count++;
		}
	}

	return count;
}
```

## Count Character Frequency

```java
public static void printFrequency(String s)
{
	int freq[] = new int[256];

	for (int i = 0; i < s.length(); i++) {
		freq[s.charAt(i)]++;
	}

	for (int i = 0; i < freq.length; i++) {
		if (freq[i] > 0) {
			System.out.println((char)i + " = " + freq[i]);
		}
	}
}
```

## Find First Non-Repeating Character

```java
public static char firstNonRepeatingChar(String s)
{
	int freq[] = new int[256];

	for (int i = 0; i < s.length(); i++) {
		freq[s.charAt(i)]++;
	}

	for (int i = 0; i < s.length(); i++) {
		if (freq[s.charAt(i)] == 1) {
			return s.charAt(i);
		}
	}

	return '\0';
}
```

## Check Anagram

- Two strings are anagrams if both contain the same characters with the same frequency.

```java
import java.util.Arrays;

public static boolean isAnagram(String s1, String s2)
{
	if (s1.length() != s2.length()) {
		return false;
	}

	char a[] = s1.toCharArray();
	char b[] = s2.toCharArray();

	Arrays.sort(a);
	Arrays.sort(b);

	return Arrays.equals(a, b);
}
```

## Check Pangram

- A pangram is a sentence containing every alphabet at least once.

```java
public static boolean isPangram(String s)
{
	boolean seen[] = new boolean[26];
	s = s.toLowerCase();

	for (int i = 0; i < s.length(); i++) {
		char ch = s.charAt(i);

		if (ch >= 'a' && ch <= 'z') {
			seen[ch - 'a'] = true;
		}
	}

	for (boolean value : seen) {
		if (!value) {
			return false;
		}
	}

	return true;
}
```

## Remove Spaces

```java
String s = "java is easy";
String result = s.replace(" ", "");

System.out.println(result); // javaiseasy
```

## Remove Duplicate Characters

```java
public static String removeDuplicates(String s)
{
	StringBuilder result = new StringBuilder();
	boolean seen[] = new boolean[256];

	for (int i = 0; i < s.length(); i++) {
		char ch = s.charAt(i);

		if (!seen[ch]) {
			result.append(ch);
			seen[ch] = true;
		}
	}

	return result.toString();
}
```

## Check Only Digits

```java
public static boolean isOnlyDigits(String s)
{
	for (int i = 0; i < s.length(); i++) {
		if (!Character.isDigit(s.charAt(i))) {
			return false;
		}
	}

	return true;
}
```

## Count Words

```java
public static int countWords(String s)
{
	s = s.trim();

	if (s.isEmpty()) {
		return 0;
	}

	String words[] = s.split("\\s+");
	return words.length;
}
```

## Find File Extension

```java
public static String getExtension(String fileName)
{
	int index = fileName.lastIndexOf('.');

	if (index == -1) {
		return "";
	}

	return fileName.substring(index);
}
```

## Longest Word in a Sentence

```java
public static String longestWord(String sentence)
{
	String words[] = sentence.split("\\s+");
	String longest = "";

	for (String word : words) {
		if (word.length() > longest.length()) {
			longest = word;
		}
	}

	return longest;
}
```

## Common Time Complexities

| Operation | Time Complexity |
|---|---|
| `length()` | `O(1)` |
| `charAt(index)` | `O(1)` |
| Traverse string | `O(n)` |
| `equals()` | `O(n)` |
| `compareTo()` | `O(n)` |
| `substring()` | `O(n)` |
| `toLowerCase()` / `toUpperCase()` | `O(n)` |
| String concatenation in loop | `O(n^2)` |
| `StringBuilder append()` in loop | `O(n)` |

## Common Interview Points

1. `String` is immutable.
2. String literals are stored in String Constant Pool.
3. `new String("java")` creates a separate object in heap.
4. Use `equals()` for content comparison.
5. Use `==` only for reference comparison.
6. `StringBuffer` is synchronized and thread-safe.
7. `StringBuilder` is not synchronized and faster.
8. Use `StringBuilder` for repeated string modifications.
9. `String` overrides `equals()` and `hashCode()`.
10. `substring(begin, end)` excludes end index.
11. `split()` accepts regex.
12. `String` objects can be used safely as `HashMap` keys because they are immutable.

## Coding Assessment Patterns on Strings

1. Traversal
2. Reversal
3. Palindrome
4. Character frequency
5. First non-repeating character
6. Anagram
7. Pangram
8. Substring
9. Word count
10. Remove duplicates
11. Remove spaces
12. Check digits or alphabets
13. Longest word
14. File extension
15. String compression

## Programs on Strings

1. Write a Java program to reverse a string.
2. Write a Java program to check whether a string is palindrome.
3. Write a Java program to count vowels in a string.
4. Write a Java program to count consonants in a string.
5. Write a Java program to count words in a string.
6. Write a Java program to count frequency of each character.
7. Write a Java program to find first non-repeating character.
8. Write a Java program to check whether two strings are anagrams.
9. Write a Java program to check whether a string is pangram.
10. Write a Java program to remove duplicate characters.
11. Write a Java program to remove spaces from a string.
12. Write a Java program to check whether a string contains only digits.
13. Write a Java program to find longest word in a sentence.
14. Write a Java program to get file extension.
15. Write a Java program to compare two strings without using `equals()`.
16. Write a Java program to count uppercase and lowercase characters.
17. Write a Java program to replace each space with `%20`.
18. Write a Java program to compress a string.
