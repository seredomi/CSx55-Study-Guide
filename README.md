# CS455 Quiz Study Guide

## Week 1 (Threads, Processes, and Synchronization)
<details open><summary>
  
  | Quiz 01  <sup><sub><i>[Click to Toggle View]</i></sub></sup> |
  | --- |
  
</summary>

| # | Question | Answer | 
| ---: | --- | --- |
| 1 | Though threads simplify sharing within a process, context-switching between threads within a process is just as expensive as context-switching between processes. | True |
| 2 | All frames on an executing thread’s stack must be of the same size. | False |
| 3 | Regardless of the recursion depth of an executing thread, there can only be 1 frame on that thread’s stack. | False |
| 4 | A process with 4 threads has 5 program counters; one for each thread, and one for the process. | False |
| 5 | Consider a Thread `T1` that invoked method `x`, which resulted in the invocation of method `y`, which resulted in the invocation of method `z`.<br><br>(T/F) All stack frames on the thread `T1`’s stack must be of the same size. | False |
| 6 | Consider a Thread `T1` that invoked method `x`, which resulted in the invocation of method `y`, which resulted in the invocation of method `z`.<br><br>How many frames exist on the thread `T1`’s stack? | 3 |
| 7 | Threads within a process cannot share the process heap. | False |
| 8 | Threads within a process must have their own stack. | True |
| 9 | Threads within a process share the same program counter. | False |
| 10 | When a process crashes, some threads within that process can continue to operate. | False |
| 11 | A single-threaded process can only execute on one core, regardless of how many cores are available. | True |
| 12 | Context-switching between threads is more time-consuming than context-switching between processes. | False |
| 13 | Temporary variables of a function/method are allocated on the stack. | True |

</details>

<details open><summary>
  
  | Quiz 02  <sup><sub><i>[Click to Toggle View]</i></sub></sup> |
  | --- |
  
</summary>
  
| # | Question | Answer | 
| ---: | --- | --- |
|| Consider a class `A` that has two synchronized methods `s1()` and `s2()`;   this class also has two unsynchronized methods `u1()` and `u2()`.  Class `A` was used to create two object instances, `a1` and `a2`, in a particular process `P`.  Within the process `P`, there are `N` threads that are represented as `T1`, `T2`, …, `TN`.<br><br> \* <ins>Please indicate if the following 5 statements are True/False.</ins><br><br> ||
| 1 | Threads `T1`, `T2`, …, `TN` can all be active in instance `a1` at the same time and have different program counters. | True |
| 2 | Threads `T1` and `T2` can be active inside method `a1.s1()` at the same time. | False |
| 3 | Thread `T1` can be active in `a1.s1()` and Thread `T2` can be active in `a1.s2()` at the same time. | False |
| 4 | Thread `T1` can be active in `a1.u1()` and Thread `T2` can be active in `a1.u2()` at the same time. | True |
| 5 | Thread `T1` can be active in `a1.s1()` and Thread `T2` can be active in `a2.s2()` at the same time. | True |
| 6 | There is more than one lock per object. | False |
| 7 | A code with latent race conditions is likely to be reliant on lucky timing for correct operation. | True |
| 8 | The scope of a lock impacts the degree of concurrency for threads within a process. | True |
| 9 | A program that declares all its variables volatile will execute faster than the same program where these variables were not declared volatile. | False |
| 10 | The volatile keyword for a variable is used for performance reasons because it allows `Threads` to cache that variable in a register. | False |

</details>

---

## Week 2 (Locks, Synchronization)
<details open><summary>
  
  | Quiz 03  <sup><sub><i>[Click to Toggle View]</i></sub></sup> |
  | --- |
  
</summary>

