# OOP Concepts

![OOP Concepts](./images/OOPS-Concepts.png)

Object-oriented programming (OOP) concepts:

- `class`, `object`, data hiding, abstraction, encapsulation, inheritance (is-a), composition (has-a), polymorphism

---

# Inheritance

Inheritance creates new classes from existing ones (IS-A relationship) using the `extends` keyword.

Notes:

- Prefer creating objects of subclasses (they contain both subclass and superclass members).
- When a subclass is instantiated, the JVM calls the subclass constructor, which implicitly calls the superclass no-arg constructor (`super()`) unless you call another `super(...)`.
- A subclass instance can be assigned to a superclass reference, but only superclass members are accessible through that reference.

Example:

```java
class One { }
class Two extends One { }

Two t = new Two(); // valid
One o = new Two(); // valid
```

To access subclass-specific members, cast the reference:

```java
One a = new B();
// a.m2(); // compile-time error
B b = (B) a;
b.m2();
```

If the superclass has only a parameterized constructor, the subclass must explicitly call it using `super(...)`.

### `super` keyword

- Access superclass instance variables: `super.var`.
- Call superclass methods: `super.method()`.
- Call superclass constructors: `super()` or `super(args)`.

---

# Types of inheritance

- Single inheritance (simple, multilevel, hierarchical)
- Java does not support multiple class inheritance directly; use interfaces for multiple inheritance of type.

---

# Polymorphism

Polymorphism means many forms. In Java:

- Compile-time (static) polymorphism: method overloading, method hiding.
- Runtime (dynamic) polymorphism: method overriding.

Method signature = method name + parameter list (return type and modifiers not part of signature).

Example of overloading:

```java
void m1() {}
void m1(int i) {}
void m1(float a, int b) {}
```

Example of overriding:

```java
class Parents {
  public void study() { System.out.println("mba"); }
}
class Son extends Parents {
  public void study() { System.out.println("engineering"); }
}
```

Covariant return types allow an overriding method to return a subtype of the overridden method's return type (applicable to reference types, not primitives).

Method hiding occurs when a subclass declares a static method with the same signature as in the superclass.

---

# Abstract classes

- `abstract` marks classes or methods as incomplete.
- An abstract method has no body and must be implemented by concrete subclasses.
- An abstract class can contain both abstract and non-abstract methods, fields, constructors, and static members.

Example:

```java
abstract class One {
  public void methodOne() {}
  public abstract void methodThree();
}
```

- You cannot instantiate an abstract class, but you can hold subclass objects using an abstract class reference.

Notes:

1. If a method parameter type is an abstract class, pass a subclass object when calling.
2. If a method's return type is an abstract class, return an object of a concrete subclass.
