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





