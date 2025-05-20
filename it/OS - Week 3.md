# Process and Memory Management
## Process Scheduling
Process scheduling refers to the function performed by the process manager in which the currently running process is removed from the CPU, and another process is selected for execution based on a specific scheduling strategy.
It is a core component of multiprogramming operating systems. These systems support multiple processes being loaded into memory simultaneously, and allow them to share the CPU by using time-multiplexing techniques.

## Categories of Process Scheduling
CPU scheduling algorithms are classified into two main categories:
### 1. Non-Preemptive Scheduling
- Once a process is assigned the CPU, it retains control until it either completes execution or moves to a waiting state (e.g., for I/O).
- The CPU cannot be forcibly taken away from a running process.
- Context switching occurs only after the process voluntarily gives up the CPU.

*Example Algorithms:*
- First-Come, First-Served (FCFS)
- Shortest Job First (SJF – Non-preemptive)
- Priority Scheduling (Non-preemptive)
### 2. Preemptive Scheduling
- The OS can interrupt a running process and reassign the CPU to another process, typically based on priority or time-slicing.
- A process may be preempted and moved from the running state to the ready state if:
    - A higher-priority process arrives
    - Its time slice expires
      
*Example Algorithms:*
- Round Robin (RR)
- Shortest Remaining Time First (SRTF)
- Priority Scheduling (Preemptive)


## Process Scheduling in Operating Systems
### Process Scheduling Queues

The *Operating System* (OS) uses *scheduling queues* to manage processes based on their current state. It stores each process’s *Process Control Block (PCB)* in the appropriate queue. When a process changes state, its PCB is *moved* from one queue to another.

#### Key Scheduling Queues:

1. *Job Queue*

   - Contains all processes that are present in the system.

2. *Ready Queue*

   -  Holds all processes that are *loaded in main memory* and are *ready for execution*.
   - Every *newly created process* is first placed here.

3. *Device Queues*

   - Contains processes that are *blocked* and are *waiting for I/O devices* to become available.

The OS can use various scheduling policies (e.g., *FIFO, **Round Robin, **Priority*) to manage these queues.

###  Two-State Process Model

This simplified model defines only *two states* for a process:

| *State*       | *Description*                                                                                                           |
| --------------- | ------------------------------------------------------------------------------------------------------------------------- |
| *Running*     | The process is currently using the CPU. When created, a process can directly start in this state.                         |
| *Not Running* | The process is *waiting in a queue* for its turn to execute. Interrupted or blocked processes are placed in this state. |

- *Dispatcher*: A system component that handles the transition of processes from *waiting to running* by selecting the next process to execute.
https://www.tutorialspoint.com/operating_system/images/queuing_diagram.jpg

### Types of Schedulers

Schedulers are *special system software* that make decisions about which processes run and when. They are classified into:

## 1. Long-Term Scheduler (Job Scheduler)

- Role: Determines which processes are admitted into the system.
- Function: Selects jobs from the job pool and loads them into memory.
- Goal: Maintain a balanced mix of CPU-bound and I/O-bound processes.
- Used When: A process moves from New → Ready state.
- Note: May be absent or minimal in time-sharing systems.



## 2. Short-Term Scheduler (CPU Scheduler)

- Role: Selects a process from the ready queue for execution.
- Function: Allocates the CPU to one of the ready processes.
- Frequency: Runs very frequently and must be fast and efficient.
- Also Called: Dispatcher



## 3. Medium-Term Scheduler

- Role: Manages swapped-out processes.
- Function: Temporarily removes processes from main memory to reduce the degree of multiprogramming.
- Swapping: Moves blocked/suspended processes to secondary storage and brings them back when needed.

  
###  Comparison: Long-Term vs Short-Term vs Medium-Term Scheduler

