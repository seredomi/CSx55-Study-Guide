# CS455 Quiz Study Guide

## Week 1 (Threads, Locks)
| Question | Answer | 
| --- | --- |
| Though threads simplify sharing within a process, context-switching between threads within a process is just as expensive as context-switching between processes. | True |
| All frames on an executing thread’s stack must be of the same size. | False |
| Regardless of the recursion depth of an executing thread, there can only be 1 frame on that thread’s stack. | False |
| A process with 4 threads has 5 program counters; one for each thread, and one for the process. | False |
| Consider a Thread T1 that invoked method x, which resulted in the invocation of method y, which resulted in the invocation of method z. (T/F) All stack frames on the thread T1’s stack must be of the same size. | False |
| Consider a Thread T1 that invoked method x, which resulted in the invocation of method y, which resulted in the invocation of method z. How many frames exist on the thread T1’s stack? | 3 |
| Threads within a process cannot share the process heap. | False |
| Threads within a process must have their own stack. | True |
| Threads within a process share the same program counter. | False |
| When a process crashes, some threads within that process can continue to operate. | False |
| A single threaded process can only execute on one core, regardless of how many cores are available. | True |
| Context-switching between threads is more time-consuming than context-switching between processes. | False |
| Temporary variables of a function/method are allocated on the stack. | True |
| Consider a class A that has two synchronized methods s1() and s2();   this class also has two unsynchronized methods u1() and u2().  Class A was used to create two object instances, a1 and a2, in a particular process P.  Within the process P, there are N threads that are represented as T1, T2, …, TN.   Please indicate if the following 5 statements are True/False. (T/F) Threads T1, T2, …, TN can all be active in instance a1 at the same time and have different program counters.  | True |
| Threads T1 and T2 can be active inside method a1.s1() at the same time. | False |
|  Thread T1 can be active in a1.s1() and Thread T2 can be active in a1.s2() at the same time. | False |
| Thread T1 can be active in a1.u1() and Thread T2 can be active in a1.u2() at the same time. | True |
| Thread T1 can be active in a1.s1() and Thread T2 can be active in a2.s2() at the same time. | True |
| There is more than one lock per object. | False |
| A code with latent race conditions is likely to be reliant on lucky timing for correct operation. | True |
| The scope of a lock impacts the degree of concurrency for threads within a process. | True |
| A program that declares all its variables volatile will execute faster than the same program where these variables were not declared volatile.  | False |
| The volatile keyword for a variable is used for performance reasons because it allows Threads to cache that variable in a register. | False |


## Week 2 (Synchronization, Locks)
| Question | Answer |
| --- | --- |
| When using the Lock interface, it is critical to use the try.. finally block with the unlock() operation occurring in the finally block. This ensures that even if unexpected exceptions (including a RuntimeException) occur, the lock will still be released. | True |
| ReentrantLocks are granted as close to arrival order as possible.  | True |
| One disadvantage of explicit locking is that the lock scope cannot be controlled and must be restricted to the entire method. | False |
| When using the Lock interface, the lock in question is no longer attached to the object whose method is being called. | True |
| How many total locks have been acquired when a non-static synchronized method calls a static synchronized method?  | 2 |
| The class lock can be grabbed and released independently of the object lock. | True |
| For any given object, any number of its synchronized methods can execute at the same time. | False |
| Consider an unsynchronized method that does not include invocations to other methods. Invocations of this method will entail lock acquisition of the encapsulating object. | False |
| Invocation of (non-static) synchronized methods on an object involves acquisition of the implicit lock associated with that object. | True |
Two or more synchronized methods of the same object can never run in parallel in separate threads. | True | 

## Week 3 (Thread Safety)
| Question | Answer |
| --- | --- |
| Synchronizing all public methods of all classes within a program will guarantee thread-safety. | False |
| Consider an instance a1 of Class A.  Class A has two synchronized methods m1() and m2().   Method m1() includes an invocation to method m2().  Any thread that invokes a1.m1() will deadlock. | False |
| We only need to synchronize accesses to write operations on a variable.  The read operations need not be synchronized. | False |
| Consider a variable count of type long.   If the mutation operation on this variable is the increment operator (++)  there is no need to synchronize accesses to the mutation operation. | False |
| Stateless objects are always thread-safe. | True |
| The transient keyword plays a role in thread-synchronization by ensuring that all accesses to that variable will be redirected to main memory. | False |
| The key to thread-safe programming is not so much what the object does, but rather how it will be accessed. | True |
| The wait()/notify() mechanism in Java has an inherent race condition that cannot be solved without deep integration with the JVM. | True |
| Storing state variables of a particular class in public fields allows other classes within that program to reason about thread-safety. | False |
| Consider a program that has a mix of serial and parallel components. If the serial component accounts for 25% of the execution time, the maximum speed up that we can ever hope to achieve is 4. | True |
| Latency and throughputs may at times be at odds with each other. | True |
| Synchronizers encapsulate state that determines whether threads arriving at the synchronizer should be allowed to pass or wait.  However, they do support manipulation of this state.  | False |
|  A weakly consistent iterator may throw the ConcurrentModificiationException. | False |
| Consider a data structure such as the ConcurrentHashMap that relies on lock striping. Acquisition of the implicit lock associated with the object representing the data structure, will not result in acquisition of all locks that are part of stripe set. | True |
| In synchronized collections, such as the Hashtable, multiple threads may concurrently be active within the data structure at the same time. | False |
| Latches wait for other threads, while barriers wait for events. | False |
| Consider the case where you are using the semaphore synchronizer to implement resource pools.  You can skip the acquisition phase, and access the resource directly without violating correctness requirements.  | False |
| Consider the case where you are using the semaphore synchronizer to implement resource pools. If you perform an acquire as opposed to a release when you are done using the resource, eventually you will have liveness issues with resource pool becoming unavailable. | True |
| Consider the case where you are using the semaphore synchronizer to implement resource pools. The semaphore must be initialized to twice the number of available resources. | False |
