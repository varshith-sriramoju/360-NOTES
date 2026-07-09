## Non-Synchronization

Allowing multiple threads to execute methods on a single object or resource at the same time is called **non-synchronization**.

### Note

If multiple threads are allowed to execute methods on a single object at the same time and the object contains data, then the data inside the object is shared between multiple threads.

This can lead to a **data inconsistency problem**.

## Resolving Data Inconsistency

Data inconsistency can be resolved by using **synchronization**.

## Synchronization

synchronized is a keyword and modifier which is allowed only for methods and blocks.

![Synchronization diagram](images/synchronization.png)

- A method declared using the synchronized keyword is called a **synchronized method**.
- A block declared using the synchronized keyword is called a **synchronized block**.

    public synchronized void methodOne() {
        // Synchronized method
    }

    synchronized (this) {
        // Synchronized block
    }

In Java, thread synchronization is achieved using the synchronized keyword.

If we declare a method or block using synchronized, the thread which gets CPU acquires the lock of an object for executing synchronized methods and blocks.

Meanwhile, other threads have to wait until the thread releases the lock.

When the thread completes execution of synchronized methods and blocks, it releases the lock. Then one waiting thread gets CPU and acquires the lock.

Waiting threads are not allowed to execute synchronized methods and synchronized blocks, but they are allowed to execute non-synchronized methods and non-synchronized blocks.

### Notes

1. Synchronization increases the waiting time of threads, which impacts performance.
2. We can reduce the waiting time of threads by reducing the lines of code inside synchronized blocks.

## Types of Locks

There are two types of locks a thread can acquire:

1. Object lock / object-level lock
2. Class lock / class-level lock

### Object Lock

A thread acquires the lock of an object if instance methods of a class are declared using the synchronized keyword.

### Class Lock

A thread acquires the lock of a class if static methods of a class are declared using the synchronized keyword.

### Notes

1. If a thread has acquired the lock of an object, we can say the thread is the owner of the object or the thread is monitoring the object.
2. In non-synchronization, multiple threads are allowed to execute methods on a single object at the same time, so the object is not thread-safe.
3. In synchronization, only one thread is allowed to execute methods on a single object at the same time, so the object is thread-safe.

## Assignment

1. Daemon thread
2. Deadlock
3. Starvation
4. interrupt()
