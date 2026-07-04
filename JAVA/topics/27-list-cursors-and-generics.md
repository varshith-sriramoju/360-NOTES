## List

`List` is a subinterface of `Collection`.
Use `List` when duplicates are allowed and insertion order is preserved.

### List hierarchy
- `ArrayList`
- `LinkedList`
- `Vector`
- `Stack`

Every element stored in a list has an index starting from 0.

### ArrayList
`ArrayList` is an implementation class of `List`.
It allows duplicates, preserves insertion order, supports homogeneous and heterogeneous objects, and allows `null` any number of times.

```java
ArrayList list = new ArrayList();
```

An empty `ArrayList` starts with initial capacity 10.
After crossing initial capacity, the new capacity is:

```text
new capacity = current capacity * 3 / 2 + 1
```

### Vector
`Vector` is an implementation class of `List`.
It has the same behavior as `ArrayList` for duplicates, insertion order, object types, and `null` handling.

```java
Vector v = new Vector();
```

An empty `Vector` starts with initial capacity 10.
The new capacity is:

```text
new capacity = 2 * current capacity
```

### ArrayList vs Vector
| ArrayList | Vector |
| --- | --- |
| Not synchronized | Synchronized |
| Not thread safe | Thread safe |
| High performance | Lower performance |
| Non-legacy class from JDK 1.2 | Legacy class from JDK 1.0 |

### LinkedList
`LinkedList` is an implementation class of `List`.
It allows duplicates, preserves insertion order, supports heterogeneous objects, and allows `null` any number of times.
In Java, `LinkedList` is built using a doubly linked list data structure.

### Stack
`Stack` is a subclass of `Vector`.
It is used when individual objects must follow last-in-first-out order.

## Cursors

A cursor is an object used to retrieve elements from a collection one by one.
There are 3 cursors in Java: `Enumeration`, `Iterator`, and `ListIterator`.

### Enumeration
`Enumeration` is used to retrieve elements one by one from a collection.
It provides:
- `boolean hasMoreElements()`
- `Object nextElement()`

`Vector` provides the factory method `Enumeration elements()`.

#### Disadvantages of Enumeration
- It is allowed only for legacy classes, so it is not universal.
- It supports only retrieval, not add, remove, or replace.

### Iterator
`Iterator` is used to retrieve elements one by one from a collection.
It provides:
- `boolean hasNext()`
- `Object next()`
- `void remove()`

The factory method is `public Iterator iterator()`.
It is available in all collections.

#### Advantages of Iterator over Enumeration
- It works with legacy and non-legacy classes.
- It supports remove operations.

#### Disadvantages of Iterator
- It is unidirectional and works only in the forward direction.
- It supports retrieve and remove only, not add or replace.

### ListIterator
`ListIterator` is used to retrieve elements from a collection.
It provides:
- `boolean hasNext()`
- `Object next()`
- `boolean hasPrevious()`
- `Object previous()`
- `void remove()`
- `void add(Object o)`
- `void set(Object o)`

The factory method is `public ListIterator listIterator()`.
It is available only for `List` collections.

#### Advantages of ListIterator over Iterator
- It is bidirectional.
- It supports retrieve, remove, add, and replace operations.

#### Disadvantages of ListIterator
- It works only with `List` collections.

## Generics

Generics were added in Java from JDK 1.5 onward.
Generics mean parameterized types.
Types such as `Integer`, `String`, `Employee`, and `Student` can be passed as parameters to classes, interfaces, and methods.

### Advantages of generics
- Type safety
- Avoids type casting problems
- Compile-time error checking instead of runtime errors

### Syntax of generics
```java
ClassName<Type>
InterfaceName<Type>
modifier <Type> returnType methodName()
```

### Type parameters
- `N` for Number
- `T` for Type
- `E` for Element
- `K` for Key
- `V` for Value

A type parameter is replaced with a class type.

### Generic class
A generic class accepts a type as a parameter and works on that type.

### Generic method
A generic method accepts a type as a parameter and works on that type.

### Arrays and collections with generics
Arrays are type safe and do not require type casting when reading values.
Collections are not type safe and require type casting when reading values.

```java
int[] arr = {10, 20, 30, 40, 50};
int a = arr[0];

ArrayList list = new ArrayList();
list.add(100);
Object o = list.get(0);
Integer i = (Integer) o;
```

