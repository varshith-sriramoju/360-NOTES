# Arrays

## What Are Arrays?

- Arrays are indexed collections of a fixed number of homogeneous elements.

## Advantages of Arrays

1. Managing multiple values becomes easy.
2. Accessing multiple values becomes easy.

```java
int a = 1, b = 2, c = 3, d = 4, e = 5;
System.out.println(a);
System.out.println(b);
System.out.println(c);

int arr[] = {1, 2, 3, 4, 5};
for (int i = 0; i < arr.length; i++) {
	System.out.println(arr[i]);
}
```

## Types of Arrays

1. One-dimensional arrays (1D arrays)
2. Multi-dimensional arrays (2D arrays and 3D arrays)

- To create an array in programming languages, we use the subscript symbol `[]`.

## 1D Array

### Declaration

```java
int a[];
int []a;
int[] a;
```

- `int a[5];` is invalid in Java.
- At declaration time, array size cannot be specified in Java.
- Declaring an array does not allocate memory.

### Creation

- Arrays are created using the `new` operator.

```java
datatype variableName[] = new datatype[size];
```

### Examples

```java
int a[] = new int[5];
float []b = new float[10];
char[] ch = new char[20];
String str[] = new String[4];
```

### Initialization

There are 2 ways to initialize a 1D array:

1. Compile-time initialization
   - Single-line initialization
   - Multi-line initialization
2. Runtime initialization

#### Single-Line Initialization

```java
int a[] = {1, 2, 3, 4, 5};
float []b = {1.1f, 2.2f, 3.3f};
char[] ch = {'a', 'b', 'c', 'd', 'e', 'f'};
String str[] = {"apple", "orange", "mango", "grapes"};
```

- In Java, we can create an array without using the `new` operator by using single-line initialization.

#### Multi-Line Initialization

```java
int a[] = new int[5];
a[0] = 10;
a[1] = 20;
a[2] = 30;
a[3] = 40;
a[4] = 50;
```

```java
double b[] = new double[3];
b[0] = 1.1;
b[1] = 2.2;
b[2] = 3.3;
```

```java
char ch[] = new char[4];
ch[0] = 'a';
ch[1] = 'b';
ch[2] = 'c';
ch[3] = 'd';
```

### Runtime Initialization

```java
Scanner sc = new Scanner(System.in);
int arr[] = new int[5];

for (int i = 0; i < arr.length; i++) {
	System.out.print("enter arr[" + i + "] = ");
	arr[i] = sc.nextInt();
}
```

## Accessing Elements of 1D Array

There are 2 ways to access the elements of a 1D array:

1. Accessing one element using index
2. Accessing all elements using loop

### Accessing One Element Using Index

```java
int arr[] = {10, 20, 30, 40, 50};

System.out.println(arr[0]);
System.out.println(arr[1]);
System.out.println(arr[2]);
System.out.println(arr[3]);
System.out.println(arr[4]);
```

### Accessing All Elements Using Loop

```java
int arr[] = {10, 20, 30, 40, 50};

for (int i = 0; i < arr.length; i++) {
	System.out.print(arr[i] + "  ");
}
```

## Programs on 1D Array

1. Write a Java program to find the sum of all the elements of a 1D array using `Scanner` to initialize the array.
2. Write a Java program to find the sum of all the even elements of a 1D array using single initialization.
3. Write a Java program to find the smallest element of a 1D array.

