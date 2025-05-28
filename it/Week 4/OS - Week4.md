# Understanding Threads and Processes in Multithreaded Programming

In modern computing, both threads and processes are fundamental concepts in the execution of programs. While traditionally the term process encapsulated everything—address space, execution state, and resources—modern operating systems distinguish between processes and threads, especially in multithreaded environments.

## What is a Thread?

A thread is an independent flow of control that operates within the same address space as other threads in a process. Threads are sometimes referred to as lightweight processes, especially in operating systems where they are used to implement concurrent execution.

Each thread has its own:
	• Stack
	• Program counter
	• Registers
	• Scheduling properties (like priority)
	• Thread-specific data (e.g., errno)

Despite their independence in execution, threads share the following resources with other threads in the same process:
	• Code section
	• Data section
	• Open files
	• Signal actions
	• Address space
	• Environment variables

Because of this shared environment, changes made by one thread (such as closing a file) are visible to all other threads within the same process.

## What is a Process?

A process is a higher-level execution unit that provides the execution environment for threads. It acts as a container for resources and execution state. In a multithreaded system, a process is considered the changeable entity that holds:
	• Process ID, group ID
	• User ID, group ID
	• Environment variables
	• Working directory
	• File descriptors
	• Signal handling information
	• IPC tools (e.g., pipes, message queues, semaphores, shared memory)

A process provides the common address space and resources that all its threads share.

## Thread vs Process: Key Differences

Here is the formatted solid table:

Feature	Thread	Process
Definition	Schedulable unit of execution	Execution environment for threads
Memory Space	Shares address space with other threads in the same process	Has its own memory space
Creation Overhead	Lower	Higher
Resource Sharing	Shares resources like files, data, and code	Resources are independent across processes
Scheduling	Managed individually by OS (kernel or user level)	Scheduled by OS
Communication	Uses shared memory (efficient)	Requires inter-process communication (more complex)

### Initial Thread

When a new process is created, a single initial thread is created automatically. This thread:
	• Runs the main() function in C/C++
	• Ensures backward compatibility with older single-threaded programs
	• Has special invisible properties for binary compatibility

## Thread Models

Thread implementations vary across operating systems:
	• User Threads: Managed entirely by a user-level threads library. The OS kernel is unaware of their existence.
	• Kernel Threads: Managed directly by the OS kernel and scheduled like regular processes.
	• Hybrid (One-to-One, Many-to-One, Many-to-Many Models):
	• 1:1: Each user thread maps to one kernel thread.
	• M:1: Many user threads map to a single kernel thread.
	• M:N: Many user threads are mapped to a pool of kernel threads.

The way user threads map to kernel threads is known as the thread model.

### Modularity in Multithreaded Programming

Programs are often built from modular components that interact to provide functionality. Threads make modular programming more efficient because:
	• Threads can perform distinct tasks simultaneously, each in its own logical section.
	• They share the same memory, making data sharing between modules simple and fast.
	• Synchronization tools like mutexes and condition variables help ensure data integrity across modules.

This modular design promotes separation of concerns—each thread can manage one functional part of the program while communicating only when necessary.

## Threads Library (pthreads)

Many systems use the POSIX Threads (pthreads) library to manage multithreading. It offers:
	• An object-oriented API, where threads and synchronization primitives are manipulated as opaque objects.
	• A naming convention, where all identifiers start with pthread_, such as pthread_create, pthread_mutex_lock.

Example:

pthread_t tid;
pthread_create(&tid, NULL, my_function, NULL);

The pthreads implementation files handle all the underlying system calls and thread management functionalities.

# Synchronization

## Race Condition?

A race condition occurs when the outcome of a program depends on the non-deterministic timing or sequence of events. In multithreaded or multiprocess systems, this typically arises when two or more threads access shared resources concurrently without proper synchronization.
	• The final result depends on the order of execution of threads.
	• This behavior is unpredictable and often hard to detect and debug.
	• Race conditions generally occur inside critical sections.

