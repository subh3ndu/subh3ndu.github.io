# Parallel Distributed Systems

<p align="center">
	<img src="https://www.investopedia.com/thmb/mDnj5rlLi3fCz3ApVPaeD4wk5Nw=/750x0/filters:no_upscale():max_bytes(150000):strip_icc():format(webp)/moores-law-4192714-final-1-a38eccda0b74461b8f410c476cf0291e.png" width="500" alt="moore's law"/>
</p>

## PDS - 1

:laughing:

## PDS - 2

### 1. Briefly Describe Superscalar Processor ? 
**Ans:-**

1. **Superscalar Execution:**  Scheduling of instructions is determined by a number of factors:
	- True Data Dependency: The result of one operation is an input to the next.

	- Resource Dependency: Two operations require the same resource.

	- Branch Dependency: Scheduling instructions across conditional branch statements cannot be done deterministically a-priority.

	- The scheduler, a piece of hardware looks at a large number of instructions in an instruction queue and selects appropriate number of instructions to execute concurrently based on these factors.

	- The complexity of this hardware is an important constraint on superscalar processors.

2. **Issue Mechanics:**
	- In the simpler model, instructions can be issued only in the order in which they are encountered. That is, if the second instruction cannot be issued because it has a data dependency with the first, only one instruction is issued in the cycle. This is called in-order issue.

	- In a more aggressive model, instructions can be issued out of order. In this case, if the second instruction has data dependencies with the first, but the third instruction does not, the first and third instructions can be co-scheduled. This is also called dynamic issue.

	- Performance of in-order issue is generally limited.

3. **Efficiency Considerations:**
	- Not all functional units can be kept busy at all times.

	- If during a cycle, no functional units are utilized, this is referred to as vertical waste.

	- If during a cycle, only some of the functional units are utilized, this is referred to as horizontal waste.

	- Due to limited parallelism in typical instruction traces, dependencies, or the inability of the scheduler to extract parallelism, the performance of superscalar processors is eventually limited.

	- Conventional microprocessors typically support four-way superscalar execution.

### 2. Explain VLIW Architecture ?
**Ans:-**

**1. Architecture:-**
- The hardware cost and complexity of the superscalar scheduler is a major consideration in processor design.

- To address this issues, VLIW processors rely on compile time analysis to identify and bundle together instructions that can be executed concurrently.

- These instructions are packed and dispatched together, and thus the name very long
instruction word.

- This concept was used with some commercial success in the Multiflow Trace machine (circa 1984).

- Variants of this concept are employed in the Intel IA64 processors.

**2. Consideration :**

- Issue hardware is simpler.

- Compiler has a bigger context from which to select co scheduled instructions.

- Compilers, however, do not have runtime information such as cache misses. Scheduling is, therefore, inherently conservative.

- Branch and memory prediction is more difficult.

- VLIW performance is highly dependent on the compiler.

- A number of techniques such as loop unrolling, speculative execution, branch prediction are critical.

- Typical VLIW processors are limited to 4-way to 8-way parallelism.


### 3. Explain Snoopy Cache System and its Performance ? 
**Ans:-**  In snoopy caches, there is a broadcast media that listens to all invalidates and read requests and performs appropriate coherence operations locally. 

A simple snoopy bus based cache coherence system.

<p align='center'>
	<img src="https://www.tutorialspoint.com/assets/questions/media/54491/cache_protocols.jpg" width="400" alt="Snoopy Cache System" />
</p>

**Performance of Snoopy Caches:**
- Once copies of data are tagged dirty, all subsequent operations can be performed locally on the cache without generating external traffic.

- If a data item is read by a number of processors, it transitions to the shared state in the cache and all subsequent read operations become local.

- If processors read and update data at the same time, they generate coherence requests on
the bus - which is ultimately bandwidth limited.

### 4. What is Cache Coherence ? Explain its activities in a Multiprocessor System ?
**Ans:-**