| # | Question | Answer |
| ---: | --- | --- |
| 1 | When using the Lock interface, it is critical to use the `try... finally` block with the `unlock()` operation occurring in the finally block. This ensures that even if unexpected exceptions (including a RuntimeException) occur, the lock will still be released. | True |
| 2 | ReentrantLocks are granted as close to arrival order as possible. | True |
| 3 | One disadvantage of explicit locking is that the lock scope cannot be controlled and must be restricted to the entire method. | False |
| 4 | When using the `Lock` interface, the lock in question is no longer attached to the object whose method is being called. | True |
| 5 | How many total locks have been acquired when a non-static synchronized method calls a static synchronized method?  | 2 |
| 6 | The class lock can be grabbed and released independently of the object lock. | True |
| 7 | For any given object, any number of its synchronized methods can execute at the same time. | False |
| 8 | Consider an unsynchronized method that does not include invocations to other methods. Invocations of this method will entail lock acquisition of the encapsulating object. | False |
| 9 | Invocation of (non-static) synchronized methods on an object involves acquisition of the implicit lock associated with that object. | True |
| 10 | Two or more synchronized methods of the same object can never run in parallel in separate threads. | True | 

</details>

---

## Week 3 (Thread Safety, Synchronization)
<details open><summary>
  
  | Quiz 04  <sup><sub><i>[Click to Toggle View]</i></sub></sup> |
  | --- |
  
</summary>

| # | Question | Answer |
| ---: | --- | --- |
| 1 | Synchronizing all public methods of all classes within a program will guarantee thread-safety. | False |
| 2 | Consider an instance `a1` of Class `A`. Class `A` has two synchronized methods `m1()` and `m2()`. Method `m1()` includes an invocation to method `m2()`.<br><br>(T/F) Any thread that invokes `a1.m1()` will deadlock. | False |
| 3 | We only need to synchronize accesses to write operations on a variable. The read operations need not be synchronized. | False |
| 4 | Consider a variable `count` of type `long`. If the mutation operation on this variable is the increment operator (`++`) there is no need to synchronize accesses to the mutation operation. | False |
| 5 | Stateless objects are always thread-safe. | True |
| 6 | The transient keyword plays a role in thread-synchronization by ensuring that all accesses to that variable will be redirected to main memory. | False |
| 7 | The key to thread-safe programming is not so much what the object does, but rather how it will be accessed. | True |
| 8 | The `wait()`/`notify()` mechanism in Java has an inherent race condition that cannot be solved without deep integration with the JVM. | True |
| 9 | Storing state variables of a particular class in public fields allows other classes within that program to reason about thread-safety. | False |
| 10 | A program that has concurrency bugs may continue to function correctly if the rate of invocations and the number of threads are below a certain threshold. | True |

</details>

<details open><summary>
  
  | Quiz 05  <sup><sub><i>[Click to Toggle View]</i></sub></sup> |
  | --- |
  
</summary>

| # | Question | Answer |
| ---: | --- | --- |
| 1 | Consider a program that has a mix of serial and parallel components. If the serial component accounts for 25% of the execution time, the maximum speed up that we can ever hope to achieve is 4x. | True |
| 2 | Latency and throughputs may, at times, be at odds with each other. | True |
| 3 | Synchronizers encapsulate state that determines whether threads arriving at the synchronizer should be allowed to pass or wait. However, they do support manipulation of this state. | True |
| 4 | A weakly consistent iterator may throw the `ConcurrentModificiationException`. | False |
| 5 | Consider a data structure such as the `ConcurrentHashMap` that relies on lock striping. Acquisition of the implicit lock associated with the object representing the data structure will not result in acquisition of all locks that are part of stripe set. | True |
| 6 | In synchronized collections, such as the `Hashtable`, multiple threads may concurrently be active within the data structure at the same time. | False |
| 7 | Latches wait for other threads, while barriers wait for events. | False |
| 8 | Consider the case where you are using the semaphore synchronizer to implement resource pools. You can skip the acquisition phase, and access the resource directly without violating correctness requirements. | False |
| 9 | Consider the case where you are using the semaphore synchronizer to implement resource pools. If you perform an `acquire` as opposed to a `release` when you are done using the resource, eventually you will have liveness issues with resource pool becoming unavailable. | True |
| 10 | Consider the case where you are using the semaphore synchronizer to implement resource pools. The semaphore must be initialized to twice the number of available resources. | False |

