# JVM Architecture

![My project screenshot](./images/jdk-jre-jvm.png)
![My project screenshot](./images/jvm-architecture.png)


### Real-time Example
- A Java program is compiled to bytecode, loaded by the classloader, and executed by the JVM on any supported platform.

### Application
- JVM architecture makes Java platform independent and manages memory, execution, and security.

## Classloaders Subsystem

- **Bootstrap classloader**
	- `jre\lib\rt.jar`
- **Extension classloader**
	- `jre\lib\ext`
- **System/Application classloader**
	- `-cp` or `-classpath`
	- `set classpath`

## Heap Area

- Objects are created in heap area, and instance variables are created inside the object.
- One heap area is created per JVM.

## Method Area

- Class-level data such as static variables are stored in method area.
- Class-level code such as methods, static blocks, and constructors are stored in method area.
- One method area is created per JVM.

## Java Stacks

- One Java stack is created per thread.
- Method execution details, local variables, and parameters are stored in the Java stack.
- Each entry in the Java stack is called a stack frame.

## PC Registers

- One PC register is created per thread.
- The current line of code or instruction being executed is stored in the PC register.

## Native Method Stacks

- Native function information is stored in native method stacks.

## Native Method Library

- Sun Microsystems placed native functions written in C and C++ inside the JVM native method library.

## Native Method Interface

- The native method interface helps in calling native functions available in the native method library.

## Interpreter

- The interpreter reads bytecode, converts it into binary code line by line, and executes it.

## JIT Compiler (Just In Time Compiler)

- It converts bytecode into binary code along with the interpreter.
- It is faster than the interpreter.

## Garbage Collector

- It is a program inside the JVM.
- It goes to the JVM heap area and removes objects that are not in use to free memory.

---