- **Cache Coherence:-**
	- In a multiprocessor system, data inconsistency may occur among adjacent levels or within the same level of the memory hierarchy. 

	- In a shared memory multiprocessor with a separate cache memory for each processor, it is possible to have many copies of any one instruction operand: one copy in the main memory and one in each cache memory. When one copy of an operand is changed, the other copies of the operand must be changed also. 

	- Example : Cache and the main memory may have inconsistent copies of the same object As multiple processors operate in parallel, and independently multiple caches may possess different copies of the same memory block, this creates a cache coherence problem.

-  **Activities in a Multiprocessor System:-**

	- If a processor just reads a value once and does not need it again, an update protocol may generate significant overhead.

	- If two processors make interleaved test and updates to a variable, an update protocol is better.

	- Both protocols suffer from false sharing overheads (two words that are not shared, however, they lie on the same cache line).

	- Most current machines use invalidate protocols

### 5. Describe Topologies of a Multistage Omega Network ?
**Ans:-**
- One of the most commonly used multistage interconnects is the Omega network.

- This network consists of log p stages, where p is the number of inputs/outputs.

- At each stage, input i is connected to output j if:

$$
j = \begin{cases}
   2i &\text{if  \ \ \ }  0 \leq i \leq p/2 - 1 \\
   2i + 1 - p &\text{if \ \ \ }  p/2 \leq i \leq p - 1
\end{cases}
$$

- Each stage of the Omega network implements a perfect shuffle as follows:

<p align="center"> 
	<img src="https://i.postimg.cc/h4r7H9LN/Screenshot-2022-12-12-at-12-30-40-AM.jpg" width="400" alt="omega network"/>
	<p align="center"><i>A perfect shuffle interconnection for eight inputs and outputs.</i></p>
</p>


- The perfect shuffle patterns are connected using 2×2 switches.

- The switches operate in two modes – crossover or passthrough

<p align="center"> 
	<img src="https://i.postimg.cc/pdmL1jWb/Screenshot-2022-12-12-at-12-40-57-AM.jpg" width="500" alt="omega network"/>
	<p align="center">
		<i>Two switching configurations of the 2 × 2 switch: (a) Pass-through; (b) Cross-over.</i>
	</p>
</p>

- A complete Omega network with the perfect shuffle interconnects and switches can now be illustrated:

<p align="center"> 
	<img src="https://i.postimg.cc/tCJ7w8CV/Screenshot-2022-12-12-at-12-32-48-AM.jpg" width="400" alt="omega network"/>
	<p align="center"><i>A complete omega network connecting eight inputs and eight outputs.</i></p>
</p>


- An omega network has $p/2 * log(p)$ switching
nodes, and the cost of such a network grows as $(p log p)$.

### 6. Compare NUMA and UMA Architecture ?


- The UMA (shared memory) model uses one or two memory controllers. As against, NUMA can have multiple memory controllers to access the memory.
    
- Single, multiple and crossbar busses are used in UMA architecture. Conversely, NUMA uses hierarchical, and tree type of busses and network connection.
    
- In UMA the memory accessing time for each processor is the same while in NUMA the memory accessing time changes as the distance of memory from the processor changes.
    
- General purpose and time-sharing applications are suitable for the UMA machines. In contrast, the appropriate application for NUMA is real-time and time-critical centric.
    
- The UMA based parallel systems work slower than the NUMA systems.
    
- When it comes to bandwidth UMA, have limited bandwidth. On the contrary, NUMA has bandwidth more than UMA.

<p align="center">
	<img src="https://i.postimg.cc/9QLgxR0h/Screenshot-2022-12-12-at-12-14-24-AM.jpg" width="500" alt="numa and uma">
</p>


### 7. Compare SIMD & MIMD Processors ? 
**Ans:-**