| S.No | Long-Term Scheduler          | Short-Term Scheduler    | Medium-Term Scheduler              |
| ---- | ---------------------------- | ----------------------- | ---------------------------------- |
| 1    | Job Scheduler                | CPU Scheduler           | Swapping Scheduler                 |
| 2    | Slower                       | Fastest                 | Medium speed                       |
| 3    | Controls multiprogramming    | Less control            | Reduces multiprogramming           |
| 4    | Often absent in time-sharing | Minimal in time-sharing | Common in time-sharing systems     |
| 5    | Loads processes into memory  | Picks from ready queue  | Reintroduces swapped-out processes |

##  Process Scheduling Algorithms in Operating Systems
A Process Scheduler is a system program that decides the order in which processes are assigned to the CPU for execution, based on specific scheduling strategies. These strategies aim to optimize CPU usage, reduce waiting time, and improve system responsiveness.

### Types of Scheduling Algorithms
There are six commonly used CPU scheduling algorithms:

1.First-Come, First-Served (FCFS) Scheduling

2.Shortest-Job-Next (SJN) Scheduling (also known as Shortest Job First or SJF)

3.Priority Scheduling

4.Shortest Remaining Time (SRT) Scheduling

5.Round Robin (RR) Scheduling

6.Multi-Level Queue Scheduling

### 1.First Come First Serve (FCFS) Scheduling
- FCFS is the simplest CPU scheduling algorithm.
- Processes are executed in the order they arrive in the ready queue.
- It works on the First In, First Out (FIFO) principle.
- Once a process starts executing, it cannot be preempted (i.e., it’s non-preemptive).

*Key Characteristics:*
| Feature            | Description                                                     |
| ------------------ | --------------------------------------------------------------- |
| **Type**           | Non-preemptive                                                  |
| **Implementation** | Uses a **FIFO queue**                                           |
| **Fairness**       | All processes are treated equally                               |
| **Complexity**     | Very easy to implement                                          |
| **Performance**    | Poor when short processes wait behind long ones (convoy effect) |
| **Use Case**       | Suitable where simplicity is more important than performance    |

*Example:*
Assume we have the following processes with their Arrival Time (AT) and Burst Time (BT):
| Process | Arrival Time | Burst Time |
| ------- | ------------ | ---------- |
| P0      | 0            | 5          |
| P1      | 1            | 3          |
| P2      | 2            | 8          |
| P3      | 3            | 6          |

*Gantt Chart:*
| P0  | P1  | P2   | P3   |
|-----|-----|------|------|
| 0   | 5   | 8    | 16   | 22

*Calculation:*
| Process | AT | BT | CT | TAT = CT - AT | WT = TAT - BT |
| ------- | -- | -- | -- | ------------- | ------------- |
| P0      | 0  | 5  | 5  | 5             | 0             |
| P1      | 1  | 3  | 8  | 7             | 4             |
| P2      | 2  | 8  | 16 | 14            | 6             |
| P3      | 3  | 6  | 22 | 19            | 13            |

*Final Metrics:*
- Total Turn Around Time (TAT) = 5 + 7 + 14 + 19 = 45
- Average Turn Around Time = 45 / 4 = 11.25 units
- Total Waiting Time (WT) = 0 + 4 + 6 + 13 = 23
- Average Waiting Time = 23 / 4 = 5.75 units

### 2.Shortest Job Next (SJN)
- This is also known as shortest job first, or SJF
- This is a non-preemptive, pre-emptive scheduling algorithm.
- Best approach to minimize waiting time.
- Easy to implement in Batch systems where required CPU time is known in advance.
- Impossible to implement in interactive systems where required CPU time is not known.
- The processer should know in advance how much time process will take.

*Key Characteristics:*
| Feature/Aspect           | Description                                                                  |
| ------------------------ | ---------------------------------------------------------------------------- |
| **Type**                 | Non-Preemptive (Also has a Preemptive variant called SRTF)                   |
| **Basic Principle**      | Process with the shortest CPU burst time is scheduled next                   |
| **Implementation Basis** | Based on burst time (execution time); needs to be known in advance           |
| **Queue Type**           | Not based on FIFO; jobs are sorted by burst time                             |
| **Preemption**           | Not allowed (in non-preemptive SJF)                                          |
| **Best Case Scenario**   | When short processes arrive frequently — very low average waiting time       |
| **Worst Case Scenario**  | When long processes arrive early, but are delayed by short ones (starvation) |
| **Starvation**           | **Yes**, long processes can suffer indefinite postponement                   |
| **Suitable For**         | **Batch systems** where burst time of processes is known beforehand          |
| **Not Suitable For**     | **Interactive systems** where burst time cannot be predicted                 |
| **Performance**          | **Best average waiting time** among all non-preemptive algorithms            |
| **Complexity**           | Moderate – requires burst time estimation or prediction                      |