</details>

---

## Week 4 (Networks)
<details open><summary>
  
  | Quiz 06  <sup><sub><i>[Click to Toggle View]</i></sub></sup> |
  | --- |
  
</summary>
  
| # | Question | Answer |
| ---: | --- | --- |
| 1 | A ***regular graph*** is one in which the `n` nodes are organized in a ring, with each node directly connected to its nearest `k` neighbors. In ***random graphs*** on the other hand, the vertices are connected to each other at random. ***Pathlength*** refers to the average number of hops needed to reach any node from any other node in the graph. The ***clustering coefficient*** is the measure of the level of clustering between the neighboring nodes for any vertex-node in the system. Indicate [High/Low] for the questions below.<br><br>Random graph: Average pathlength | Low |
| 2 | A ***regular graph*** is one in which the `n` nodes are organized in a ring, with each node directly connected to its nearest `k` neighbors. In ***random graphs*** on the other hand, the vertices are connected to each other at random. ***Pathlength*** refers to the average number of hops needed to reach any node from any other node in the graph. The ***clustering coefficient*** is the measure of the level of clustering between the neighboring nodes for any vertex-node in the system. Indicate [High/Low] for the questions below.<br><br>Random graph: Clustering Coefficients | Low |
| 3 | A ***regular graph*** is one in which the `n` nodes are organized in a ring, with each node directly connected to its nearest `k` neighbors. In ***random graphs*** on the other hand, the vertices are connected to each other at random. ***Pathlength*** refers to the average number of hops needed to reach any node from any other node in the graph. The ***clustering coefficient*** is the measure of the level of clustering between the neighboring nodes for any vertex-node in the system. Indicate [High/Low] for the questions below.<br><br>Regular graph: Average pathlength | High |
| 4 | A ***regular graph*** is one in which the `n` nodes are organized in a ring, with each node directly connected to its nearest `k` neighbors. In ***random graphs*** on the other hand, the vertices are connected to each other at random. ***Pathlength*** refers to the average number of hops needed to reach any node from any other node in the graph. The ***clustering coefficient*** is the measure of the level of clustering between the neighboring nodes for any vertex-node in the system. Indicate [High/Low] for the questions below.<br><br>Regular graph: Clustering Coefficients | High |
| 5 | A simple rule to create power-law networks is to ensure that new nodes attach preferentially to nodes with a high degree of connections to other nodes in the system. | True |
| 6 | Hubs can emerge in small-world networks. | False |
| 7 | An advantage of using a thread-per-connection is that the server benefits from lower thread management overheads compared to thread-per-request. | True |
| 8 | An advantage of using thread-per-request is that throughput is potentially maximized. | True |
| 9 | One advantage of a worker pool is that the number of worker threads is fixed. So, the number of threads may be too few to adequately cope with the rate of requests. Additionally, one disadvantage of a worker pool is that you need to account for coordinated accesses to the shared queue. | False |
| 10 | An advantage of a worker pool is that thread context-switching is minimized. | True |

</details>

---

## Week 5 (P2P, Pastry, Chord)
<details open><summary>
  
  | Quiz 07  <sup><sub><i>[Click to Toggle View]</i></sub></sup> |
  | --- |
  
</summary>
  
