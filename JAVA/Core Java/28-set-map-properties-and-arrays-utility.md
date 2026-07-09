## Set

Use `Set` when duplicates are not allowed and insertion order is not preserved.

### Set hierarchy
- `HashSet`
  - `LinkedHashSet`
- `SortedSet`
  - `NavigableSet`
    - `TreeSet`

### HashSet
`HashSet` does not allow duplicates and does not preserve insertion order because objects are stored based on hash codes.
It allows homogeneous and heterogeneous objects.
`null` is allowed only once.

```java
HashSet hs = new HashSet();
```

An empty `HashSet` starts with initial capacity 16 and load factor 0.75.
After crossing the load factor, the capacity doubles.

### LinkedHashSet
`LinkedHashSet` is a subclass of `HashSet`.
It preserves insertion order.
It is built using a combination of hash table and linked list data structures.
It is available from JDK 1.4 onward.

### SortedSet
`SortedSet` is a subinterface of `Set`.
Use it when duplicates are not allowed, insertion order is not preserved, and elements must be stored in sorting order.

### NavigableSet
`NavigableSet` is a subinterface of `SortedSet` and provides navigation methods.

### TreeSet
`TreeSet` stores objects in sorting order.
It does not allow duplicates.
It does not preserve insertion order.
It allows only homogeneous objects; heterogeneous objects cause `ClassCastException`.
`null` is not allowed; otherwise `NullPointerException` is thrown.

```java
TreeSet ts = new TreeSet();
```

An empty `TreeSet` uses natural sorting order, which is ascending.

### Valid examples
```java
Set<Integer> s1 = new HashSet<Integer>();
Set<String> s2 = new TreeSet<String>();
Collection<Integer> c = new HashSet<Integer>();
SortedSet<String> s3 = new TreeSet<String>();
NavigableSet<Integer> s4 = new TreeSet<Integer>();
```

### Invalid example
```java
SortedSet<Integer> s = new HashSet<Integer>();
```

## Map

`Map` is an interface available in `java.util`.
Use `Map` when you want to store objects as key-value pairs.
In `Map`, both key and value are objects.
Duplicate keys are not allowed, but duplicate values are allowed.

### HashMap
`HashMap` is an implementation class of `Map`.
It does not preserve insertion order because keys are stored based on hash codes.
It allows homogeneous and heterogeneous objects for both key and value.
`null` is allowed for keys only once and for values any number of times.

```java
HashMap map = new HashMap();
```

An empty `HashMap` starts with initial capacity 16 and load factor 0.75.

### LinkedHashMap
`LinkedHashMap` is a subclass of `HashMap`.
It preserves insertion order.
It is built using a combination of hash table and linked list data structures.
It is available from JDK 1.4 onward.

### Hashtable
`Hashtable` is an implementation class of `Map`.
It is synchronized and thread safe.
Performance is lower than `HashMap`.
`null` is not allowed for both key and value.
It is a legacy class from JDK 1.0.

### HashMap vs Hashtable
| HashMap | Hashtable |
| --- | --- |
| Not synchronized | Synchronized |
| Not thread safe | Thread safe |
| High performance | Low performance |
| `null` allowed for key and value | `null` not allowed for key and value |
| Non-legacy class from JDK 1.2 | Legacy class from JDK 1.0 |

### IdentityHashMap
`IdentityHashMap` is an implementation class of `Map`.
It uses `==` to compare keys instead of `equals()`.

### WeakHashMap
`WeakHashMap` is an implementation class of `Map`.
It stores weak references for keys, so the garbage collector can remove entries when keys have no external references.
`HashMap` uses strong references for keys.

### TreeMap
`TreeMap` is an implementation class of `NavigableMap`, which is a subinterface of `SortedMap`, which is a subinterface of `Map`.
Use it when you want key-value pairs with keys in sorted order.
Duplicate keys are not allowed, duplicate values are allowed.
Keys must be homogeneous; heterogeneous keys cause `ClassCastException`.
`null` keys are not allowed; values can be `null` any number of times.

```java
TreeMap tm = new TreeMap();
```

An empty `TreeMap` uses natural sorting order, which is ascending.

### Comparable and Comparator
`Comparable` is in `java.lang` and is used for natural sorting order.
`Comparator` is in `java.util` and is used for customized sorting order.

```java
Comparable<T>
- int compareTo(T obj)

Comparator<T>
- int compare(T obj1, T obj2)
- boolean equals()
```

## Properties

`Properties` is a subclass of `Hashtable`.
It stores key-value pairs where both key and value are strings.
It can also load key-value pairs from a properties file.

### Properties file
A properties file uses the `.properties` extension.
It stores values in the form `key=value`.
A property means a key-value pair.

### Properties methods
- `void setProperty(String key, String value)`
- `String getProperty(String key)`
- `void load(Reader r)`

## Arrays utility class

`Arrays` is a class in `java.util`.
Its `asList(T... obj)` method converts values into a `List`.

```java
List<Integer> list = Arrays.asList(10, 20, 30, 40, 50);
```
