## Ways to Create a Thread

There are two ways to create a thread in Java:

1. Creating a thread by extending the Thread class
2. Creating a thread by implementing the Runnable interface

## Creating a Thread by Extending Thread Class

### Steps

1. Develop a class which extends the Thread class.
2. Override run() to define the job of the thread.
3. Create an object of the class which extends the Thread class.
4. Call start() to execute the thread.

    class MyThread extends Thread {
        @Override
        public void run() {
            // Thread job
        }
    }

### Important Methods

    public void run()
    public void start()

- A class which extends Thread is called a **thread class**.
- The main thread executes the main() method.
- The child thread executes the run() method.

## Thread Life Cycle States

1. Newly born state
2. Runnable or ready state
3. Running state
4. Waiting state
5. Dead state

<p align="center">
  <img src="images/thread-life-cycle-state.png" alt="Thread life cycle state diagram">
  <br>
  <b>Thread life cycle state diagram</b>
</p>

## start() Method

start() registers the thread class object, which is in the newly born state, with the thread scheduler.

It means start() takes the state of the thread class object inherited from java.lang.Thread and passes it to the thread scheduler.

## Runnable Interface

    java.lang
    |- Runnable (interface)
       |- void run() (abstract method)

- A class which extends Thread is called a **thread class**.
- A class which implements Runnable is called a **runnable class**.

## Creating a Thread by Implementing Runnable Interface

### Steps

1. Develop a class which implements the Runnable interface.
2. Override run() to define the job of the thread.
3. Create an object of the class which implements the Runnable interface.
4. Create an object of the Thread class by passing the runnable class object.
5. Call start() to execute the thread.

    class MyRunnable implements Runnable {
        @Override
        public void run() {
            // Thread job
        }
    }

## Setting and Getting Thread Names

In Java, every thread has a name. The name is assigned either by the JVM or manually by the programmer.

    public final void setName(String name)
    public final String getName()

- setName(String name): changes the name of the thread.
- getName(): returns the name of the thread.

## Thread Priorities

In Java, every thread has some priority. The priority can be the default priority 5, or it can be assigned manually by the programmer.

- The thread scheduler uses thread priorities to allocate CPU to threads.
- The thread with high priority may complete first.
- The thread with low priority may complete last.
- If multiple threads have the same priority, the thread scheduler decides which thread gets CPU.
- Thread priority must be between 1 and 10.
- 1 is the lowest priority.
- 10 is the highest priority.
- If we use a priority other than 1 to 10, JVM throws IllegalArgumentException.

### Standard Thread Priority Constants

    MIN_PRIORITY
    NORM_PRIORITY
    MAX_PRIORITY

### Important Methods

    public final void setPriority(int priority)
    public final int getPriority()

- setPriority(int priority): changes the priority of the thread.
- getPriority(): returns the priority of the thread.

> On some operating systems, thread priority support may not be available by default.

## Methods to Prevent Thread Execution

1. yield()
2. join()
3. sleep()

## yield()

It causes the currently executing thread to go to waiting state by giving chance to other waiting threads having the same priority.

- If waiting threads have low priority, the same thread resumes execution.
- If waiting threads are available, they execute first.
- After waiting threads complete, the thread which called yield() executes.

    public static void yield()

## join()

It makes a thread wait until another thread dies or completes execution.

    public final void join() throws InterruptedException

## sleep()

It causes the currently executing thread to sleep, or temporarily stop execution, for some milliseconds.

    public static void sleep(long millis) throws InterruptedException