| # | Question | Answer |
| ---: | --- | --- |
| 1 | Lookups based on centralized databases such as those used in Napster are susceptible to reliability, scalability, and targeted denial of service attacks. | True |
| 2 | In P2P systems that rely on prefix routing, the routing logic selects hops that have an increasing number of hexadecimal digits that are shared with destination GUID. | True |
| 3 | In P2P systems, it is costly and cumbersome to replicate routes and object references n-fold. | False |
| 4 | Unlike network routers, routing tables in P2P overlays are updated in seconds. | True |
| 5 | In P2P systems, each node may differ in the quality of the resource that they contribute. This also implies that every node will have different functional capabilities and responsibilities. | False |
| 6 | Data discovery by flooding the P2P system is guaranteed to succeed. | True |
| 7 | Cryptographic hash functions are used to generate GUIDs in P2P systems because of the distribution/dispersion of values they generate (load balancing) and their one-way property (it is computationally infeasible to derive the original content from the hash). | True |
| 8 | In P2P systems, nodes can be assigned identifiers from a different ID space than what is used for data items without impacting system performance. For example, the peer identifiers can be based on 160-bit identifiers while the data item identifiers can be based on 128-bit identifiers. | False |
| 9 | In P2P systems newly available peers are incrementally assimilated (i.e., it's not the case that all new data traffic is redirected to the newly available peer till such time that another new peer is available). | True |
| 10 | In the Napster P2P system, to account for peer failures at the edges, a copy of every data item is maintained in the central database. | False |

</details>

<details open><summary>
  
  | Quiz 08  <sup><sub><i>[Click to Toggle View]</i></sub></sup> |
  | --- |
  
</summary>

| # | Question | Answer |
| ---: | --- | --- |
| 1 | In Pastry, using only the leafset is inefficient because the number of hops needed to reach a destination is very high. | True |
| 2 | In a well-populated Pastry system, a newly added node `X` will construct its routing table by retrieving 1 row from each of the peers that assist it in finding its position within the DHT space. | True |
| 3 | In Pastry, the routing table at a peer `A` can have multiple entries from some other peer `X` in the same row. | False |
| 4 | In Pastry, the routing table at a peer `A` can have multiple entries from some other peer `X` in the same column. | False |
| 5 | Consider a P2P system where peers are organized in a ring structure. Two peers in this system have IDs `4980` and `5220`; assume there are no other peers with IDs that fall between `4981` through `5219`.<br><br>(T/F) A data item with hash-code `4992` will be stored at Peer `5219` in ***Chord***. | False |
| 6 | Consider a P2P system where peers are organized in a ring structure. Two peers in this system have IDs `4980` and `5220`; assume there are no other peers with IDs that fall between `4981` through `5219`.<br><br>(T/F) A data item with hash-code `4992` will be stored at Peer `4980` in ***Pastry***. | True |
| 7 | Similar to routing in Pastry with leafsets, it is possible to route content using only the successor in Chord. | True |
| 8 | In Chord, a peer `X` may occupy multiple entries in the finger table maintained at node `Y`. | True |
| 9 | Consider a Chord system with an ID space that encompasses 0 through 2<sup>128-1</sup>. How many entries are stored in the finger table at each peer? | 128 |
| 10 | Consider a P2P system where the peers have 160-bit IDs but the content identifiers are generated using MD5 (128-bits). In this system: **(1)** there are thousands of peers who IDs are randomly generated using the SHA-1 cryptographic hash function, and **(2)** billions of data items that need to be stored.<br><br>(T/F) Once the storage operations have been completed, most of the peers will have no (or very few) stored elements. | True |

</details>

---

## Week 6 (Continued - P2P, Pastry, Chord)
<details open><summary>
  
  | Quiz 09  <sup><sub><i>[Click to Toggle View]</i></sub></sup> |
  | --- |
  
</summary>
  
| # | Question | Answer |
| ---: | --- | --- |
| 1 | In this question you are required to contrast a well-populated Pastry and Chord system. Peers and contents in both these systems are based on a 128-bit GUID. You are required to consider the basic scheme without having to deal with refinements such as diversity of routing paths, redundancies, etc.<br><br>How many rows are there in the routing table (or finger table) at a ***Pastry*** peer in this system? | 32 |
| 2 | Which of the 2 refinements, `consistent hashing` or `replication`, is suitable for search in ***unstructured*** P2P systems. | Replication |
| 3 | Which of the 2 refinements, `ephemeral peers` or `random walks`, is suitable for search in ***unstructured*** P2P systems. | Random Walks |
| 4 | Which of the 2 refinements, `gossiping` or `trackers`, is suitable for search in ***unstructured*** P2P systems. | Gossiping |
| 5 | Which of the 2 refinements, `expanded ring search` or `postfix routing`, is suitable for search in ***unstructured*** P2P systems. | Expanded Ring Search |
| 6 | A multicast group can be constructed using just the class `D` address. | False |
| 7 | It may be possible for the average pathlengths (representing the number of logical hops) for communications between two nodes to be lower in hybrid P2P systems than in DHT-based P2P systems. An ultra-peer network as in Gnutella, results in a power-law network. Here, the average pathlengths for communications becomes $\log \log N$, which is much better than the $\log N$ that is possible in DHT-based systems.  | True |
| 8 | One ***disadvantage*** of an ***unstructured*** P2P system is that it is probabilistic, meaning that it can't offer absolute guarantees on locating objects. | True |
| 9 | One ***advantage*** of an ***unstructured*** P2P system is that it is self-organizing and naturally resilient to failures. | True |
| 10 | One ***advantage*** of a ***structured*** P2P system is that it maintains complex structures that are difficult and costly to maintain in dynamic settings. | False |
| 11 | One ***advantage*** of a ***structured*** P2P system is that it is guaranteed to locate objects with bounds on this operation. | True |
| 12 | In this question you are required to contrast a well-populated Pastry and Chord system. Peers and contents in both these systems are based on a 128-bit GUID. You are required to consider the basic scheme without having to deal with refinements such as diversity of routing paths, redundancies, etc.<br><br>How many rows are there in the routing table (or finger table) at a ***Chord*** peer in this system? | 128 |

</details>

---

## Week 9 (MapReduce)
<details open><summary>
  
  | Quiz 10  <sup><sub><i>[Click to Toggle View]</i></sub></sup> |
  | --- |
  
</summary>
  
| # | Question | Answer |
| ---: | --- | --- |
| 1 | The combiner has data locality. | True |
| 2 | In cases, where speculative backup tasks are launched to circumvent stragglers, results from the original task are discarded regardless of whether it arrives before the corresponding speculative task. | False |
| 3 | Straggler circumventions in a MapReduce job only targets mappers and not the reducers. | False |
| 4 | A given reducer can start processing only after all mappers have finished their processing. | True |
| 5 | Reducers **do not** have data locality. | True |
| 6 | In some instances, the MapReduce framework allows mappers to communicate with each other. | False |
| 7 | Consider a particular reducer `RX` that has received 1000 intermediate outputs from mappers; these intermediate outputs correspond to 100 unique keys.<br><br>(T/F) If the reducer `RX` fails, all mappers must be re-executed to retrieve their intermediate outputs for the newly launched replacement for reducer `RX`. | False |
| 8 | Consider a particular reducer `RX` that has received 1000 intermediate outputs from mappers; these intermediate outputs correspond to 100 unique keys.<br><br>(T/F) It is possible that one of the mappers may not have generated intermediate outputs (<key, value> pairs) that need to be routed to `RX`. | True |
| 9 | Consider a particular reducer `RX` that has received 1000 intermediate outputs from mappers; these intermediate outputs correspond to 100 unique keys.<br><br>(T/F) The intermediate keys are sorted but not grouped (by key) before invoking the reduce function. | False |
| 10 | Consider a particular reducer `RX` that has received 1000 intermediate outputs from mappers; these intermediate outputs correspond to 100 unique keys.<br><br>(T/F) The keys are grouped (by key), but not sorted before invoking the reduce function. | False |
| 11 | Consider a particular reducer `RX` that has received 1000 intermediate outputs from mappers; these intermediate outputs correspond to 100 unique keys.<br><br>(T/F) The reduce function of `RX` is invoked exactly 100 times. | True |

</details>
