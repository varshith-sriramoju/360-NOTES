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

### Accessing Elements Using Enhanced For Loop

```java
int arr[] = {10, 20, 30, 40, 50};

for (int value : arr) {
	System.out.print(value + "  ");
}
```

### Notes

1. Enhanced for loop is also called for-each loop.
2. It is useful when we want to access all elements from left to right.
3. It does not provide index directly.
4. It should not be used when we need to update array elements using index.

## Important Properties of Arrays

1. Arrays are objects in Java.
2. Arrays are stored in heap memory.
3. Array size is fixed after creation.
4. Array index always starts from `0`.
5. Last index of an array is `length - 1`.
6. `length` is a variable, not a method.
7. Arrays can store primitive values and object references.
8. Array elements are stored in continuous index order.

```java
int arr[] = new int[5];

System.out.println(arr.length);   // 5
System.out.println(arr[0]);       // 0
System.out.println(arr[4]);       // 0
```

## Default Values in Arrays

| Array Type | Default Value |
|---|---|
| `byte`, `short`, `int`, `long` | `0` |
| `float`, `double` | `0.0` |
| `char` | `'\u0000'` |
| `boolean` | `false` |
| Object types like `String` | `null` |

```java
int a[] = new int[3];
boolean b[] = new boolean[3];
String s[] = new String[3];

System.out.println(a[0]);   // 0
System.out.println(b[0]);   // false
System.out.println(s[0]);   // null
```

## Valid and Invalid Array Creation

```java
int a[] = new int[5];       // valid
int b[] = new int[0];       // valid
int c[] = new int[-5];      // runtime exception
int d[] = new int[5L];      // compile-time error
```

### Notes

1. Array size can be `0`.
2. Negative array size gives `NegativeArraySizeException`.
3. Array size must be `int` type or compatible with `int`.
4. `byte`, `short`, and `char` values can be used as array size because they can be promoted to `int`.
5. `long`, `float`, and `double` cannot be used directly as array size.

## Common Array Exceptions

### `ArrayIndexOutOfBoundsException`

- This exception occurs when we access an array using an invalid index.

```java
int arr[] = {10, 20, 30};

System.out.println(arr[3]);   // runtime exception
System.out.println(arr[-1]);  // runtime exception
```

### `NullPointerException`

- This exception occurs when an array reference points to `null` and we try to access it.

```java
int arr[] = null;

System.out.println(arr.length);   // runtime exception
```

## Array Reference Assignment

- Array reference variables can be assigned to another reference variable of the same compatible type.

```java
int a[] = {10, 20, 30};
int b[] = a;

b[0] = 100;

System.out.println(a[0]);   // 100
```

### Note

- Here, both `a` and `b` refer to the same array object.

## Passing Array to Method

```java
class Test
{
	public static void printArray(int arr[])
	{
		for (int value : arr) {
			System.out.print(value + " ");
		}
	}

	public static void main(String[] args)
	{
		int a[] = {10, 20, 30};
		printArray(a);
	}
}
```

### Note

- When we pass an array to a method, the array reference is passed.
- If the method changes array elements, the original array is also changed.

```java
class Test
{
	public static void change(int arr[])
	{
		arr[0] = 100;
	}

	public static void main(String[] args)
	{
		int a[] = {10, 20, 30};
		change(a);
		System.out.println(a[0]);   // 100
	}
}
```

## Returning Array from Method

```java
class Test
{
	public static int[] getArray()
	{
		return new int[]{10, 20, 30};
	}

	public static void main(String[] args)
	{
		int arr[] = getArray();

		for (int value : arr) {
			System.out.print(value + " ");
		}
	}
}
```

## Copying an Array

### Manual Copy

```java
int a[] = {10, 20, 30};
int b[] = new int[a.length];

for (int i = 0; i < a.length; i++) {
	b[i] = a[i];
}
```

### Using `Arrays.copyOf()`

```java
import java.util.Arrays;

int a[] = {10, 20, 30};
int b[] = Arrays.copyOf(a, a.length);
```

### Using `System.arraycopy()`

```java
import java.util.Arrays;

int a[] = {10, 20, 30, 40, 50};
int b[] = new int[3];

System.arraycopy(a, 1, b, 0, 3);

System.out.println(Arrays.toString(b));   // [20, 30, 40]
```

## `java.util.Arrays` Utility Class

- `Arrays` is a utility class available in `java.util` package.
- It provides predefined methods to work with arrays.

