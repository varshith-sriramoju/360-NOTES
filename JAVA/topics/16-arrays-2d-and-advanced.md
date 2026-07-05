## 2D Array

![2D Arrays](../images/2d-arrays.png)

### Declaration

```java
int a[][];
int [][]a;
int[][] a;
int[] []a;
int []a[];
```

- `int a[3][3];` is invalid in Java.
- At declaration time, array size cannot be specified in Java.
- Declaring a 2D array does not allocate memory.

### Creation

- 2D arrays are implemented in array-of-arrays form.

```java
datatype variableName[][] = new datatype[size-1][size-2];
```

- `size-1` represents the base array size and number of 1D arrays.
- `size-2` represents the size of each 1D array.

### Examples

```java
int a[][] = new int[3][3];
float[][] b = new float[4][3];
char [][]ch = new char[5][4];
String str[][] = new String[3][2];
```

### Initialization

There are 2 ways to initialize a 2D array:

1. Compile-time initialization
   - Single-line initialization
   - Multi-line initialization
2. Runtime initialization

#### Single-Line Initialization

```java
int a[][] = {{1, 2, 3}, {4, 5, 6}, {7, 8, 9}};
double[][] b = {{1.1, 2.2, 3.3}, {4.4, 5.5, 6.6}};
char[][] ch = {{'a', 'b'}, {'c', 'd'}, {'e', 'f'}};
String str[][] = {{"apple", "mango"}, {"orange", "grapes"}};
```

- A 2D array can also be created without using the `new` operator by using single-line initialization.

#### Multi-Line Initialization

```java
int a[][] = new int[3][3];
a[0][0] = 1;
a[0][1] = 2;
a[0][2] = 3;
a[1][0] = 4;
a[1][1] = 5;
a[1][2] = 6;
a[2][0] = 7;
a[2][1] = 8;
a[2][2] = 9;
```

```java
double[][] b = new double[2][2];
b[0][0] = 1.1;
b[0][1] = 2.2;
b[1][0] = 3.3;
b[1][1] = 4.4;
```

```java
String str[][] = new String[2][3];
str[0][0] = "india";
str[0][1] = "china";
str[0][2] = "russia";
str[1][0] = "japan";
str[1][1] = "nepal";
str[1][2] = "france";
```

### Runtime Initialization

```java
Scanner sc = new Scanner(System.in);
int arr[][] = new int[3][3];

for (int i = 0; i < arr.length; i++) {
	for (int j = 0; j < 3; j++) {
		System.out.print("enter arr[" + i + "][" + j + "] = ");
		arr[i][j] = sc.nextInt();
	}
}
```

## Accessing Elements of 2D Array

There are 2 ways to access the elements of a 2D array:

1. Accessing one element using index
2. Accessing all elements using loops

### Accessing One Element Using Index

```java
int arr[][] = {{1, 2, 3}, {4, 5, 6}, {7, 8, 9}};

System.out.println(arr[0][0]);
System.out.println(arr[0][1]);
System.out.println(arr[0][2]);
System.out.println(arr[1][0]);
System.out.println(arr[1][1]);
System.out.println(arr[1][2]);
System.out.println(arr[2][0]);
System.out.println(arr[2][1]);
System.out.println(arr[2][2]);
```

### Accessing All Elements Using Loops

```java
int arr[][] = {{1, 2, 3}, {4, 5, 6}, {7, 8, 9}};

for (int i = 0; i < arr.length; i++) {
	for (int j = 0; j < 3; j++) {
		System.out.print(arr[i][j] + "  ");
	}
	System.out.println();
}
```

## Programs on 2D Array

1. Write a Java program to find the sum of all the elements of a 2D array using runtime initialization.
2. Write a Java program to find the sum of all the odd elements of a 2D array.
3. Write a Java program to find the matrix transpose.

### Matrix Transpose

```text
1  2  3             1  4  7
4  5  6  transpose  2  5  8
7  8  9             3  6  9
```

## Anonymous Array

- In Java, an array without a name is called an anonymous array.
- Since it has no name, it can be used only once.
- Anonymous arrays are used for instant use.

```java
new datatype[]{elements...}
new datatype[][]{{elements...}, {elements...} ...}
```

### Examples

```java
new int[]{1, 2, 3, 4, 5}
new float[]{1.1f, 2.2f, 3.3f}
new char[]{'a', 'b', 'c', 'd', 'e'};
new String[]{"apple", "mango", "orange"}
new int[][]{{1, 2, 3}, {4, 5, 6}, {7, 8, 9}}
```

- If we assign a name to an anonymous array, then it is not anonymous.

```java
int arr[] = new int[]{1, 2, 3, 4, 5};
```

## Ways of Creating Array in Java

1. Using `new` operator

```java
int[] arr = new int[5];
```

2. Using single-line initialization

```java
int[] arr = {1, 2, 3, 4, 5};
```

3. Using anonymous array

```java
new int[]{1, 2, 3, 4, 5}
```

## Command Line Arguments

- The `main` method has a parameter named `args` of type `String[]`.
- The `args` parameter is used to receive command-line arguments.
- The values passed to the `main` method at runtime are called command-line arguments.
- The JVM reads the command-line arguments and passes them to the `main` method.
- The `args` parameter stores the values in an array as `String` type in respective indexes.

```java
public class Test
{
	public static void main(String[] args)
	{
		int n = args.length;
		System.out.println("n = " + n);

		for (int i = 0; i < n; i++) {
			System.out.println("args[" + i + "] = " + args[i]);
		}
	}
}
```

```text
java Test hello 10 2.5
			|   |   |
			|   | args[2]
			|   |
			| args[1]
			|
		  args[0]
```

## Programs on Command Line Arguments

1. Write a Java program to find the sum of two numbers by reading values using command-line arguments.
2. Write a Java program to find the sum of n numbers by reading values using command-line arguments.

## Var-Args (Variable Length Arguments)

- Var-args was introduced in JDK 1.5.
- If we want to change the number of parameters of a method, we would normally need to change the method signature or write another method.
- To solve this problem, Sun Microsystems introduced var-args.
- Var-args can be used only as a parameter.
- If a method has var-args as a parameter, it can be called by passing 0 or more arguments.
- Internally, var-args is a 1D array.

```java
datatype ...variableName
```

or

```java
datatype... variableName
```

### Notes

1. A method can use var-args only once.

```java
public void methodOne(int... a, int... b) {   // invalid
}

public void methodOne(int... a) {  // valid
}
```

2. If var-args is used with other parameters, it must be the last parameter.

```java
public void methodOne(int a, int... b) {  // valid
}

public void methodOne(int... a, int b) {  // invalid
}
```