Example: Two threads withdrawing money from a bank account at the same time may both read the same balance and deduct the same amount, resulting in an incorrect final balance.

Preventing Race Conditions
	• Use atomic operations in the critical section.
	• Implement thread synchronization mechanisms such as locks, mutexes, or semaphores.

## Critical Section?

A critical section is a portion of code that accesses shared resources (like memory, files, or devices) and must not be executed by more than one thread at the same time.

### Typical Structure of a Critical Section:

do {
    // Entry Section
    // Acquire lock or check conditions

    // Critical Section
    // Access or modify shared resources

    // Exit Section
    // Release lock or notify others

    // Remainder Section
    // Other unrelated code
} while(TRUE);

Key Points:
	• Entry Section: Requests permission to enter.
	• Critical Section: Executes operations on shared resources.
	• Exit Section: Releases locks or signals completion.
	• Remainder Section: Executes the rest of the program.

### Requirements for a Solution to the Critical Section Problem
	*1. Mutual Exclusion*
		• Only one process/thread can execute in the critical section at a time.
		• Prevents simultaneous access to shared resources.
	*2. Progress*
		• If no process is in the critical section, one of the waiting processes must be allowed to enter.
		• Ensures system does not remain idle unnecessarily.
	*3. Bounded Waiting*
	• Limits how many times other processes can enter their critical sections before a waiting process is granted access.
	• Prevents starvation.

### Synchronization Mechanisms for Critical Sections

*i. Preemptive Kernels*
	• The OS can interrupt a running process even in kernel mode.
	• Enables better multitasking and responsiveness.
	• Complex to implement due to potential race conditions in kernel data structures.
	• Used in: Windows, Linux, macOS.

*ii. Non-Preemptive Kernels*
	• Once a process enters kernel mode, it runs until it blocks, exits, or voluntarily yields the CPU.
	• Easier to implement and avoids kernel-level race conditions.
	• Poor responsiveness.
	• Used in: Some older or embedded systems.

### Issues Related to Critical Sections

*Deadlock*
	• Occurs when two or more processes wait indefinitely for each other to release resources.

*Starvation*
	• A process is perpetually denied access to the critical section while others repeatedly enter.

*Overhead*
	• Acquiring and releasing locks incurs CPU and memory usage.

### Pseudo-code Representation

Simple Implementation

do {
    acquireLock();       // Entry section
    // Critical section
    releaseLock();       // Exit section
    // Remainder section
} while(true);

### Real-World Examples of Critical Sections

Application	Critical Section	Risk Without Synchronization
Banking System	Updating account balance	Incorrect balance due to concurrent access
Ticket Booking System	Reserving the last seat	Double booking, overbooking
Print Spooler	Adding print jobs to queue	Jobs may mix or be skipped
Shared Document Editing	Saving changes	Data loss or version conflict
Multiplayer Online Games	Updating player stats	Inconsistent game state
E-Commerce Inventory	Reducing item stock after order	Overselling of items

### Advantages of Using Critical Sections
	• Prevents race conditions by controlling access.
	• Enforces mutual exclusion to maintain data consistency.
	• Reduces CPU usage by minimizing unnecessary polling or spinning.
	• Simplifies synchronization logic for shared resources.

### Disadvantages of Critical Sections
	• Overhead due to synchronization mechanisms.
	• Deadlocks if not managed properly.
	• Limited parallelism if critical sections are too long.
	• Contention if too many processes compete for access.

### Real-Life Case: The Therac-25 Incident

The Therac-25 radiation therapy machine had a race condition in its software. A counter overflow during rapid terminal input caused safety locks to fail. As a result, several patients received fatal overdoses of radiation.
	• Root cause: Critical synchronization bug due to a race condition.
	• Takeaway: Even subtle bugs in timing can have severe consequences.

### Common Causes of Race Conditions
	• Multiple threads modifying shared global variables simultaneously.
	• Use-after-free errors where memory is deallocated before use.
	• Returning local variables from threads.
	• Calling non-thread-safe functions concurrently.