- **SIMD Processors**
	- Some of the earliest parallel computers such as the Illiac IV, MPP, DAP, CM-2, and MasPar MP-1 belonged to this class of machines.

	- Variants of this concept have found use in co-processing units such as the MMX units in Intel processors and DSP chips such as the Sharc.

	- SIMD relies on the regular structure of computations (such as those in image processing).

	- t is often necessary to selectively turn off operations on certain data items. For this reason, most SIMD programming paradigms allow for an ``activity mask'', which determines if a processor should participate in a computation or not.

- **MIMD Processors**
	- In contrast to SIMD processors, MIMD processors can execute different programs on different processors.

	- A variant of this, called single program multiple data streams (SPMD) executes the same program on different processors.

	- It is easy to see that SPMD and MIMD are closely related in terms of programming flexibility and underlying architectural support.

	- Examples of such platforms include current generation Sun Ultra Servers, SGI Origin Servers, multiprocessor PCs, workstation clusters, and the IBM SP.

<p align="center"> 
	<img src="https://i.postimg.cc/g2H6V8MY/Screenshot-2022-12-12-at-12-08-31-AM.jpg" width="500" alt="mimd"/>
</p>


## PDS - 3

### 1. Explain Task Interaction Graph with Example ?
**Ans:-** 
**1. Task Interaction Graph**

- Subtasks generally exchange data with others in a decomposition. For example, even in the trivial decomposition of the dense matrix - vector product, if the vector is not replicated across all tasks, they will have to communicate elements of the vector.

- The graph of tasks (nodes) and their interactions/data exchange (edges) is referred to as a task interaction graph.

- Note that task interaction graphs represent data dependencies, whereas task dependency graphs represent control dependencies.

**2. Example:-** Consider the problem of multiplying a sparse matrix A with a
vector b. The following observations can be made:

- As before, the computation of each element of the result vector can be viewed as an independent task.

- Unlike a dense matrix-vector product though, only non-zero elements of matrix A participate in the computation.

- If, for memory optimality, we also partition b across tasks, then one can see that the task interaction graph of the computation is identical to the graph of the matrix A (the graph for which A represents the adjacency structure).

<p align='center'>
	<img src="https://i.postimg.cc/vmNqHjxj/Screenshot-2022-12-12-at-1-14-43-AM.jpg" width="600" alt="Task ingegration graph"/>
</p>

### 2. Effect of Granularity on Performance ?
**Ans:-**
- Often, using fewer processors improves performance of parallel systems.

- Using fewer than the maximum possible number of processing elements to execute a parallel algorithm is called scaling down a parallel system.

- A naive way of scaling down is to think of each processor in the original case as a virtual processor and to assign virtual processors equally to scaled down processors.

- Since the number of processing elements decreases by a factor of n / p, the computation at each processing element increases by a factor of n / p.

- The communication cost should not increase by this factor since some of the virtual processors assigned to a physical processors might talk to each other. This is the basic reason for the improvement from building granularity.

### 3. Explain Degree of Concurrency & Critical Path Length in a PDS ?
**Ans:-**

**1. Degree of Concurrency:-**
- The number of tasks that can be executed in parallel is the degree of concurrency of a decomposition.

- Since the number of tasks that can be executed in parallel may change over program execution, the maximum degree of concurrency is the maximum number of such tasks at any point during execution. What is the maximum degree of concurrency of the database query examples?

- The average degree of concurrency is the average number of tasks that can be processed in parallel over the execution of the program. Assuming that each tasks in the database example takes identical processing time, what is the average degree of concurrency in each decomposition?

- The degree of concurrency increases as the decomposition becomes finer in granularity and vice versa.

**2. Critical Path Length:-**

- A directed path in the task dependency graph represents a sequence of tasks that must be processed one after the other.

- The longest such path determines the shortest time in which the program can be executed in parallel.

- The length of the longest path in a task dependency graph is called the critical path length.

### 4. Explain the various types of Task Decomposition Techniques used in PDS ?
**Ans:-**

**Task Decomposition Techniques :-**
While there is no single recipe that works for all problems, we present a set of commonly used techniques that apply to broad classes of problems.