*Example:*
Assume we have the following processes with their Arrival Time (AT) and Burst Time (BT):
| Process | Arrival Time (AT) | Burst Time (BT) |
| ------- | ----------------- | --------------- |
| P0      | 0                 | 5               |
| P1      | 1                 | 3               |
| P2      | 2                 | 8               |
| P3      | 3                 | 6               |

*Gantt Chart:*
| P0  | P1  | P3  | P2   |
|-----|-----|-----|------|
| 0   | 5   | 8   | 14   | 22


*Calculation:*
| Process | AT | BT | CT | TAT = CT - AT | WT = TAT - BT |
| ------- | -- | -- | -- | ------------- | ------------- |
| P0      | 0  | 5  | 5  | 5             | 0             |
| P1      | 1  | 3  | 8  | 7             | 4             |
| P3      | 3  | 6  | 14 | 11            | 5             |
| P2      | 2  | 8  | 22 | 20            | 12            |

*Final Metrics:*
- Total Turn Around Time (TAT) = 5 + 7 + 11 + 20 = 43
- Average Turn Around Time = 43 / 4 = 10.75 units
- Total Waiting Time (WT) = 0 + 4 + 5 + 12 = 21
- Average Waiting Time = 21 / 4 = 5.25 units

### 3.Priority Based Scheduling (Non-Preemptive)
- Priority scheduling is a scheduling method in which each process is assigned a priority, and the CPU is allocated to the process with the highest priority. If two processes have the same priority, FCFS is used to break the tie.
- Lower number = lower priority (here, 1 is the lowest, 3 is highest).
- Non-preemptive: Once the CPU is given to a process, it runs till completion.
- Priority can be decided based on memory requirements, time requirements or any other resource requirement.

*Key Characteristics:*
|   Feature                     |   Description                                                                |
| ----------------------------- | ---------------------------------------------------------------------------- |
| **Algorithm Type**            | Non-Preemptive                                                               |
| **Scheduling Basis**          | Process Priority (Higher number = Higher priority, or vice versa as defined) |
| **Execution Order**           | Highest priority process executes first                                      |
| **Tie-breaker**               | First-Come, First-Served (FCFS) among processes with same priority           |
| **Implementation Simplicity** | Simple if priority values are known                                          |
| **Starvation**                | Possible for low-priority processes (can be avoided using aging technique)   |
| **Preemption**                |  Not allowed in this version                                                 |
| **Fairness**                  | Not always fair; may favor high-priority tasks consistently                  |
| **Waiting Time**              | Can be low for high-priority tasks; high for low-priority tasks              |
| **Use Case**                  | Batch systems, system-critical task execution where priority is well defined |

*Example:*
Assume we have the following processes with their Arrival Time (AT) and Burst Time (BT):
| Process | Arrival Time (AT) | Burst Time (BT) | Priority |
| ------- | ----------------- | --------------- | -------- |
| P0      | 0                 | 5               | 1        |
| P1      | 1                 | 3               | 2        |
| P2      | 2                 | 8               | 1        |
| P3      | 3                 | 6               | 3        |

*Gantt Chart:*
| P0  | P3  | P1  | P2   |
|-----|-----|-----|------|
| 0   | 5   | 11  | 14   | 22 |