# What is a Deadlock?
A deadlock occurs when a group of processes becomes permanently blocked, with each process holding a resource and waiting for another resource that is currently held by another process in the group.

Deadlock is considered an infinite waiting state—once a process enters a deadlock, it cannot recover on its own. There is no automatic deadlock-stopping mechanism; only detection, prevention, or resolution techniques can handle it.

## How Does a Deadlock Occur?

![image](https://github.com/user-attachments/assets/d585dbbc-595e-4a20-804a-61a45eee7ce3)


*Consider two processes, Process A and Process B, and two resources, Resource 1 and Resource 2:*
- Process A acquires Resource 1
- Process B acquires Resource 2

*Now:*
- Process A requests Resource 2 (held by Process B)
- Process B requests Resource 1 (held by Process A)

*At this point:*
- Process A is waiting for Process B
- Process B is waiting for Process A

Since neither process can proceed without the other releasing its resource, both remain blocked indefinitely — this is a deadlock.

Breaking this deadlock would require external intervention, like the OS terminating one of the processes. Deadlocks are problematic because they waste resources and reduce system performance. Therefore, operating systems use resource allocation and scheduling algorithms to prevent, detect, or avoid deadlocks.

## Necessary Conditions for the Occurrence of a Deadlock
For a deadlock to occur in an operating system, four necessary conditions must hold simultaneously. If any one of these conditions is not met, a deadlock cannot arise. These conditions are:

### 1. Mutual Exclusion
This condition states that at least one resource must be non-shareable. That is, only one process can use the resource at any given time. If another process requests the same resource, it must wait until the resource is released.

*Example:* In a system where Process 1 holds Resource 1 and Process 2 holds Resource 2, both resources are exclusively assigned, and no other process can use them simultaneously.

### 2. Hold and Wait
According to this condition, a process must be holding at least one resource and simultaneously waiting to acquire additional resources that are currently being held by other processes.

*Example:* Process 1 holds Resource 1 and waits for Resource 2, which is held by Process 2. Similarly, Process 2 holds Resource 2 and waits for Resource 1.

### 3. No Preemption
This condition states that resources cannot be forcibly taken away from a process. A process must voluntarily release its held resources after completing its task.

*Example:* If Process P1 is holding Resource R1 and needs Resource R2 (held by Process P2), then P1 must wait. It cannot preempt R2 from P2. This may cause the system to enter a state of livelock if not handled properly.

### 4. Circular Wait
In this condition, a set of processes exists such that each process is waiting for a resource held by the next process in the chain, forming a circular chain.

![image](https://github.com/user-attachments/assets/872c4c84-2fe8-465d-9c0e-189a5e9cb5ce)

*Example:*

- Process P1 holds Resource R1 and waits for R2 (held by P2)

- Process P2 holds R2 and waits for R3 (held by P3)

- Process P3 holds R3 and waits for R4 (held by P4)

- Process P4 holds R4 and waits for R1 (held by P1)
  
This forms a circular wait, satisfying the final condition for deadlock.

## Deadlock Prevention
Deadlock prevention works by ensuring that at least one of the four necessary conditions for deadlock does not occur. These four conditions are:

1.Mutual Exclusion

2.Hold and Wait

3.No Preemption

4.Circular Wait

Below are the techniques to prevent each of these conditions:
### 1. Eliminate Mutual Exclusion
- Mutual exclusion means that resources cannot be shared and only one process can use a resource at a time.

- However, some resources are inherently non-shareable (e.g., printers, tape drives) and this condition cannot always be removed.

- For shareable resources, spooling can be used.

*Example – Spooling Technique:*

- Print jobs from processes are placed in a queue (spooler directory).

- The printer processes the jobs one-by-one (e.g., using FCFS).

- Processes don’t wait; they simply queue the job and move on.

### 2. Eliminate Hold and Wait
This condition occurs when a process is holding one resource while waiting for others.

![image](https://github.com/user-attachments/assets/5642a465-da7f-4627-af7d-49c4ac1ab5d5)


It can be prevented in two ways:

*a. By Eliminating Wait:*

A process must request all required resources at once, before it starts execution.

If all resources are not available, the process must wait before starting.

*b. By Eliminating Hold:*

A process must release all held resources before requesting new ones.

This prevents a process from holding resources while waiting.

### 3. Eliminate No Preemption
No preemption means that resources cannot be forcibly taken from a process.

Prevention strategies:

*a. Preempt Resources Voluntarily:*

A process must release resources if it is waiting for others to become available.

*b. Avoid Partial Allocation:*

- Allocate all resources at once.

- If not possible, do not allocate any and make the process wait.

### 4. Eliminate Circular Wait
Circular wait occurs when a set of processes are waiting on each other in a circular fashion.
It can be avoided by imposing an order on resource requests.

*Technique:*

- Assign a unique numerical ID to each resource.

- Processes must request resources in increasing order of their IDs.

- This breaks the circular chain, preventing deadlock.

## Deadlock Avoidance
Deadlock avoidance is a strategy used in operating systems to ensure that the system never enters a deadlock state. Unlike deadlock prevention, which structurally avoids one or more of the necessary conditions, deadlock avoidance involves careful analysis of resource allocation requests before granting them.

### Key Principle
A request for a resource is granted only if doing so does not lead the system into an unsafe state. An unsafe state does not necessarily mean a deadlock has occurred, but it means the system could eventually enter a deadlock state if further requests are made.

### How Deadlock Avoidance Works
- Each process must declare its maximum resource needs in advance.

- The operating system (kernel) will allocate resources only if it determines that doing so will still allow all processes to complete (i.e., the system remains in a safe state).

- If the resource request might lead to a deadlock, the process must wait.

This method is conservative, as the system avoids deadlocks by only allowing actions that are guaranteed to be safe.

### Banker’s Algorithm
Banker’s Algorithm is a well-known deadlock avoidance technique, named because it mimics how a bank might loan money only if it is sure it can satisfy future withdrawals.

*Inputs Required:*

1.Maximum Need – The maximum number of instances of each resource a process may request.

2.Allocation – The number of instances of each resource currently allocated to each process.

3.Available – The number of instances of each resource currently available in the system.

*Conditions for Granting a Request:*

A resource request from a process is granted only if:

- The requested resources are less than or equal to the process's declared maximum need.

- The requested resources are available in the system.

- After granting the request, the system remains in a safe state.

### Example of Banker’s Algorithm
*Total Resources in the System:*

| Resource | A | B | C | D |
| -------- | - | - | - | - |
| Total    | 6 | 5 | 7 | 6 |

*Currently Available Resources:*

| Resource  | A | B | C | D |
| --------- | - | - | - | - |
| Available | 3 | 1 | 1 | 2 |

*Allocated Resources:*                                         

| Process | A | B | C | D |
| ------- | - | - | - | - |
| P1      | 1 | 2 | 2 | 1 |
| P2      | 1 | 0 | 3 | 3 |
| P3      | 1 | 2 | 1 | 0 |

*Maximum Resources Required:*

| Process | A | B | C | D |
| ------- | - | - | - | - |
| P1      | 3 | 3 | 2 | 2 |
| P2      | 1 | 2 | 3 | 4 |
| P3      | 1 | 3 | 5 | 0 |

*Resource Need = Maximum - Allocated:*

| Process | A | B | C | D |
| ------- | - | - | - | - |
| P1      | 2 | 1 | 0 | 1 |
| P2      | 0 | 2 | 0 | 1 |
| P3      | 0 | 1 | 4 | 0 |

### Step-by-step Execution (Safe Sequence Check):
We need to find a sequence of processes where each one can finish with the available resources and return them for the next.

*Check P1:*

Need: (2,1,0,1)

Available: (3,1,1,2)

- P1 can be satisfied.

- P1 completes and releases its resources:

Allocation: (1,2,2,1)

New Available:
(3+1, 1+2, 1+2, 2+1) = (4, 3, 3, 3)

*Check P2:*

Need: (0,2,0,1)

Available: (4,3,3,3)

- P2 can be satisfied.

- P2 completes and releases its resources:

Allocation: (1,0,3,3)

New Available:
(4+1, 3+0, 3+3, 3+3) = (5, 3, 6, 6)

*Check P3:*

Need: (0,1,4,0)

Available: (5,3,6,6)

- P3 can be satisfied.

- P3 completes and releases its resources:

Allocation: (1,2,1,0)

New Available:
(5+1, 3+2, 6+1, 6+0) = (6, 5, 7, 6)

*Final Safe Sequence*
 
All processes can finish in the order:
P1 → P2 → P3

### Deadlock Detection And Recovery
Deadlock Detection and Recovery is the mechanism of detecting and resolving deadlocks in an operating system. In operating systems, deadlock recovery is important to keep everything running smoothly. A deadlock occurs when two or more processes are blocked, waiting for each other to release the resources they need.

- Deadlock detection is the process of identifying when processes are stuck waiting for resources held by other processes.
  
- Recovery is the method of resolving the deadlock to allow the system to continue functioning.
  
- Detection is done using techniques like Resource Allocation Graphs (RAG) or Wait-for Graphs.
  
- Once a deadlock is detected, recovery methods include process termination, resource preemption, or process rollback.

*Conclusion:*

- The system is in a safe state.

- A safe sequence exists: P1, P2, P3

- Hence, current resource allocation will not lead to deadlock.


# Operating system based Virtualization
Operating System-based Virtualization, also known as Containerization, is a lightweight virtualization method that enables multiple isolated user-space instances, called containers, to run on a single operating system kernel.

Unlike traditional virtualization, where each virtual machine (VM) includes its own OS along with the application, containerization allows all containers to share the same OS kernel, significantly reducing resource usage and improving performance.

## Operating System Based Operations
Various major operations of Operating System Based Virtualization are described below:  

- Hardware capabilities can be employed such as the network connection and CPU.
- Connected peripherals with which Host OS can interact such as a webcam, printer, keyboard, or scanners.
- Host OS can be used to read or write data in files, folders, and network shares.

The image below illustrates the architecture of traditional virtualization using Virtual Machines (VMs). In this model, each VM functions as an independent environment, running its own guest operating system and application software. Since every VM has a separate operating system, this leads to increased resource usage. The Virtual Machine Management layer handles the control and coordination of these VMs, ensuring appropriate allocation of resources like CPU, memory, and storage, while also maintaining isolation between them.

Above the physical hardware lies the host operating system, which provides the foundation for the hypervisor to run. The hypervisor is responsible for creating, managing, and assigning resources to the virtual machines. The underlying hardware—referred to as the virtualization host—supplies the computing power and infrastructure needed to support the hypervisor and run multiple VMs at the same time.

![image](https://github.com/user-attachments/assets/d0f49692-b34d-42e5-8899-66ff7c4990aa)

### Full Virtualization
Full virtualization is a virtualization technique in which the entire hardware of a machine is simulated, allowing unmodified guest operating systems to run in isolation. This method uses a hypervisor to create a complete virtual replica of the underlying hardware, which allows multiple guest operating systems to run independently on the same physical machine.

- The guest OS is unaware that it is running in a virtualized environment.

- It does not require modification of the guest operating system.

- Full virtualization uses binary translation to trap and translate privileged instructions.

- It provides complete isolation between the guest OS and the host system.

- Examples: VMware, Microsoft Hyper-V, Parallels.

### Para Virtualization
Para virtualization is a virtualization technique where the guest operating system is aware that it is being virtualized. The OS is modified to replace sensitive instructions with hypercalls to the hypervisor, improving performance by avoiding the need for binary translation.

- The guest OS must be modified before it can be used in a virtualized environment.

- It communicates directly with the hypervisor using hypercalls.

- This method provides better performance compared to full virtualization because it eliminates the overhead of trapping and translating instructions.

- However, it lacks compatibility with unmodified operating systems.

- Examples: Xen hypervisor with para-virtualized Linux kernels.

## Hypervisor
A hypervisor is a virtualization software that enables a single physical machine to run multiple guest operating systems simultaneously by dividing and allocating hardware resources among them. It acts as a virtual machine manager (VMM), providing partitioning, isolation, and abstraction of the underlying hardware. Hypervisors are commonly used in cloud hosting environments to efficiently manage resources.

### Types of Hypervisor
### 1.Type-1 Hypervisor:

Also known as a native or bare-metal hypervisor, this type runs directly on the host’s hardware without needing an underlying operating system. It has direct control over the physical hardware resources such as CPU, memory, network, and storage. Popular examples include VMware ESXi, Microsoft Hyper-V, and Citrix XenServer.

*Pros and Cons of Type-1 Hypervisor*

*Pros:*

- High efficiency due to direct access to hardware resources.

- Enhanced security, as there is no intermediary operating system or third-party software layer that could be compromised.

*Cons:*

- Typically requires a dedicated physical machine to run.

- Needs specialized setup and management since it controls hardware and multiple virtual machines directly.

### 2.Type-2 Hypervisor
A Type-2 hypervisor, also known as a hosted hypervisor, runs on top of a host operating system rather than directly on the hardware. Essentially, it operates as an application within the host OS and relies on it to make hardware calls. Unlike Type-1 hypervisors, it does not have direct access to the physical hardware. Examples of Type-2 hypervisors include VMware Player and Parallels Desktop. These are commonly used on personal computers and endpoints. Type-2 hypervisors are especially useful for engineers and security analysts who need to run guest operating systems for testing malware, analyzing code, or developing new applications.

*Pros and Cons of Type-2 Hypervisor*

*Pros:*

- Provides easy and quick access to guest operating systems alongside the host OS.

- Often includes additional features that improve interaction and coordination between the host and guest machines.

*Cons:*

- Since it does not have direct access to hardware, it is generally less efficient and performs slower compared to Type-1 hypervisors.

- Potential security risks exist because if an attacker compromises the host OS, they may also gain access to the guest OS running on the hypervisor.

## Virtual Machines in Operating Systems
A Virtual Machine (VM) is an operating system or application environment that runs on software designed to simulate hardware. The user experience while using a virtual machine is effectively the same as using dedicated physical hardware.

A Virtual Machine abstracts the physical hardware of a computer—such as the CPU, disk drives, memory, and network interface card (NIC)—and presents multiple independent execution environments as needed. For example, software like VirtualBox enables this abstraction. When different processes run on an operating system, they each appear to have their own processor and virtual memory through CPU scheduling and virtual memory management techniques.

While hardware alone can provide some features like CPU and memory virtualization, additional functionalities like system calls and file systems are supported by the operating system. Virtual machines do not provide these extra OS features directly but instead offer an interface that mimics basic hardware.

Each process or VM is given a virtual copy of the underlying computer system. This setup allows sharing the same physical hardware while running different execution environments or operating systems simultaneously.

One limitation of the virtual machine approach concerns disk resources. Suppose a physical machine has only three disk drives but must support seven virtual machines. It cannot assign a physical disk drive to each VM. Instead, virtual disks are created using storage space on the physical machine. This virtual disk allows each VM to operate as if it has its own disk.

The virtual-machine software manages the multiplexing of multiple virtual machines onto a single physical machine, but it does not handle user-support software. This separation simplifies the design of multi-user interactive systems by dividing it into two manageable parts.

### Types of Virtual Machines
Virtual machines are generally classified into two types:

*Process Virtual Machine:* Designed to run a single program, providing a platform-independent programming environment.

*System Virtual Machine:* Provides a complete system platform that supports the execution of a full operating system.




