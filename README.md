# CS455 Quiz Study Guide

## Week 1 (Threads, Processes, and Synchronization)
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


## Week 2 (Locks, Synchronization)
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

## Week 3 (Thread Safety, Synchronization)
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

## Week 4 (Networks)
| Question | Answer |
| --- | --- |
| A regular graph is one in which the n nodes are organized in a ring, with each node directly connected to its nearest k neighbors. In random graphs on the other hand, the vertices are connected to each other at random. Pathlength refers to the average number of hops needed to reach any node from any other node in the graph. The clustering coefficient is the measure of the level of clustering between the neighboring nodes for any vertex-node in the system. Indicate [High/Low] for the questions below. Random graph: Average pathlength | High |
| A regular graph is one in which the n nodes are organized in a ring, with each node directly connected to its nearest k neighbors. In random graphs on the other hand, the vertices are connected to each other at random. Pathlength refers to the average number of hops needed to reach any node from any other node in the graph. The clustering coefficient is the measure of the level of clustering between the neighboring nodes for any vertex-node in the system. Indicate [High/Low] for the questions below. Random graph: Clustering Coefficients | Low |
| A regular graph is one in which the n nodes are organized in a ring, with each node directly connected to its nearest k neighbors. In random graphs on the other hand, the vertices are connected to each other at random. Pathlength refers to the average number of hops needed to reach any node from any other node in the graph. The clustering coefficient is the measure of the level of clustering between the neighboring nodes for any vertex-node in the system. Indicate [High/Low] for the question below. Regular graph: Average pathlength | Low |
| A regular graph is one in which the n nodes are organized in a ring, with each node directly connected to its nearest k neighbors. In random graphs on the other hand, the vertices are connected to each other at random. Pathlength refers to the average number of hops needed to reach any node from any other node in the graph. The clustering coefficient is the measure of the level of clustering between the neighboring nodes for any vertex-node in the system. Indicate [High/Low] for the question below. Regular graph: Clustering Coefficients | High |
| A simple rule to create power-law networks is to ensure that new nodes attach preferentially to nodes with a high degree of connections to other nodes in the system. | True |
| Hubs can emerge in small-world networks. | False |
| An advantage of using a thread per connection is that the server benefits from lower thread management overheads compared to thread-per-request. | True |
| An advantage of using thread per request is that throughput is potentially maximized. | True |
| One advantage of a worker pool is that the number of worker threads is fixed, so, the number of threads may be too few to adequately cope with the rate of requests. Additionally, one disadvantage of a worker pool is that you need to account for coordinated accesses to the shared queue. | False |
| An advantage of a worker pool is that thread context switching is minimized. | True |

## Week 5 (P2P, Pastry, Chord)
| Question | Answer |
| --- | --- |
| Lookups based on centralized databases such as those used in Napster are susceptible to reliability, scalability, and targeted denial of service attacks. | True |
| In P2P systems that rely on prefix routing, the routing logic selects hops that have an increasing number of hexadecimal digits that are shared with destination GUID.  | True |
| In P2P systems, it is costly and cumbersome to replicate routes and object references n-fold. | False |
| Unlike network routers, routing tables in P2P overlays are updated in seconds. | True |
| In P2P systems, each node may differ in the quality of the resource that they contribute.  This also implies that every node will have different functional capabilities and responsibilities. | False |
| Data discovery by flooding the P2P system is guaranteed to succeed. | True |
| Cryptographic hash functions are used to generate GUIDs in P2P systems because of the distribution/dispersion of values they generate (load balancing) and their one-way property (it is computationally infeasible to derive the original content from the hash). | True |
| In P2P systems, nodes can be assigned identifiers from a different ID space than what is used for data items without impacting system performance. For example, the peer identifiers can be based on 160-bit identifiers while the data item identifiers can be based on 128-bit identifiers. | False |
| In P2P systems newly available peers are incrementally assimilated i.e. it's not the case that all new data traffic is redirected to the newly available peer till such time that another new peer is available.  | True |
| In the Napster P2P system, to account for peer failures at the edges, a copy of every data item is maintained in the central database. | False |
| In Pastry, using only the leafset is inefficient because the number of hops needed to reach a destination is very high. | True |
| In a well-populated Pastry system, a newly added node X will construct its routing table by retrieving 1 row from each of the peers that assist it in finding its position within the DHT space. | True |
| In Pastry, the routing table at a peer A can have multiple entries from some other peer X in the same row. | False |
| In Pastry, the routing table at a peer A can have multiple entries from some other peer X in the same column. | False |
| Consider a P2P system where peers are organized in a ring structure. Two peers in this system have IDs 4980 and 5220; assume there are no other peers with IDs that fall between 4981 through 5219.  A data item with hash-code (4992) will be stored at  Peer 5219 in Chord. | False |
| Consider a P2P system where peers are organized in a ring structure. Two peers in this system have IDs 4980 and 5220; assume there are no other peers with IDs that fall between 4981 through 5219.  A data item with hash-code (4992) will be stored at  Peer 4980 in Pastry. | True |
| Similar to routing in Pastry with leaf sets,  it is possible to route content using only the successor in Chord. | True |
| In Chord, a peer X may occupy multiple entries in the finger-table maintained at node Y. | True |
| Consider a Chord system with an ID space that encompasses 0 through 2128-1. How many entries are stored in the Finger Table at each peer? | 128 |
| Consider a P2P system where the peers have 160-bit IDs but the content identifiers are generated using MD5 (128-bits).  In this system: (1) there are thousands of peers who IDs are randomly generated using the SHA-1 cryptographic hash function, and (2) billions of data items that need to be stored. Once the storage operations have been completed, most of the peers will have no (or very few) stored elements. | True |


## Week 6
| Question | Answer |
| --- | --- |
| In this question you are required to contrast a well-populated PASTRY and Chord system. Peers and contents in both these systems are based on a 128-bit GUID.  You are required to consider the basic scheme without having to deal with refinements such as diversity of routing paths, redundancies, etc. How many rows are there in the routing table (or finger table) at a Chord peer in this system? | 128 |
| Which of these 2 refinements are suitable for search in unstructured peer to peer systems. | replication |
| Which of these 2 refinements are suitable for search in structured peer to peer systems. | random walks |
| Which of these 2 refinements are suitable for search in structured peer to peer systems. | gossiping |
| Which of these 2 refinements are suitable for search in unstructured peer to peer systems. | expanded ring search |
| A A multicast group can be constructed using just the class D address. | False |
| It may be possible for the average pathlengths (representing the number of logical hops) for communications between two nodes to be lower in hybrid P2P systems than in DHT based P2P systems. An ultra-peer network as in Gnutella, results in a power law network. Here, the average pathlengths for communications becomes log log N, which is much better than the log N that is possible in DHT-based systems.  | True |
| One disadvantage of an unstructured P2P system is that it is probabilistic, meaning that it can't offer absolute guarantees on locating objects. | True |
| One advantage of an unstructured P2P system is that it is self-organizing and naturally resilient to failures. | True |
| One advantage of a structured P2P system is that it maintains complex structures that are difficult and costly to maintain in dynamic settings. | False |
| One advantage of a structured P2P system is that it is guaranteed to locate objects with bounds on this operation. | True |
In this question you are required to contrast a well-populated PASTRY and Chord system. Peers and contents in both these systems are based on a 128-bit GUID.  You are required to consider the basic scheme without having to deal with refinements such as diversity of routing paths, redundancies, etc. How many rows are there in the routing table (or finger table) at a Chord peer in this system? | 128 |