*Calculation:*
| Process | AT | BT | Priority | CT | TAT = CT - AT | WT = TAT - BT |
| ------- | -- | -- | -------- | -- | ------------- | ------------- |
| P0      | 0  | 5  | 1        | 5  | 5             | 0             |
| P3      | 3  | 6  | 3        | 11 | 8             | 2             |
| P1      | 1  | 3  | 2        | 14 | 13            | 10            |
| P2      | 2  | 8  | 1        | 22 | 20            | 12            |


*Final Metrics:*
Average Waiting Time (AWT): AWT = (0 + 2 + 10 + 12) / 4 = 24 / 4 = 6
Average Turnaround Time (ATAT):ATAT = (5 + 8 + 13 + 20) / 4 = 46 / 4 = 11.5

### 4.Shortest Remaining Time
- Shortest Remaining Time (SRT) is the preemptive version of the Shortest Job Next (SJN) scheduling algorithm.
- In SRT, the CPU is always assigned to the process that has the least remaining burst time among all ready processes.
- If a new process arrives with a shorter remaining time than the current process, the current process is preempted.

*Key Characteristics:*
| Feature              | Description                                                              |
| -------------------- | ------------------------------------------------------------------------ |
| **Type**             | Preemptive                                                               |
| **Criteria**         | Shortest Remaining Burst Time                                            |
| **Best Suited For**  | Batch systems where process burst times are known in advance             |
| **Not Suitable For** | Interactive systems (CPU burst time is usually unknown)                  |
| **Fairness**         | Favors short jobs, may cause starvation for longer processes             |
| **Performance**      | Minimizes average waiting and turnaround time when burst times are known |

*Example:*
Assume we have the following processes with their Arrival Time (AT) and Burst Time (BT):
| Process | Arrival Time | Burst Time |
| ------- | ------------ | ---------- |
| P0      | 0            | 8          |
| P1      | 1            | 4          |
| P2      | 2            | 2          |
| P3      | 3            | 1          |

*Gantt Chart:*
| P0 | P1 | P2 | P3 | P2 | P1 | P1 | P1 | P0 | P0 | P0 | P0 |
|----|----|----|----|----|----|----|----|----|----|----|----|
| 0  | 1  | 2  | 3  | 4  | 5  | 6  | 7  | 8  | 9  | 10 | 11 | 12 |


*Calculation:*
| Process | Arrival | Burst | Completion | Turnaround (CT - AT) | Waiting (TAT - BT) |
| ------- | ------- | ----- | ---------- | -------------------- | ------------------ |
| P0      | 0       | 8     | 12         | 12 - 0 = 12          | 12 - 8 = 4         |
| P1      | 1       | 4     | 7          | 7 - 1 = 6            | 6 - 4 = 2          |
| P2      | 2       | 2     | 4          | 4 - 2 = 2            | 2 - 2 = 0          |
| P3      | 3       | 1     | 4          | 4 - 3 = 1            | 1 - 1 = 0          |

*Final Metrics:*
Average Waiting Time (AWT): (4 + 2 + 0 + 0) / 4 = 1.5
Average Turnaround Time (ATAT):   (12 + 6 + 2 + 1) / 4 = 5.25

### 5.Round Robin (RR) Scheduling
- Type: Preemptive scheduling algorithm.
- How it works:
    - Each process is assigned a fixed time slice called a time quantum (or time slice).
    - The CPU executes a process for the quantum time or until the process finishes, whichever is earlier.
    - If the process is not finished, it is preempted and moved to the end of the ready queue.
    - The next process in the ready queue gets the CPU for the next quantum.
- Context Switching: Saves the current process state and switches CPU to the next process.
- Use case: Widely used in time-sharing systems to ensure fair CPU time among processes.

*Example:*
Assume we have the following processes with their Arrival Time (AT) and Burst Time (BT):
| Process | Arrival Time | Burst Time |
| ------- | ------------ | ---------- |
| P0      | 0            | 5          |
| P1      | 1            | 3          |
| P2      | 2            | 8          |
| P3      | 3            | 6          |

*Gantt Chart:*
| P0 | P1 | P2 | P3 | P0 | P2 | P3 | P2 | P2 | P2 | P2 | P3 |
|----|----|----|----|----|----|----|----|----|----|----|----|
| 0  | 4  | 7  | 11 | 15 | 16 | 20 | 20 | 24 | 28 | 32 | 34 |