These includes :
-  Recursive decomposition
-  Data decomposition
-  Exploratory decomposition
-  Speculative decomposition
-  Hybrid decomposition

1. **Recursive decomposition :-**
	- Generally suited to problems that are solved using the divide-and conquer strategy.
	
	- A given problem is first decomposed into a set of sub-problems.
	
	- These sub-problems are recursively decomposed further until a desired granularity is reached.

	- **Example :-**
	<p align="center">
    <img src="https://i.postimg.cc/ZqwR9PJX/Screenshot-2022-12-12-at-1-26-38-AM.jpg" width="600" alt="Recursive Decomposition">
	</p>

	In this example, once the list has been partitioned around the pivot, each sublist can be processed concurrently (i.e., each sublist represents an independent subtask). This can be repeated recursively.

2. **Data decomposition :-**
	- Identify the data on which computations are performed.

	- Partition this data across various tasks.

	- This partitioning induces a decomposition of the problem.

	- Data can be partitioned in various ways - this critically impacts performance of a parallel algorithm

	- **Example :-**
	<p align="center">
		<img src="https://i.postimg.cc/nrGwZ18w/Screenshot-2022-12-12-at-1-29-25-AM.jpg" width="600" alt="data decomposition" />
	</p>

3. **Exploratory decomposition :-**
	
	- In many cases, the decomposition of the problem goes hand-in hand with its execution.
	
	- These problems typically involve the exploration (search) of a state space of solutions.

	- Problems in this class include a variety of discrete optimization problems (0/1 integer programming, QAP, etc.), theorem proving, game playing, etc.

4. **Speculative decomposition :-**

	- In some applications, dependencies between tasks are not known a priori.

	- For such applications, it is impossible to identify independent tasks.

	- There are generally two approaches to dealing with such applications: conservative approaches, which identify independent tasks only when they are guaranteed to not have dependencies, and, optimistic approaches, which schedule tasks even when they may potentially be erroneous.
	
	- Conservative approaches may yield little concurrency and optimistic approaches may require roll-back mechanism in the case of an error.

5. **Hybrid decomposition :-**
Often, a mix of decomposition techniques is necessary for decomposing a problem. Consider the following examples:
	- In quicksort, recursive decomposition alone limits concurrency (Why?). A mix of data and recursive decompositions is more desirable.

	- In discrete event simulation, there might be concurrency in task processing. A mix of speculative decomposition and data decomposition may work well.

	- Even for simple problems like finding a minimum of a list of numbers, a mix of data and recursive decomposition works well.

### 5. How Task Characteristics impacts on Parallel Algorithm Performance ?
**Ans:-**

**Characteristics of Tasks :**
Once a problem has been decomposed into independent tasks, the characteristics of these tasks critically impact choice and performance of parallel algorithms. Relevant task characteristics include:
- Task generation.
- Task sizes.
- Size of data associated with tasks.

1. **Task Generation :-**
	- **Static task generation:** Concurrent tasks can be identified a-priori. Typical matrix operations, graph algorithms, image processing applications, and other regularly structured problems fall in this class. These can typically be decomposed using data or recursive decomposition techniques.
	- **Dynamic task generation:** Tasks are generated as we perform computation. A classic example of this is in game playing - each 15 puzzle board is generated from the previous one. These applications are typically decomposed using exploratory or speculative decompositions.

2. **Task Sizes:-**
	- Task sizes may be uniform (i.e., all tasks are the same size) or non-uniform.

	- Non-uniform task sizes may be such that they can be determined (or estimated) a-priori or not.

	- Examples in this class include discrete optimization problems, in which it is difficult to estimate the effective size of a state space.


3. **Size of data associated with tasks:-**
	- The size of data associated with a task may be small or large when viewed in the context of the size of the task.

	- A small context of a task implies that an algorithm can easily communicate this task to other processes dynamically (e.g., the 15 puzzle).

	- A large context ties the task to a process, or alternately, an algorithm may attempt to reconstruct the context at another processes as opposed to communicating the context of the task (e.g., 0/1 integer programming).

