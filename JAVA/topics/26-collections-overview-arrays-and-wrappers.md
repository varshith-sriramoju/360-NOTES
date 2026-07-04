# Java Collections

## Collections

### What is a collection?
A collection is an object used to represent a group of other individual objects as a single entity.

### What is a collection framework?
A collection framework provides a set of classes and interfaces to represent a group of other individual objects as a single entity.

A collection framework means a set of classes and interfaces.

![Collection diagram](images/collection-diagram.png)

### Collections class
`Collections` is a class available in `java.util`.
It provides utility methods for collections such as `copy()`, `sort()`, and `reverse()`.

## Arrays

Arrays are indexed collections of a fixed number of homogeneous elements.
They can be used instead of collections, but they have disadvantages.

### Disadvantages of arrays
- Fixed size: the size is decided before compilation and cannot be changed at runtime.
- Only homogeneous elements: this can be partially handled with `Object[]`.
- No ready-made methods: arrays are not built on a data structure with rich utility methods.

### Advantages of collections
- Growable in nature: the size can expand dynamically at runtime.
- Support homogeneous and heterogeneous objects.
- Built on data structures, so they provide ready-made method support.

### Arrays vs Collections
| Arrays | Collections |
| --- | --- |
| Fixed in size | Growable in nature |
| Only homogeneous elements | Homogeneous and heterogeneous elements |
| No ready-made method support | Ready-made method support |
| Better memory usage | Better flexibility |
| Better performance | Lower performance |
| Store primitive values and objects | Store only objects |

### Collection interfaces
The collection chapter is dependent on 9 key interfaces.

1. `Collection`
2. `List`
3. `Set`
4. `SortedSet`
5. `NavigableSet`
6. `Queue`
7. `Map`
8. `SortedMap`
9. `NavigableMap`

These interfaces are available in `java.util`.
The `Collection` interface is the root interface in the collection hierarchy.
It contains methods common to all collections.

### Methods of Collection interface
- `boolean add(Object element)`
- `boolean addAll(Collection c)`
- `void clear()`
- `boolean contains(Object o)`
- `boolean isEmpty()`
- `Iterator iterator()`
- `boolean remove(Object o)`
- `boolean removeAll(Collection c)`
- `int size()`
- `Object[] toArray()`

## Wrapper classes

### What is a wrapper class?
A wrapper class is used to convert a primitive value into an object.
A wrapper object wraps a single primitive value.

### Primitive types and wrapper classes
| Primitive | Wrapper |
| --- | --- |
| byte | Byte |
| short | Short |
| int | Integer |
| long | Long |
| float | Float |
| double | Double |
| boolean | Boolean |
| char | Character |

All wrapper classes are available in `java.lang`.

### Examples
```java
Integer obj = new Integer(10);
System.out.println(obj);

Float fObj = new Float(2.5);
System.out.println(fObj);

Boolean bObj = new Boolean(true);
System.out.println(bObj);
```

### Wrapper object to primitive value
```java
Integer obj = new Integer(10);
int i = obj.intValue();

Float obj2 = new Float(2.5);
float f = obj2.floatValue();

Boolean obj3 = new Boolean(true);
boolean b = obj3.booleanValue();
```

### Auto-boxing and auto-unboxing
From JDK 1.5, Java supports auto-boxing and auto-unboxing.

Auto-boxing is the automatic conversion of a primitive value into a wrapper object.

```java
Integer obj1 = 10;
Float obj2 = 2.5f;
Boolean obj3 = true;
```

Auto-unboxing is the automatic conversion of a wrapper object into a primitive value.

```java
Integer obj1 = 10;
int i = obj1;

Float obj2 = 2.5f;
float f = obj2;

Boolean obj3 = true;
boolean b = obj3;
```

You can directly perform arithmetic and relational operations on wrapper objects.

```java
Integer obj1 = 10;
Integer obj2 = 20;

Integer obj3 = obj1 + obj2;
Boolean obj4 = obj1 <= obj2;
```

## Eclipse directory structure for a core Java project

- `src` for `.java` files
- `bin` for `.class` files

Collections store only objects, not primitive values.