*Calculation:*
| Process | Arrival Time | Burst Time | Completion Time | Turnaround Time | Waiting Time |
| ------- | ------------ | ---------- | --------------- | --------------- | ------------ |
| P0      | 0            | 5          | 16              | 16              | 11           |
| P1      | 1            | 3          | 7               | 6               | 3            |
| P2      | 2            | 8          | 20              | 18              | 10           |
| P3      | 3            | 6          | 22              | 19              | 13           |

*Final Metrics:*
Average Waiting Time (AWT): (11 + 3 + 10 + 13) / 4 = 37 / 4 = 9.25
Average Turnaround Time (ATAT): (16 + 6 + 18 + 19) / 4 = 59 / 4 = 14.75

### 6.Multiple-Level Queues Scheduling
Multiple-level queues are not an independent scheduling algorithm. They make use of other existing algorithms to group and schedule jobs with common characteristics.
- Multiple queues are maintained for processes with common characteristics.
- Each queue can have its own scheduling algorithms.
- Priorities are assigned to each queue.
For example, CPU-bound jobs can be scheduled in one queue and all I/O-bound jobs in another queue. The Process Scheduler then alternately selects jobs from each queue and assigns them to the CPU based on the algorithm assigned to the queue.

# Process Synchronization
Process Synchronization is a fundamental concept in operating systems, ensuring that multiple processes or threads can execute concurrently without conflicting with each other or corrupting shared data.
###  Why Synchronization is Needed
In a multi-process system, processes often need to access shared resources (like memory, files, or variables). Without proper coordination, concurrent access can lead to:
- Inconsistent Data
- Data Loss
- Deadlocks
  
Thus, synchronization mechanisms are essential to maintain data integrity, system stability, and process coordination.
*Definition*: Process Synchronization is the technique of coordinating the execution of processes so that they access shared resources in a safe and predictable way. It prevents problems like race conditions, where the system's behavior depends on the sequence or timing of uncontrollable events.

###Types of Processes Based on Synchronization
| Type                    | Description                                                                    |
| ----------------------- | ------------------------------------------------------------------------------ |
| **Independent Process** | Executes without affecting or being affected by other processes.               |
| **Cooperative Process** | Can interact with other processes, either affecting or being affected by them. |

## Conditions That Require Process Synchronization
Process synchronization becomes essential when multiple processes interact with shared resources. The following conditions particularly demand synchronization to ensure correct and reliable system behavior:
### Critical Section
https://www.geeksforgeeks.org/wp-content/uploads/gq/2015/06/critical-section-problem.png
- A Critical Section is a part of the code where shared resources (like variables, memory, or files) are accessed or modified.
- Key Requirement: Only one process should be allowed to execute its critical section at any point in time to avoid inconsistencies.
- Note: If there are no shared resources, synchronization mechanisms are not needed.
### Race Condition
- A Race Condition occurs when two or more processes attempt to access and update the shared resource simultaneously, and the final output depends on the order of execution.
- Without proper synchronization, this can lead to unexpected and incorrect results.
- Goal of Synchronization: Ensure that the execution order is controlled and only one process updates at a time.
### Preemption
- Preemption is when the operating system interrupts a currently running process to allocate CPU time to another.
- This is essential for multitasking, but it can lead to issues if the interrupted process hasn't finished accessing the shared resource.
- If synchronization isn't in place, the next process may read partial or inconsistent data, leading to system errors.

## Classical Inter-Process Communication (IPC) Problems
Classical IPC problems illustrate typical synchronization challenges in multi-process systems. These problems help in understanding how to manage shared resources, avoid race conditions, and prevent deadlocks using synchronization tools like semaphores.