**Characteristics of Task Interactions:** Tasks may communicate with each other in various ways. The associated dichotomy is:
- **Static interactions:** The tasks and their interactions are known a-priori. These are relatively simpler to code into programs.

- **Dynamic interactions:** The timing or interacting tasks cannot be determined a-priori. These interactions are harder to code, especitally, as we shall see, using message passing APIs.

- **Regular interactions:** There is a definite pattern (in the graph sense) to the interactions. These patterns can be exploited for efficient implementation.

- **Irregular interactions:** Interactions lack well-defined topologies

## PDS - 4

### 1. Briefly describe One to All Broadcasting and All to One Reduction ?
**Ans:-**

**One to All Broadcast and All to One Reduction :-**

- One processor has a piece of data (of size m) it needs to send to everyone.

- The dual of one-to-all broadcast is all-to-one reduction.

- In all-to-one reduction, each processor has m units of data. These data items must be combined piece-wise (using some associative operator, such as addition or min), and the result made available at a target processor.

<p align="center">
	<img src="https://i.postimg.cc/SNVF0cpv/Screenshot-2022-12-12-at-1-56-24-AM.jpg"  width="600" alt="One to all and all to one" />
	<p>
		<i>One-to-all broadcast and all-to-one reduction among processors.</i>
	</p>
</p>

**One to All Broadcast and All to One Reduction on Rings:-**

- Simplest way is to send p-1 messages from the source to the other p-1 processors - this is not very efficient.

- Use recursive doubling: source sends a message to a selected processor. We now have two independent problems derined over halves of machines.

- Reduction can be performed in an identical fashion by inverting the process.

**One to All Boradcast :-** 

<p align="center">
	<img src="https://i.postimg.cc/MG5zdgpv/Screenshot-2022-12-12-at-1-52-22-AM.jpg" width="500" alt="one to all" />
</p>

One-to-all broadcast on an eight-node ring. Node 0 is the source of the broadcast. Each message transfer step is shown by a numbered, dotted arrow from the source of the message to its destination. The number on an arrow indicates the time step during which the message is transferred.

**All to One Reduction :-**

<p align="center">
	<img src="https://i.postimg.cc/dVmFVgd4/Screenshot-2022-12-12-at-1-52-39-AM.jpg" width="500" alt="all to one" />
</P>

Reduction on an eight-node ring with node 0 as the destination of the reduction.

## PDS - 5

### 1. Explain the Performance Matrices, Total Parallel Overhead, Speed-Up and Efficiency of a Parallel System ?
**Ans:-**

1. **Performance Metrics for Parallel Systems: Execution Time:**
	- Serial runtime of a program is the time elapsed between the beginning and the end of its execution on a sequential computer.

	- The parallel runtime is the time that elapses from the moment the first processor starts to the moment the last processor finishes execution.

	- We denote the serial runtime by and the parallel runtime by TP

2. **Performance Metrics for Parallel Systems: Total Parallel Overhead:**
	- Let $T_{all}$ be the total time collectively spent by all the processing elements.

	- $T_S$ is the serial time.

	- Observe that $T_{all} - T_S$ is then the total time spend by all processors combined in non-useful work. This is called the total overhead.

	- The total time collectively spent by all the processing elements Tall = p TP (p is the number of processors).

	- The overhead function $T_o$ is therefore given by $T_o = p T_P – T_S$

3. **Speedup:**
	- Speedup (S) is the ratio of the time taken to solve a problem on a single processor to the time required to solve the same problem on a parallel computer with p identical processing elements.

4. **Performance Metrics: Efficiency:**

	- Efficiency is a measure of the fraction of time for which a processing element is usefully employed.

	- Mathematically, it is given by  $\Rightarrow E = s/p$
	
	- Following the bounds on speedup, efficiency can be as low as 0 and as high as 1.