```java
import java.util.Arrays;
```

| Method | Use |
|---|---|
| `Arrays.toString(arr)` | Converts array to readable string. |
| `Arrays.sort(arr)` | Sorts array in ascending order. |
| `Arrays.binarySearch(arr, key)` | Searches key in sorted array. |
| `Arrays.copyOf(arr, newLength)` | Copies array with given length. |
| `Arrays.equals(a, b)` | Compares two arrays by values. |
| `Arrays.fill(arr, value)` | Fills array with same value. |

```java
import java.util.Arrays;

int arr[] = {30, 10, 50, 20, 40};

Arrays.sort(arr);
System.out.println(Arrays.toString(arr));        // [10, 20, 30, 40, 50]
System.out.println(Arrays.binarySearch(arr, 30)); // 2
```

### Important Note on `binarySearch()`

- `Arrays.binarySearch()` should be used only on a sorted array.
- If the array is not sorted, the result is unpredictable.

## Comparing Arrays

```java
import java.util.Arrays;

int a[] = {10, 20, 30};
int b[] = {10, 20, 30};

System.out.println(a == b);              // false
System.out.println(a.equals(b));         // false
System.out.println(Arrays.equals(a, b)); // true
```

### Notes

1. `==` compares references.
2. Object class `equals()` also compares references for arrays.
3. `Arrays.equals()` compares array elements.

## Sorting Primitive and String Arrays

```java
import java.util.Arrays;

int numbers[] = {40, 10, 30, 20};
Arrays.sort(numbers);

String names[] = {"Ravi", "Amit", "Kiran"};
Arrays.sort(names);

System.out.println(Arrays.toString(numbers)); // [10, 20, 30, 40]
System.out.println(Arrays.toString(names));   // [Amit, Kiran, Ravi]
```

## Sorting in Descending Order

- Primitive arrays cannot be directly sorted in descending order using `Collections.reverseOrder()`.
- Use wrapper class array like `Integer[]`.

```java
import java.util.Arrays;
import java.util.Collections;

Integer arr[] = {40, 10, 30, 20};

Arrays.sort(arr, Collections.reverseOrder());

System.out.println(Arrays.toString(arr));   // [40, 30, 20, 10]
```

## Linear Search

- Linear search checks elements one by one.
- It works on sorted and unsorted arrays.

```java
public static int linearSearch(int arr[], int key)
{
	for (int i = 0; i < arr.length; i++) {
		if (arr[i] == key) {
			return i;
		}
	}
	return -1;
}
```

### Time Complexity

- Best case: `O(1)`
- Worst case: `O(n)`

## Binary Search

- Binary search repeatedly divides the search space into two parts.
- It works only on sorted arrays.

```java
public static int binarySearch(int arr[], int key)
{
	int left = 0;
	int right = arr.length - 1;

	while (left <= right) {
		int mid = left + (right - left) / 2;

		if (arr[mid] == key) {
			return mid;
		}
		else if (arr[mid] < key) {
			left = mid + 1;
		}
		else {
			right = mid - 1;
		}
	}

	return -1;
}
```

### Time Complexity

- Best case: `O(1)`
- Worst case: `O(log n)`

## Reverse an Array

```java
public static void reverse(int arr[])
{
	int left = 0;
	int right = arr.length - 1;

	while (left < right) {
		int temp = arr[left];
		arr[left] = arr[right];
		arr[right] = temp;

		left++;
		right--;
	}
}
```

## Find Largest and Smallest Element

```java
int arr[] = {40, 10, 50, 20, 30};

int largest = arr[0];
int smallest = arr[0];

for (int i = 1; i < arr.length; i++) {
	if (arr[i] > largest) {
		largest = arr[i];
	}

	if (arr[i] < smallest) {
		smallest = arr[i];
	}
}

System.out.println("Largest = " + largest);
System.out.println("Smallest = " + smallest);
```

## Find Second Largest Element

```java
public static int secondLargest(int arr[])
{
	int largest = Integer.MIN_VALUE;
	int secondLargest = Integer.MIN_VALUE;

	for (int value : arr) {
		if (value > largest) {
			secondLargest = largest;
			largest = value;
		}
		else if (value > secondLargest && value != largest) {
			secondLargest = value;
		}
	}

	return secondLargest;
}
```

### Note

- If the array does not contain at least two different values, this method returns `Integer.MIN_VALUE`.