### 1. Producer-Consumer Problem
*Scenario:*
- A Producer process generates data and places it into a shared buffer.
- A Consumer process takes data from this buffer and processes it.
- The buffer has limited capacity, which both processes must respect.
*Key Issues:*
- Buffer Overflow: Occurs when the producer tries to add data to a full buffer.
- Buffer Underflow: Occurs when the consumer tries to remove data from an empty buffer.
- Race Condition: Without synchronization, both may access the buffer simultaneously, leading to inconsistent data.
*Objective:*
Ensure that producers and consumers operate in coordination, such that:
- Producers wait when the buffer is full.
- Consumers wait when the buffer is empty.
*Solution:*  Use Semaphores for mutual exclusion and signaling between processes.

### 2.Readers-Writers Problem
*Scenario:*
- Multiple reader processes and writer processes access a shared data resource.
- Readers: Only read the data, no modifications.
- Writers: Modify the data.
*Key Challenges:*
- Multiple readers can read simultaneously without conflict.
- Only one writer should write at a time.
- No reader should read while a writer is writing to prevent data inconsistency.
*Objective:*
- Allow concurrent reads.
- Ensure exclusive write access.
- Prioritize based on specific scenarios.
*Solutions:*
- Readers Preference: Prioritize readers over writers.
- Writers Preference: Prioritize writers over readers.
- Fairness Approach: Treat both equally to avoid starvation.

### 3. Dining Philosophers Problem
*Scenario:*
- Five philosophers sit around a circular table with one fork between each pair.
- To eat, a philosopher needs both forks (left and right).
- After eating, the philosopher puts down the forks and resumes thinking.
*Key Challenges:*
- Deadlock: Each philosopher picks up their left fork and waits for the right, causing a circular wait.
- Starvation: Some philosophers may never get to eat if scheduling is unfair.
*Objective:*
- Ensure no deadlock.
- Ensure no starvation.
- Allow fair access to forks.
 *Solution:*  Use Semaphores or Monitors to coordinate fork access and avoid circular wait.

##Summary Table
| Problem             | Processes Involved | Key Issue                 | Common Solution          |
| ------------------- | ------------------ | ------------------------- | ------------------------ |
| Producer-Consumer   | Producer, Consumer | Buffer overflow/underflow | Semaphores (Full, Empty) |
| Readers-Writers     | Readers, Writers   | Data inconsistency        | Reader/Writer preference |
| Dining Philosophers | 5 Philosophers     | Deadlock, Starvation      | Semaphores, Mutexes      |

### Advantages of Process Synchronization
1.Ensures data consistency and integrity

2.Avoids race conditions

3.Prevents inconsistent data due to concurrent access

4.Supports efficient and effective use of shared resources

### Disadvantages of Process Synchronization
1.Adds overhead to the system

2.This can lead to performance degradation

3.Increases the complexity of the system

4.Can cause deadlock if not implemented properly.

## Memory Allocation Techniques:
### Contiguous Memory Allocation
Contiguous Memory Allocation is a memory management technique where each process is assigned a single, continuous block of memory in the main memory. This approach is simple and allows for fast access because memory addresses can be easily calculated using a base address and an offset. Since the allocated memory is contiguous, it ensures better performance in terms of access time and CPU efficiency.

https://static.takeuforward.org/content/-hMawFssQ

However, contiguous memory allocation has several limitations. One major issue is fragmentation. There are two types of fragmentation associated with this method. External fragmentation occurs when there is enough total free memory, but it is scattered in small, non-contiguous blocks, preventing allocation of large memory blocks to new processes. Internal fragmentation, on the other hand, happens when the memory block allocated to a process is slightly larger than what is required, leading to wasted space within the allocated block.
To manage memory more effectively under contiguous allocation, operating systems use different strategies to place processes into memory.
*First Fit:*
- Allocates the first available block that is large enough.
*Best Fit:*
- Allocates the smallest block that is sufficient.
- Minimizes internal fragmentation but may lead to more external fragmentation.
*Worst Fit:*
- Allocates the largest available block.
- Leaves largest possible remaining fragment.
Despite its simplicity, contiguous memory allocation is not flexible enough for dynamic environments where processes frequently enter and leave the system. It may require memory compaction to combine scattered free memory blocks, which adds overhead. Thus, while effective in systems with static memory requirements, contiguous allocation becomes inefficient in modern multiprogramming environments due to its poor handling of fragmentation and limited scalability.

