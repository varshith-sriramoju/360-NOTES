# Multi Threading

## Task

- A task means a job or work.
- Executing one task is called **single tasking**.

## Multi-Tasking

Executing multiple tasks simultaneously is called **multi-tasking**.

<p align="center">
  <img src="images/multi-tasking-diagram.png" alt="Multi-tasking diagram">
  <br>
  <b>Multi-tasking diagram</b>
</p>

### Types of Multi-Tasking

There are two types of multi-tasking:

1. Process-based multi-tasking / multi-processing
2. Thread-based multi-tasking

## Process

A program which is in running state or executing state is called a **process**. A process runs or executes to do some task.

## Thread

- A thread is a sub-part of a process.
- An independent path of execution in a process is called a thread.
- A flow of execution in a process is called a thread.
- A thread is a lightweight process.

### Notes

1. A process contains one or more threads.
2. A thread in a process performs some task.

## Process-Based Multi-Tasking

Executing multiple tasks simultaneously where each task is a separate independent process is called **process-based multi-tasking** or **multi-processing**.

> Process-based multi-tasking is an operating system approach.

## Thread-Based Multi-Tasking

Executing multiple tasks simultaneously where each task is a separate independent part of the same process is called **thread-based multi-tasking**.

Each part is a thread.

> Thread-based multi-tasking is a programmatic approach.

## Single Threading

If a process has one executing thread, it is called **single threading**.

## Multi-Threading

If a process has more than one thread executing simultaneously, it is called **multi-threading**.

![Multi-threading basics diagrams](images/multi-threading-basics-diagrams.png)

## Advantages of Multi-Threading

Multi-threading reduces response time and improves performance.

Examples:

1. Application servers and web servers use multi-threading.
2. Multimedia animations use multi-threading.

## Main Thread

- In every Java program, one thread is available which is created by the JVM. This thread is called the **main thread**.
- When Java program execution starts, the JVM creates the main thread to execute the Java program.
- As execution starts from the main() method, the main thread executes the main() method.
- If the main thread finishes execution, the program terminates immediately.
- The main thread is the last thread to finish execution.
- Other child threads are created from the main thread.
- In Java, everything is represented as a class and object, so a thread is also represented as a class and object.
- To work with multi-threading, Sun Microsystems provided predefined classes and interfaces.

### Multi-Threading API

    java.lang
    |- Thread (class)
    |- Runnable (interface)

The main thread is an object of Thread.

    public static Thread currentThread()

It returns the reference of the currently executing thread object.

> The priority of the main thread is 5.

## Child Thread / User Thread

In Java, programmers can also create threads. These threads are called **child threads** or **user threads**.

To create a thread, we have to create a thread class and an object of the thread class.

