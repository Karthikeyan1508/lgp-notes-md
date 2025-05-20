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