### Paging
Paging is a memory management technique that overcomes the limitations of contiguous memory allocation by dividing both the physical memory and the logical memory into fixed-size blocks. The physical memory is divided into blocks called frames, while the logical memory used by processes is divided into blocks of the same size called pages. When a process is loaded into memory, its pages can be stored in any available memory frames, eliminating the requirement for contiguous physical memory. A key component of this system is the page table, which keeps track of the mapping between each page of the process and the corresponding frame in physical memory.

https://static.takeuforward.org/content/-vgiSDSEx

This scheme allows the physical address space of a process to be non-contiguous, thereby solving the issue of external fragmentation. It also simplifies memory allocation, as the system no longer needs to find large contiguous blocks of memory, making memory usage more efficient and management more straightforward.

The page table is a crucial data structure in paging. Each entry in the page table corresponds to a page in the process’s logical address space and contains the address of the frame in physical memory where that page is stored. There are various types of page table structures, including single-level, multi-level, and inverted page tables. While a single-level page table is simple and easy to implement, it can become quite large and inefficient when dealing with extensive address spaces.
*Advantages:*
- Avoids gaps between allocated memory blocks, ensuring efficient use of available memory.
- Pages can be placed anywhere in physical memory, simplifying memory allocation.
- Fixed-size pages mean that memory allocation does not require complex algorithms.
- Allows larger programs to run even with limited physical memory.
- Virtual memory allows parts of a program to be stored on disk and brought into memory as needed.
*Disadvantages:*        
- Each process requires a page table, which can consume a lot of memory for large address spaces.
- Each memory access requires a lookup in the page table, which can add delay.
- Unused space in the last page of a process can lead to internal fragmentation.

###  Segmentation
Segmentation is a memory management technique where a process’s memory is divided into variable-sized segments, each representing a logical unit such as a function, array, or data structure. Unlike paging, segmentation aligns with the logical structure of programs by allowing segments to vary in length, based on their content and purpose.

In this scheme, each segment is identified by a segment number and has an associated length. Memory addresses within a segment are determined using an offset from the segment’s base address. The system uses a segment table to keep track of each segment’s base address and its length, enabling efficient translation of logical addresses to physical addresses.

https://static.takeuforward.org/content/-mq-95-02

Segmentation supports enhanced modularity and protection. Since each segment represents a logical division of the program, it allows for independent access control and sharing. This makes segmentation useful for improving program structure, readability, and overall security by assigning different permissions to different segments.

Despite its benefits, segmentation has some limitations. It can suffer from external fragmentation, since segments are of variable size and need to be allocated in contiguous memory blocks. Also, the memory management algorithms needed for segment allocation and deallocation are more complex than those used in paging.

## Virtual Memory: Page Tables, TLB (Translation Lookaside Buffer)
Virtual memory is a memory management technique that uses a portion of the hard disk as if it were RAM, creating the illusion of a larger memory space. It allows computers to run programs that are larger than the available physical memory, and to run multiple programs at once without requiring all of them to fit in RAM simultaneously.

### Page Tables
*Page Tables:*
- Page tables are used to map virtual addresses to physical addresses. 
- They are maintained by the operating system. 
- When a virtual address is accessed, the CPU uses the page table to find the corresponding physical address.

*Translation Lookaside Buffer (TLB):*
- The TLB is a high-speed cache that stores recent translations between virtual and physical addresses.
- It acts as an address-translation cache.
- By storing these translations, the TLB reduces the time it takes to translate virtual addresses to physical addresses.
- When a virtual address is accessed, the TLB first checks if the translation is already stored in the cache.
- If the translation is found (a TLB hit), the physical address can be retrieved quickly.
- If the translation is not found (a TLB miss), the page table must be consulted to find the physical address.
- The TLB is updated with the new translation after a TLB miss.