## Check if Array Is Sorted

```java
public static boolean isSorted(int arr[])
{
	for (int i = 1; i < arr.length; i++) {
		if (arr[i] < arr[i - 1]) {
			return false;
		}
	}
	return true;
}
```

## Remove Duplicates from Sorted Array

- This is a common coding assessment problem.
- The array must be sorted.
- The method returns the count of unique elements.

```java
public static int removeDuplicates(int arr[])
{
	if (arr.length == 0) {
		return 0;
	}

	int index = 1;

	for (int i = 1; i < arr.length; i++) {
		if (arr[i] != arr[i - 1]) {
			arr[index] = arr[i];
			index++;
		}
	}

	return index;
}
```

```java
int arr[] = {10, 10, 20, 20, 30};
int uniqueCount = removeDuplicates(arr);

for (int i = 0; i < uniqueCount; i++) {
	System.out.print(arr[i] + " ");
}
```

## Frequency of Elements

### Using Nested Loops

```java
int arr[] = {10, 20, 10, 30, 20, 10};
boolean visited[] = new boolean[arr.length];

for (int i = 0; i < arr.length; i++) {
	if (visited[i]) {
		continue;
	}

	int count = 1;

	for (int j = i + 1; j < arr.length; j++) {
		if (arr[i] == arr[j]) {
			count++;
			visited[j] = true;
		}
	}

	System.out.println(arr[i] + " occurs " + count + " times");
}
```

### Using `HashMap`

```java
import java.util.HashMap;
import java.util.Map;

int arr[] = {10, 20, 10, 30, 20, 10};
Map<Integer, Integer> frequency = new HashMap<>();

for (int value : arr) {
	frequency.put(value, frequency.getOrDefault(value, 0) + 1);
}

System.out.println(frequency);
```

## Prefix Sum

- Prefix sum is used to answer range sum questions efficiently.

```java
int arr[] = {10, 20, 30, 40, 50};
int prefix[] = new int[arr.length];

prefix[0] = arr[0];

for (int i = 1; i < arr.length; i++) {
	prefix[i] = prefix[i - 1] + arr[i];
}

// Sum from index 1 to index 3
int left = 1;
int right = 3;
int sum = prefix[right] - prefix[left - 1];

System.out.println(sum);   // 90
```

### Range Sum Formula

```java
if (left == 0) {
	sum = prefix[right];
}
else {
	sum = prefix[right] - prefix[left - 1];
}
```

## Two Pointer Technique

- Two pointer technique is commonly used on sorted arrays.
- It is useful for pair sum, reversing, removing duplicates, and partition problems.

### Pair Sum in Sorted Array

```java
public static boolean hasPairSum(int arr[], int target)
{
	int left = 0;
	int right = arr.length - 1;

	while (left < right) {
		int sum = arr[left] + arr[right];

		if (sum == target) {
			return true;
		}
		else if (sum < target) {
			left++;
		}
		else {
			right--;
		}
	}

	return false;
}
```

## Sliding Window Technique

- Sliding window is used for subarray problems.
- It is commonly used when we need sum, maximum, or minimum in a continuous window.

### Maximum Sum of Subarray of Size `k`

```java
public static int maxSumWindow(int arr[], int k)
{
	int windowSum = 0;

	for (int i = 0; i < k; i++) {
		windowSum += arr[i];
	}

	int maxSum = windowSum;

	for (int i = k; i < arr.length; i++) {
		windowSum = windowSum + arr[i] - arr[i - k];
		maxSum = Math.max(maxSum, windowSum);
	}

	return maxSum;
}
```

## Kadane's Algorithm

- Kadane's algorithm is used to find maximum sum subarray.

```java
public static int maxSubarraySum(int arr[])
{
	int currentSum = arr[0];
	int maxSum = arr[0];

	for (int i = 1; i < arr.length; i++) {
		currentSum = Math.max(arr[i], currentSum + arr[i]);
		maxSum = Math.max(maxSum, currentSum);
	}

	return maxSum;
}
```

## Rotate Array by One Position

### Left Rotation by One

```java
public static void leftRotateByOne(int arr[])
{
	if (arr.length == 0) {
		return;
	}

	int first = arr[0];

	for (int i = 0; i < arr.length - 1; i++) {
		arr[i] = arr[i + 1];
	}

	arr[arr.length - 1] = first;
}
```

### Right Rotation by One

