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






