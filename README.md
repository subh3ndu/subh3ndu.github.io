# Parallel and Distributed Systems

## Internal - 1

### 1. Briefly Describe Superscalar Processor ?
Ans:- 

- A superscalar processor is created to produce an implementation rate of more than one instruction per clock cycle for a single sequential program. 

- Superscalar processor design defines as a set of methods that enable the central processing unit (CPU) of a computer to manage the throughput of more than one instruction per cycle while performing a single sequential program.

- While there is not a global agreement on the interpretation, superscalar design techniques involve parallel instruction decoding, parallel register renaming, speculative execution, and out-of-order execution. 

- These techniques are usually employed along with complementing design techniques including pipelining, caching, branch prediction, and multi-core in current microprocessor designs.

- Superscalar processor emerged in three consecutive phases as first, the idea was conceived, then a few architecture proposals and prototype machines appeared, and finally, in the last phase, the commercial products reached the market.

<p align="center"> 
	<img src="https://www.tutorialspoint.com/assets/questions/media/54372/superscalar_processor.jpg" />
</p>

### 2. Compare the NUMA to UMA Architecture ?
Ans:-

| **Basis for comparison**  | **UMA**                                       | **NUMA**                                             |
| ------------------------- | --------------------------------------------- | ---------------------------------------------------- |
| **Definition**            | Uses a single memory controller               | Multiple memory controller                           |
| **Type of buses used**    | Single, multiple and crossbar.                | Tree and hierarchical                                |
| **Memory accessing time** | Equal                                         | Changes according to the distance of microprocessor. |
| **Suitable for**          | General purpose and time-sharing applications | Real-time and time-critical applications             |
| **Speed**                | Slower                                        | Faster                                               |
| **Bandwidth**                | Limited                                       | More than UMA                                        |

### 3. What is Cache Coherence ? Explain its activities in a Multiprocessor System ? 
Ans:-

- **Cache Coherence:-**
	- In a multiprocessor system, data inconsistency may occur among adjacent levels or within the same level of the memory hierarchy. 

	- In a shared memory multiprocessor with a separate cache memory for each processor, it is possible to have many copies of any one instruction operand: one copy in the main memory and one in each cache memory. When one copy of an operand is changed, the other copies of the operand must be changed also. 

	- Example : Cache and the main memory may have inconsistent copies of the same object As multiple processors operate in parallel, and independently multiple caches may possess different copies of the same memory block, this creates a cache coherence problem.

-  **Activities in a Multiprocessor System:-**

	- If a processor just reads a value once and does not need it again, an update protocol may generate significant overhead.

	- If two processors make interleaved test and updates to a variable, an update protocol is better.

	- Both protocols suffer from false sharing overheads (two words that are not shared, however, they lie on the same cache line).

	- Most current machines use invalidate protocols

### 4. Explain SIMD & MIMD Processor ?
Ans:-

- **SIMD Processors**
	- Some of the earliest parallel computers such as the Illiac IV, MPP, DAP, CM-2, and MasPar MP-1 belonged to this class of machines.

	- Variants of this concept have found use in co-processing units such as the MMX units in Intel processors and DSP chips such as the Sharc.

	- SIMD relies on the regular structure of computations (such as those in image processing).

	- t is often necessary to selectively turn off operations on certain data items. For this reason, most SIMD programming paradigms allow for an ``activity mask'', which determines if a processor should participate in a computation or not.

<p align="center"> 
	<img src="https://media.geeksforgeeks.org/wp-content/uploads/20190602175031/Untitled-Diagram-90.png" alt="smid" />
</p>

- **MIMD Processors**
	- In contrast to SIMD processors, MIMD processors can execute different programs on different processors.

	- A variant of this, called single program multiple data streams (SPMD) executes the same program on different processors.

	- It is easy to see that SPMD and MIMD are closely related in terms of programming flexibility and underlying architectural support.

	- Examples of such platforms include current generation Sun Ultra Servers, SGI Origin Servers, multiprocessor PCs, workstation clusters, and the IBM SP.

<p align="center"> 
	<img src="https://media.geeksforgeeks.org/wp-content/uploads/20190602175050/Untitled-Diagram-911.png" alt="mimd"/>
</p>


## Internal - 2

### Briefly Describe One-All Broadcast and All-One Broadcast Reduction ??