```java
public static void rightRotateByOne(int arr[])
{
	if (arr.length == 0) {
		return;
	}

	int last = arr[arr.length - 1];

	for (int i = arr.length - 1; i > 0; i--) {
		arr[i] = arr[i - 1];
	}

	arr[0] = last;
}
```

## Rotate Array by `k` Positions

- This solution uses reversal algorithm.
- Time complexity is `O(n)`.

```java
public static void reverse(int arr[], int left, int right)
{
	while (left < right) {
		int temp = arr[left];
		arr[left] = arr[right];
		arr[right] = temp;
		left++;
		right--;
	}
}

public static void rightRotate(int arr[], int k)
{
	int n = arr.length;

	if (n == 0) {
		return;
	}

	k = k % n;

	reverse(arr, 0, n - 1);
	reverse(arr, 0, k - 1);
	reverse(arr, k, n - 1);
}
```

## Find Missing Number

- Array contains numbers from `1` to `n`.
- One number is missing.

```java
public static int missingNumber(int arr[], int n)
{
	int expectedSum = n * (n + 1) / 2;
	int actualSum = 0;

	for (int value : arr) {
		actualSum += value;
	}

	return expectedSum - actualSum;
}
```

## Find Duplicate Number

### Using `HashSet`

```java
import java.util.HashSet;
import java.util.Set;

public static int findDuplicate(int arr[])
{
	Set<Integer> set = new HashSet<>();

	for (int value : arr) {
		if (set.contains(value)) {
			return value;
		}
		set.add(value);
	}

	return -1;
}
```

## Merge Two Sorted Arrays

```java
public static int[] mergeSortedArrays(int a[], int b[])
{
	int result[] = new int[a.length + b.length];
	int i = 0;
	int j = 0;
	int k = 0;

	while (i < a.length && j < b.length) {
		if (a[i] <= b[j]) {
			result[k] = a[i];
			i++;
		}
		else {
			result[k] = b[j];
			j++;
		}
		k++;
	}

	while (i < a.length) {
		result[k] = a[i];
		i++;
		k++;
	}

	while (j < b.length) {
		result[k] = b[j];
		j++;
		k++;
	}

	return result;
}
```

## Common Time Complexities

| Operation | Time Complexity |
|---|---|
| Access by index | `O(1)` |
| Update by index | `O(1)` |
| Traverse all elements | `O(n)` |
| Linear search | `O(n)` |
| Binary search | `O(log n)` |
| Insert at end if space is available | `O(1)` |
| Insert at beginning or middle | `O(n)` |
| Delete from beginning or middle | `O(n)` |
| Sort primitive array using `Arrays.sort()` | `O(n log n)` |

## Common Interview Points

1. Array size is fixed.
2. Array index starts from `0`.
3. Array length is accessed using `arr.length`.
4. String length is accessed using `str.length()`.
5. ArrayList size is accessed using `list.size()`.
6. Arrays can store duplicate values.
7. Arrays can store `null` if the array type is non-primitive.
8. Primitive arrays store actual values.
9. Object arrays store references.
10. `Arrays.equals()` compares values, but `==` compares references.
11. `Arrays.binarySearch()` requires sorted array.
12. For unknown or changing size, prefer `ArrayList` over array.

## Coding Assessment Patterns on Arrays

1. Traversal
2. Searching
3. Sorting
4. Reversal
5. Frequency counting
6. Prefix sum
7. Two pointers
8. Sliding window
9. Maximum subarray sum
10. Removing duplicates
11. Rotating array
12. Finding missing number
13. Finding duplicate number
14. Merging sorted arrays

## Programs on 1D Array

1. Write a Java program to find the sum of all the elements of a 1D array using `Scanner` to initialize the array.
2. Write a Java program to find the sum of all the even elements of a 1D array using single initialization.
3. Write a Java program to find the smallest element of a 1D array.
4. Write a Java program to find the largest element of a 1D array.
5. Write a Java program to find the second largest element of a 1D array.
6. Write a Java program to search an element using linear search.
7. Write a Java program to search an element using binary search.
8. Write a Java program to reverse a 1D array.
9. Write a Java program to sort a 1D array.
10. Write a Java program to count the frequency of each element.
11. Write a Java program to remove duplicates from a sorted array.
12. Write a Java program to find maximum sum subarray.
13. Write a Java program to find maximum sum of subarray of size `k`.
14. Write a Java program to find whether a pair exists with a given sum in a sorted array.

